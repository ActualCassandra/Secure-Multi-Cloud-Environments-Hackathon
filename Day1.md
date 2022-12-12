# Day One
Sessions on day one of the Secure Multi-Cloud Environments hack around our [Imbroglio Group scenario](Scenario.md).

## Agenda
Times are estimates.
| **Time** | **Description**
| :--- | :---
| 0930 | Welcome and Housekeeping
| 0945 | `[LAB]` Preparing your AAD tenant
| 1030 | Azure AD for Single Sign-on with AWS
| 1100 | `[LAB]` Integrating AWS with AAD
| 1200 | Lunch
| 1230 | Entra Permissions Management (EPM) Overview
| 1300 | `[LAB]` Onboarding into EPM
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
5. Connect your AWS account to Microsoft Defender for Cloud (MDC) and entroll your virtual machine(s) (and containers *if you want a bigger challenge*) into Defender for Servers.
6. Present back to your proctor. Live 'show and tell' in the portal or screenshots of the completion of each step.

### Prerequisites
[There are a number of activities to perform and requirements to meet in order to participate.](Prerequisites.md)

### Introduction
Day one is all about getting the service basics congigured, your Azure tenant locke down, and your AWS tenant and resources onboarded, so that you can work with those resources on the following days.

### Learn more / lab resources
:warning: Many people use multiple accounts in their day-to-day activities. Make sure you are using an InPrivate/Private/Incognito browser session or a have the browser set to a specific session for  the user account you will use for the labs.

#### Azure AD (AAD)
1. [Azure AD for SSO with AWS](https://learn.microsoft.com/en-us/azure/active-directory/saas-apps/aws-single-sign-on-tutorial#next-steps)

#### Entra Permissions Management (EPM)
1. [Getting started with EPM](/labs/EPM-labs.md#getting-started-with-entra-permissions-management-epm) Steps 1-4.

#### Microsoft Defender for Cloud (MDC)
1. [Planning your Defender for Cloud Deployment](https://docs.microsoft.com/en-us/azure/defender-for-cloud/security-center-planning-and-operations-guide)
2. [Connect MDC to AWS](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws)
   - [Official MDC lab - Creating an AWS connector](https://github.com/Azure/Microsoft-Defender-for-Cloud/blob/main/Labs/Modules/Module-11-AWS.md#exercise-2-create-an-aws-connector-for-the-new-aws-account-in-microsoft-defender-for-cloud)
4. [Defender for Servers Introduction](https://docs.microsoft.com/en-us/azure/defender-for-cloud/defender-for-servers-introduction)
5. [Selecting a Defender for Servers Plan](https://learn.microsoft.com/en-us/azure/defender-for-cloud/plan-defender-for-servers-select-plan)

