# Agenda for the Hack

## Day One
Baseline Azure setup + Defender for Cloud? *Or* Start straight with identity and get the foundational bits in place there, and have Session 2 call the same identities used in Session 1?

AWS
 - https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/aws/aws-azure-ad-security
 - https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/aws/aws-azure-security-solutions
 -
GCP
 - https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/google-apps-tutorial
 
General
 - SSO: cloud platforms + show MFA
 - SSO: VMs

Does Defender for Cloud Apps fit best in this session?

## Day Two
Defender for Cloud Basics

Defender for Cloud CSPM
 - Can we show SSO or AAD identity usage during setup here?
 - [Connect to AWS](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws)
 - [Connect to GCP](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-gcp) (perhaps just show one or the other in the hack as it will require a lot of effort. Or have as an extra option for those who want to do it?)
 - [Custom Standards and Assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/custom-assessments-and-standards-in-microsoft-defender-for-cloud/ba-p/3066575)

Azure Arc+Defender for Cloud
 - https://azurearcjumpstart.io/azure_arc_jumpstart/azure_arc_servers/day2/arc_defender/#connect-azure-arc-enabled-servers-to-microsoft-defender-for-cloud

Defender for Cloud CWP
 - [Defender for Servers](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#prerequisites) Details are further down under the connector
 - https://www.youtube.com/watch?v=62_Cj6yseno
 - [Defender for Containers](https://docs.microsoft.com/en-us/azure/defender-for-cloud/defender-for-containers-enable?tabs=aks-deploy-portal%2Ck8s-deploy-asc%2Ck8s-verify-asc%2Ck8s-remove-arc%2Caks-removeprofile-api&pivots=defender-for-container-eks)
 - Find the server in the Security.microsoft.com portal

JIT with AWS
 - https://docs.microsoft.com/en-us/azure/defender-for-cloud/just-in-time-access-overview?tabs=defender-for-container-arch-eks#what-permissions-are-needed-to-configure-and-use-jit (unified AAD and MDfC)

+Azure Lighthouse https://azurearcjumpstart.io/azure_arc_jumpstart/azure_arc_servers/day2/arc_defender/#connect-azure-arc-enabled-servers-to-microsoft-defender-for-cloud? Might be too much for this, so just have  some knowledge point about it

## Day Three
Entra Permissions Management
 - https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-aws
 - https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-gcp
 - Permission Creep Index in MDfC
 
Microsoft Sentinel
 - Overview
 - Connecting up the various data sources used in the hack
 - 

# Outstanding Questions and Decisions
 - Start straight with identity or talk about getting the basics of MDfC and AAD first before connecting up AWS and GCP for SSO?
 - Cover landing zones at all?
 - Defender for Cloud Apps? Requires additional licensing
 - Defender EASM? Wait for Defender for Cloud integration as it is in rapid development?
 - Cover Sentinel at all? Or just cover threat hunting using MDfC and KQL? Could also just use threat hunting in security.microsoft.com portal as Defender for Servers will be there.
