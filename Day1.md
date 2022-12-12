# Day One
Sessions on day one of the Secure Multi-Cloud Environments hack around our [Imbroglio Group scenario](Scenario.md).

## Agenda
| **Time** | **Description**
| :--- | :---
| 0930 | Welcome and Housekeeping
| 0945 | `[LAB]` Preparing your AAD tenant
| 1030 | Azure AD for Single Sign-on with AWS
| 1100 | `[LAB]` Integrating AWS with AAD
| 1200 | Lunch
| 1230 | Entra Permissions Management (EPM) Overview
| 1300 | `[LAB]` Onboarding AWS into EPM
| 1400 | Planning your MDC deployment
| 1430 | `[LAB]` Enrolling AWS servers into MDC
| 1500 | Within your group - present to proctor
| 1530 | Q&A, Discussion around partner challenges

## Scenario
[Background information on the hackathon scenario.](Scenario.md)

## Day 1 Challenge
Onboarding your resources.
1. Ensure your Azure AD tenant has MFA enabled and that all user accounts are using just enough access and following least privilege. 
2. Configure an AWS account to use Azure AD for single-sign on.
3. Configure Entra Permissions Management (EPM) and onboard your AWS account into EPM
4. Configure Defender for Cloud's enhanced security features
5. Connect your AWS account to Microsoft Defender for Cloud (MDC) and entroll your virtual machine(s) (and containers if you want a bigger challenge) into Defender for Servers.
6. Present back to your proctor.

### Prerequisites
[There are a number of activities to perform and requirements to meet in order to participate.](Prerequisites.md)

### Introduction
Day one is all about getting your AWS tenants and resources onboarded, so that you can work with those resources on the following days.

### Learn more / lab resources
#### Azure AD (AAD)
1. Preparing your AAD tenant
   - Hardening
     - Option A: Enable Secure by Default:
       - [ ] Enable from security config: https://learn.microsoft.com/en-us/azure/active-directory/fundamentals/concept-fundamentals-security-defaults
     - Option B: Common Conditionl Access policies:
       - [ ] Require MFA for administrators: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa
       - [ ] Securing security info registration: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-registration
       - [ ] Require MFA for Azure management: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management
       - [ ] Block legacy authentication: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy
       - [ ] Require MFA for all users: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa
       - [ ] Review general CA deployment guidance and other Common CA policies: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/plan-conditional-access
   - Relevant entities
     - Group (a): Create AAD Security Group used as VM administrators
     - Group (b): Create AAD Security Group used as VM members
     - Group (c): Create AAD Security Group used to access AWS (SSO)
     - Modify firstname, lastname for AWS-User following the requirements by AWS: https://learn.microsoft.com/en-us/azure/active-directory/saas-apps/aws-single-sign-on-provisioning-tutorial#missing-attributes
     - User: Create hackadmin1 as a member of AAD Security Group (a)
     - User: Create hackuser1 as a member of AAD Security Group (b)
```powershell
#USERS
$domain = az ad signed-in-user show --query 'userPrincipalName' | cut -d '@' -f 2 | sed 's/\"//'
$hackadmin1 = "hackadmin"
$hackadmin1pw = "$(-join ((48..57) + (64..90) + (97..122)| Get-Random -Count 12 | foreach {[char]$_}))#"
$admin = az ad user create --display-name $hackadmin1 --password $hackuser1pw --user-principal-name "$($hackadmin1)@$($domain)" | ConvertFrom-Json 
Write-Host "=> AAD user created. UPN: '$($hackadmin1)@$($domain)' - Password: '$($hackadmin1pw)'"
$hackuser1 = "hackuser"
$hackuser1pw = "$(-join ((48..57) + (64..90) + (97..122)| Get-Random -Count 12 | foreach {[char]$_}))#"
$user = az ad user create --display-name $hackuser1 --password $hackuser1pw --user-principal-name "$($hackuser1)@$($domain)" | ConvertFrom-Json 
Write-Host "=> AAD user created. UPN: '$($hackuser1)@$($domain)' - Password: '$($hackuser1pw)'"
$hackaws1 = "hackaws"
$hackaws1pw = "$(-join ((48..57) + (64..90) + (97..122)| Get-Random -Count 12 | foreach {[char]$_}))#"
$aws = az ad user create --display-name $hackaws1 --password $hackaws1pw --user-principal-name "$($hackaws1)@$($domain)" | ConvertFrom-Json 
Write-Host "=> AAD user created. UPN: '$($hackaws1)@$($domain)' - Password: '$($hackaws1pw)'"

#GROUPS
$grpAdmin = az ad group create --display-name "hackVMadmin" --mail-nickname "hackVMadmin" --description "Used to grant admin privileges on Virtual Machines" --force true | ConvertFrom-Json 
az ad group member add --group $grpAdmin.id --member-id $admin.id
$grpUser = az ad group create --display-name "hackVMuser" --mail-nickname "hackVMuser" --description "Used to grant user privileges on Virtual Machines" --force true | ConvertFrom-Json 
az ad group member add --group $grpUser.id --member-id $user.id
$grpAWS = az ad group create --display-name "hackAWS" --mail-nickname "hackAWS" --description "Used to grant access to AWS" --force true | ConvertFrom-Json 
az ad group member add --group $grpAWS.id --member-id $aws.id

```
2. Authenticate to Azure hosted Windows-VMs using AAD credentials
     - [ ] Register connecting client in target tenant: Settings -> Accounts -> E-Mail & accounts ->  Add a work or school account
     - [ ] Remove Workplace Join: Settings -> Accounts -> Access work or school -> Expand used identity -> Disconnect
3. Workload 1: Create Azure hosted Windows VM & enable AAD login
   - [ ] Register Resource Group and assign relevant roles:
```powershell
$location = "EastUS"
$resourceGroup = "hackathon"
$rg = az group create --name $resourceGroup --location $location --verbose | ConvertFrom-Json
$grpAdmin = az ad group show --group "hackVMadmin" | ConvertFrom-Json
$grpUser = az ad group show --group "hackVMuser" | ConvertFrom-Json
az role assignment create --assignee-object-id $grpAdmin.id --assignee-principal-type Group --role "Virtual Machine Administrator Login" --scope $rg.id
az role assignment create --assignee-object-id $grpUser.id --assignee-principal-type Group --role "Virtual Machine User Login" --scope $rg.id
```
 - [ ] Create Windows based Virtual Machine and join to AAD
```powershell
$vmWinName = "hackWinA"
$size = "Standard_DS1_v2"
$adminacc = "azureadmin"
$adminpw = "$(-join ((48..57) + (64..90) + (97..122)| Get-Random -Count 12 | foreach {[char]$_}))#"
az vm create --resource-group $resourceGroup --name $vmWinName --image Win2022Datacenter --admin-username $adminacc --admin-password $adminpw --size $size --os-disk-name "$($vmWinName )OsDisk" --public-ip-address "$($vmWinName)PIP" --public-ip-sku Standard --assign-identity --verbose
az vm auto-shutdown --resource-group $resourceGroup --name $vmWinName --time 1900
az vm extension set --publisher Microsoft.Azure.ActiveDirectory --name AADLoginForWindows --resource-group $resourceGroup --vm-name $vmWinName

$vmPIP = az vm list-ip-addresses --resource-group $resourceGroup --name $vmWinName --query "[].virtualMachine.network.publicIpAddresses[*].ipAddress" -o tsv
Write-Host "=> RDP connection available via PublicIP: '$($vmPIP)' using local credentials '$($adminacc)':'$($adminpw)' or Members of $($grpAdmin.displayName)/$($grpUser.displayName)"![image](https://user-images.githubusercontent.com/70759212/207049038-9adabb54-3a68-49b5-bbf8-8ad390db3221.png)
```
4. Workload 2: Integrate AWS as a Single-Sign-On application in AAD: https://learn.microsoft.com/en-us/azure/active-directory/saas-apps/aws-single-sign-on-tutorial
 - Enable AWS IAM Identity Center
   - [ ] Authenticate as Root User: https://us-east-1.console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin&region=us-east-1&skipRegion=true#
   - [ ] Naviate to IAM Identity Center: Menu -> Security, Identity, Compliance -> IAM Identity Center (successor to AWS Single Sign-On): https://us-east-1.console.aws.amazon.com/singlesignon/home?region=us-east-1#/
   - [ ] Enable IAM Identity Center
   <img width="251" alt="image" src="https://user-images.githubusercontent.com/70759212/207055626-13e0d3fc-add3-497f-a28b-e529ca0224ee.png">
   
   - [ ] Confirm to create AWS Organization (one-time-action per AWS account)
   <img width="435" alt="image" src="https://user-images.githubusercontent.com/70759212/207056010-2781b930-31d8-4608-8ed1-383c4c8654f3.png">
   
   - [ ] Enable External Identity Provider as Identity Source: 
   <img width="616" alt="image" src="https://user-images.githubusercontent.com/70759212/207114818-7ca2805b-f3b4-43ba-a50b-4c400296cdbe.png">
  
   - [ ] Download service provide metadata file
   <img width="585" alt="image" src="https://user-images.githubusercontent.com/70759212/207115519-5d2b4b33-d0a5-4e98-af7f-3db42867f83d.png">

   - [ ] Register 'AWS IAM Identity Center (successor to AWS Single Sign-On)' in Enterprise Gallery: https://portal.azure.com/#view/Microsoft_AAD_IAM/AppGalleryBladeV2
   - [ ] Assign AWS-group to SP
   - [ ] Enable Saml-based SSO and download Federation Metadata XML
   - [ ] Upload Metadata XML, review and "ACCEPT" ne identity provider 
   - [ ] Enable Provisioning Mode - Automatic
#### Entra Permissions Management (EPM)
1. [Getting started with EPM](/labs/EPM-labs.md#getting-started-with-entra-permissions-management-epm) Steps 1-4.

#### Microsoft Defender for Cloud (MDC)
1. [Planning your Defender for Cloud Deployment](https://docs.microsoft.com/en-us/azure/defender-for-cloud/security-center-planning-and-operations-guide)
2. [Connect MDC to AWS](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws)
   - [Official MDC lab - Creating an AWS connector](https://github.com/Azure/Microsoft-Defender-for-Cloud/blob/main/Labs/Modules/Module-11-AWS.md#exercise-2-create-an-aws-connector-for-the-new-aws-account-in-microsoft-defender-for-cloud)
4. [Defender for Servers Inttroduction](https://docs.microsoft.com/en-us/azure/defender-for-cloud/defender-for-servers-introduction)
5. [Selecting a Defender for Servers Plan](https://learn.microsoft.com/en-us/azure/defender-for-cloud/plan-defender-for-servers-select-plan)

