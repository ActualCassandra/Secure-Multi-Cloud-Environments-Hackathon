# Prerequisites
Please go through this list of prerequisites before attending one of our multi-cloud security partner hacks. 

## Tenants
Depending on the specific hack, you will need to have access to tenants in:
 - [Microsoft Azure](https://azure.microsoft.com/en-gb/free/), plus
 - [Amazon Web Services (AWS)](https://aws.amazon.com/free/) or
 - [Google Cloud Platform (GCP)](https://cloud.google.com/blog/products/gcp/getting-started-with-google-cloud-for-free)
 
 *Some stretch goals will entail working in both AWS and GCP.*

## Tenant-level permissions
High levels of access are required in all tenants. Please ensure that you have also properly secured access into your tenant (such as requiring [MFA](https://learn.microsoft.com/en-us/azure/active-directory/authentication/howto-mfa-getstarted) and using [PIM](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started) in Azure, or [MFA in AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_enable_virtual.html) and [MFA in GCP](https://cloud.google.com/identity/solutions/enforce-mfa).

### Azure permissions
 - [It depends](https://learn.microsoft.com/en-us/azure/defender-for-cloud/permissions#roles-and-allowed-actions), but for the purposes of this lab, Owner to the subscription being used will be make things simpler for MDC. In the real world, please use [Azure PIM](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started) and least privilege depending on the specific role requirements.
 - In order to enable Entra Permissions Management, you will need *global administrator* permissions as a user in your tenant. [Learn more](https://learn.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-enable-tenant#prerequisites).
### AWS Permissions
 - [Administrator on the AWS account being used](https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#availability)
### GCP Permissions
 - [Owner on the GCP organization or project being used](https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings#availability)

## Services
You will have to ensure you have enabled the following services, trial or otherwise.
 - [Defender for Cloud Enhanced Security Features](https://learn.microsoft.com/en-us/azure/defender-for-cloud/enable-enhanced-security)
 - [Entra Permissions Management](https://learn.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-enable-tenant)
 - [Azure AD P2](https://learn.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-get-started-premium)

## Resources
:warning: This hackathon needs some compute resources running in your multi-cloud environment(s).

**Virtual Machines/Servers**
 - You'll need a virtual machine running Windows Server 2019, with 2-4 vCPU, and 2-4 GB RAM. Something like a t2.medium. This will go beyond free tier limits but you'll only be running this virtual machine for a few days.
   - The virtual machine needs to have AWS Systems Manager (SSM) agent installed, [choose an AMI which comes with it](https://docs.aws.amazon.com/systems-manager/latest/userguide/ami-preinstalled-agent.html), or [install manually](https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-install-managed-win.html).
   - Verify that the pre-requisites have not changed at this Microsoft Docs link - [AWS virtual machine pre-requisites: Scroll down to 'To enable the Defender for Servers plan](https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#prerequisites)
 - [Virtual machine requirements for Defender for Servers](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/minimum-requirements?view=o365-worldwide#hardware-and-software-requirements)
 - DO NOT UPDATE THE OPERATING SYSTEM

**Containers**

 - You'll need at least one Amazon EKS cluster with permissions to access the EUKS K8s API server. If you are creating a new cluster, folow these instructions: https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html
 - The resource capacity to create a new SQS queue, Kinesis Fire Hose delivery stream, and S3 bucket in the cluster's region.
   - Verify that the pre-requisites have not changed at this Microsoft Docs link - [AWS container pre-requisites: Scroll down to 'To enable the Defender for Containers plan](https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#prerequisites)
 - [Supported features by environment](https://learn.microsoft.com/en-us/azure/defender-for-cloud/supported-machines-endpoint-solutions-clouds-containers?tabs=aws-eks#supported-features-by-environment)

## Checks

[SSM Agent Installation verification:](https://docs.aws.amazon.com/systems-manager/latest/userguide/ssm-agent-status-and-restart.html)
 - Linux: In your shell - `sudo systemctl status amazon-ssm-agent`
 - Windows: Run in PowerShell - `Get-Service AmazonSSMAgent`
