# Day Three
Sessions on day three of the Secure Multi-Cloud Environments hack around our [Imbroglio Group scenario](Scenario.md).

## Agenda
| **Time** | **Description**
| :--- | :---
| 0930 | Welcome and kick-off
| 0945 | `[LAB]` Threat hunting in MDC
|  | `[LAB]` Threat hunting in the M365 Security Portal
|  | `[LAB]` Workflow automation in MDC
| 1200 | Lunch
| 1230 | Microsoft Sentinel Overview
|  | `[LAB]` Connecting data sources
|  | `[LAB]` Tying it all together
|  | `[LAB]` KQL
| 1500 | Within your group - present to proctor
| 1530 | Q&A, Discussion around partner challenges and goodbyes

## Scenario
[Background information on the hackathon scenario.](Scenario.md)

## Day 3 Challenge
Find and block threats in your cloud environments.
1. Generate test alerts in the M365 security portal
2. Create sample alerts in the MDC blade
3. Manually trigger ransomware alerts from your VM
4. Find threats in your AWS environment using the MDC blade
5. Find threats in the M365 security portal
6. Create a MDC workflow automation to isolate your virtual machine
7. Create a Microsoft Sentinel workspace
8. Connect lab data sources into Microsoft Sentinel
9. :timer_clock: DEPENDING ON TIME: Identity AWS-originating alerts in Microsoft Sentinel
10. :timer_clock: DEPENDING ON TIME: Using KQL to query for AWS-related security alerts
11. Present back to your proctor

### Prerequisites
You'll need to complete the labs from [Day 1](Day1.md), except for AWS SSO.

### Introduction
Day three is around threat hunting and detection and response in MDC and Sentinel.

### Learn more / lab resources

#### Microsoft Defender for Cloud (MDC)
1. [Workflow automation in MDC](https://docs.microsoft.com/en-us/azure/defender-for-cloud/workflow-automation))
2. [Alert validation in Microsoft Defender for Cloud-Create Sample alerts](https://docs.microsoft.com/en-us/azure/defender-for-cloud/alert-validation#generate-sample-security-alerts)

#### Microsoft Defender for Endpoint (MDE)
1. [Generate test alerts on server in MDE](https://docs.microsoft.com/en-us/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#send-a-test-alert)

#### Microsoft Sentinel
1. [AWS S3 Connector](https://docs.microsoft.com/en-us/azure/sentinel/connect-aws?tabs=s3) [![](https://img.shields.io/badge/-STRETCH%20GOAL-important?style=flat)](#stetch-goals)
2. [Kusto Query Language (KQL)](https://learn.microsoft.com/en-us/azure/sentinel/kusto-overview)
3. [Must Learn KQL](https://aka.ms/mustlearnkql)
