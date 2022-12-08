# Day Two
Sessions on day two of the Secure Multi-Cloud Environments hack around our [Imbroglio Group scenario](Scenario.md).

## Agenda
| **Time** | **Description**
| :--- | :---
| 0930 | Welcome day kick-off
| 0945 | `[LAB]` Multi-cloud CSPM with MDC
|  | `[LAB]` Custom standards and assessments
|  | `[LAB]` Setting up governance
| 1200 | Lunch
| 1230 | EPM in MDC
| 1240 | `[LAB]` Permissions on Demand
|  | `[LAB]` Just enough access policy creation
|  | `[LAB]` Rightsizing permissions
|  | `[LAB]` Setting up alerts
| 1500 | Within your group - present to proctor
| 1530 | Q&A, Discussion around partner challenges

## Scenario
[Background information on the hackathon scenario.](Scenario.md)

## Day 2 Challenge
Configuring and making use of MDC and EPM.
1. Find recommendations specific to AWS
2. Create regulatory compliance standard and ensure the same one is used in AWS and Azure
3. Set up governance rules with the relevant owners in AWS and Azure
4. Identity Entra Permissions Management's Permissions Creep Index recommendations in the MDC blade
5. Create custom policies in EPM
6. Change permissions to follow least privilege
7. Configure permissions on demand for the EC2 VM
8. Configure alerts in EPM
9. Present back to your proctor

### Prerequisites
You will have to have completed ***most*** of the day 1 activities - AWS SSO is *optional*. which means:
1. Connected EPM to AWS
2. Connected MDC to AWS
3. Onboarded your server(s) into MDC / Defender for servers

### Introduction
Day two will involve finishing the configuration of and using Entra Permissions Management (EPM) and Microsoft Defender for Cloud (MDC) which had the basic configuration on day one, including connecting to AWS.

### Learn more / lab resources
#### Microsoft Defender for Cloud (MDC)
1. [EPM's Permission Creep Index in MDC](https://docs.microsoft.com/en-us/azure/defender-for-cloud/other-threat-protections#entra-permission-management-formerly-cloudknox)
   - [YouTube Video](https://www.youtube.com/watch?v=dasixjOOldk)
2. [Custom Standards and Assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/custom-assessments-and-standards-in-microsoft-defender-for-cloud/ba-p/3066575)
3. [Setting up governance in Defender for Cloud](https://docs.microsoft.com/en-us/azure/defender-for-cloud/governance-rules)
   - [Official MDC lab on configuring governance](https://github.com/Azure/Microsoft-Defender-for-Cloud/blob/main/Labs/Modules/Module-13-Governance.md#exercise-1-add-a-new-governance-rule-in-microsoft-defender-for-cloud)

#### Entra Permissions Management (EPM)
1. [Getting started with EPM](/labs/EPM-labs.md#getting-started-with-entra-permissions-management-epm) Starting from Step 5, permissions on demand.



