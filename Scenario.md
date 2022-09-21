# Scenario
Your customer, Imbroglio Group, recently started its cloud journey and has suffered a security breach. You have been brought in to help it get the basics right and secure its multi cloud architecture; you have been asked to deliver a proof of concept.

## Introduction
Your customer, Imbroglio, is already using Azure and has synchronised with their on-premise Active Directory. However, the AWS tenant for the proof of concept has been treated as an entirely separate entity. They do not have any security teams and their infrastructure team has been managing their cloud environments. 

After their recent breach, new corporate security control requirements have been drafted, and compliance and governance are now very important.

Imbroglio will mainly run PaaS services in Azure but has servers and containers running in its other cloud provider(s). 

You have been asked to:
 - Improve the security of Azure AD implementation
 - Control access into AWS using Azure AD
 - Ensure their cloud identities are following good practice
 - Gain visibility of all cloud resources and protect Imbroglio's cloud workloads
 - Ensure that any security recommendations are actioned by the appropriate team(s)
 - Help Imbroglio adhere to their corporate security control requirements 
 - Automate provisioning as well as the detection and response of security incidents


## The Hack
This hack will cover the following topics:
1. Multi-cloud identity and access management with Entra
2. Protecting multi-cloud resources with Defender for Cloud and Azure Arc
3. Multi-cloud automation, detection, and response

## The basics
This hack will cover the technologies below and a basic understanding is required.
 - [Azure Active Directory](https://learn.microsoft.com/en-gb/azure/active-directory/fundamentals/active-directory-whatis)
 - [Entra Permissions Management](https://learn.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/overview)
 - [Microsoft Defender for Cloud](https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-cloud-introduction)
 - [Azure Arc](https://learn.microsoft.com/en-us/azure/azure-arc/overview)
 - [Microsoft Sentinel](https://learn.microsoft.com/en-gb/azure/sentinel/overview)

## Let's get started!
We will start with configuring single sign on into Imbroglio's AWS environment. *(Sometimes the hack will use GCP, but you'll be told beforehand.)*
