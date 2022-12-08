# Day One
Sessions on day one of the Secure Multi-Cloud Environments hack around our Imbroglio Group scenario.

## Agenda
| **Time** | **Description**
| :--- | :---
| 0930 | Welcome and Housekeeping
| 0945 | Azure AD for Single Sign-on with AWS
| 1030 | `[LAB]` Preparing your AAD tenant
| 1100 | `[LAB]` Integrating AWS with AAD
| 1200 | Lunch
| 1230 | Entra Permissions Management (EPM) Overview
| 1300 | `[LAB]` Onboarding AWS into EPM
| 1400 | `[LAB]` Planning your MDC deployment
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
4. Connect your AWS account to Microsoft Defender for Cloud (MDC) and entroll your virtual machine(s) (and containers if you want a bigger challenge) into Defender for Servers.
5. Present back to your proctor.

### Prerequisites
[There are a number of activities to perform and requirements to meet in order to participate.](Prerequisites.md)

### Introduction
Day one is all about getting your AWS tenants and resources onboarded, so that you can work with those resources on the following days.

### Learn more / lab resources
#### Azure AD (AAD)
1. Azure AD for SSO with AWS

#### Entra Permissions Management (EPM)
1. [Getting started with EPM](/labs/EPM-labs.md#getting-started-with-entra-permissions-management-epm) Steps 1-4.

#### Microsoft Defender for Cloud (MDC)
1. [Planning your Defender for Cloud Deployment](https://docs.microsoft.com/en-us/azure/defender-for-cloud/security-center-planning-and-operations-guide)
2. [Connect MDC to AWS](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws)
3. [Defender for Servers](https://docs.microsoft.com/en-us/azure/defender-for-cloud/defender-for-servers-introduction)

