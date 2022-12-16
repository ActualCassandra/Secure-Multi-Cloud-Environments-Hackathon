# Day Three
Sessions on day three of the Secure Multi-Cloud Environments hack around our [Imbroglio Group scenario](Scenario.md).

## Agenda
Times are estimates. 
| **Time** | **Description**
| :--- | :---
| 0930 | Welcome and kick-off
| 1030 | `[LAB]` Threat hunting in MDC
|  | `[LAB]` Threat hunting in the M365 Security Portal
|  | `[LAB]` Workflow automation in MDC
| 1200 | Lunch
| 1230 | Microsoft Sentinel Overview
|  | `[LAB]` Connecting data sources
|  | `[LAB]` Tying it all together
|  | `[LAB]` KQL
| 1500 | Within your group - present to proctor. Live 'show and tell' in the portal or screenshots of the completion of each step.
| 1530 | Q&A, Discussion around partner challenges and goodbyes

## Scenario
[Background information on the hackathon scenario.](Scenario.md)

## Day 3 Challenge
Find and block threats in your cloud environments.

1. [Create sample alerts in MDC](https://docs.microsoft.com/en-us/azure/defender-for-cloud/alert-validation#generate-sample-security-alerts)
2. [Generate test alerts on your server](https://docs.microsoft.com/en-us/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#send-a-test-alert)
3. Manually trigger ransomware alerts from your VM (try and download something dodgy)
4. [Find threats in your AWS environment using MDC](https://learn.microsoft.com/en-us/azure/defender-for-cloud/managing-and-responding-alerts)
5. [Find threats in the M365 security portal](https://learn.microsoft.com/en-us/microsoft-365/security/defender/incident-response-overview?view=o365-worldwide)
6. [Create a MDC workflow automation to isolate your virtual machine](https://github.com/ActualCassandra/Secure-Multi-Cloud-Environments-Hackathon/blob/main/labs/MDC-labs.md#isolate-a-machine-impacted-by-ransomware)
  - STRETCH GOAL - improve the logic app
7. IF YOU'VE NOT ALREADY DONE THIS - [Create a Microsoft Sentinel workspace](https://learn.microsoft.com/en-us/training/modules/create-manage-azure-sentinel-workspaces/3-create-azure-sentinel-workspace)
8. [Connect lab data sources into Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/connect-defender-for-cloud)
9. :timer_clock: DEPENDING ON TIME: Identity AWS-originating alerts in Microsoft Sentinel
10. :timer_clock: DEPENDING ON TIME: Using KQL to query for AWS-related security alerts (missing SME today :( )
11. Present back to your proctor

### Prerequisites
You must have completed the labs from [Day 1](Day1.md), except for AWS SSO.

Also, if you want to test ransomware on your virtual machine, you'll need a way to access it via RDP (but make sure the AWS security group only allows access from your IP(s)).

### Introduction
Day three is around threat hunting and detection and response in MDC and Sentinel. Depending on Time, Sentinel may end up being optional.

### Learn more / lab resources
:warning: Many people use multiple accounts in their day-to-day activities. Make sure you are using an InPrivate/Private/Incognito browser session or a have the browser set to a specific session for  the user account you will use for the labs.

#### Microsoft Defender for Cloud (MDC)
1. [Workflow automation in MDC](https://docs.microsoft.com/en-us/azure/defender-for-cloud/workflow-automation))
2. [Alert validation in Microsoft Defender for Cloud-Create Sample alerts](https://docs.microsoft.com/en-us/azure/defender-for-cloud/alert-validation#generate-sample-security-alerts)
3. [Defender for Cloud ninja training](https://aka.ms/ascninja)

#### Microsoft Defender for Endpoint (MDE)
1. [Generate test alerts on server in MDE](https://docs.microsoft.com/en-us/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#send-a-test-alert)

#### Microsoft Sentinel
1.  [Azure Sentinel Training Lab](https://github.com/Azure/Azure-Sentinel/tree/master/Solutions/Training/Azure-Sentinel-Training-Lab)
2.  [Microsoft Sentinel Ninja training](https://aka.ms/sentinelninja)
3.  [Getting started with Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/quickstart-onboard)
4.  [Create a Microsoft Sentinel workspace](https://learn.microsoft.com/en-us/training/modules/create-manage-azure-sentinel-workspaces/3-create-azure-sentinel-workspace)
5. [AWS S3 Connector](https://docs.microsoft.com/en-us/azure/sentinel/connect-aws?tabs=s3) [![](https://img.shields.io/badge/-STRETCH%20GOAL-important?style=flat)](#stretch-goals)
6. [Kusto Query Language (KQL)](https://learn.microsoft.com/en-us/azure/sentinel/kusto-overview)
7. [Must Learn KQL](https://aka.ms/mustlearnkql)
