# Agenda for the Hack

## Day One
Baseline Azure setup + Defender for Cloud? *Or* Start straight with identity and get the foundational bits in place there, and have Session 2 call the same identities used in Session 1?

1. AWS
   - https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/aws/aws-azure-ad-security
   - [Multi-cloud security and identity with Azure and Amazon web services (AWS)](https://docs.microsoft.com/en-us/azure/architecture/aws-professional/security-identity)
   - [Tutorial: Azure AD SSO integration with AWS Single-Account Access](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/amazon-web-service-tutorial)
   - https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/aws/aws-azure-security-solutions
2. GCP
   - https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/google-apps-tutorial
 
3. General
   - SSO: cloud platforms + show MFA
   - SSO: VMs

*Does Defender for Cloud Apps fit best in this session?*

## Day Two
1. Defender for Cloud Basics
   - Overerview
   - Planning your Defender for Cloud Deployment

2. Defender for Cloud CSPM
   - Can we show SSO or AAD identity usage during setup here?
   - [Connect to AWS](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws)
   - [Connect to GCP](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-gcp) (perhaps just show one or the other in the hack as it will require a lot of effort. Or have as an extra option for those who want to do it?)
   - [Custom Standards and Assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/custom-assessments-and-standards-in-microsoft-defender-for-cloud/ba-p/3066575)
   - Setting up governance in Defender for Cloud

3. Azure Arc+Defender for Cloud
   - Azure Arc Basics
   - https://azurearcjumpstart.io/azure_arc_jumpstart/azure_arc_servers/day2/arc_defender/#connect-azure-arc-enabled-servers-to-microsoft-defender-for-cloud
   - Script to auto-onboard AWS servers into Azure Arc
4.  Defender for Cloud CWP
    - [Defender for Servers](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#prerequisites) Details are further down under the connector
      - [Microsoft Defender for Cloud PoC Series - Defender for Servers](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/microsoft-defender-for-cloud-poc-series-defender-for-servers/ba-p/2767508)
      - Find the server in the Security.microsoft.com portal
        - [Generate test alerts on server in MDE](https://docs.microsoft.com/en-us/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#send-a-test-alert)
        - [Alert validation in Microsoft Defender for Cloud-Create Sample alerts](https://docs.microsoft.com/en-us/azure/defender-for-cloud/alert-validation#generate-sample-security-alerts)
    - [YouTube Video - Demo Defender for Containers in a multi-cloud](https://www.youtube.com/watch?v=62_Cj6yseno)
    - [Enabling Defender for Containers - MS Docs Link](https://docs.microsoft.com/en-us/azure/defender-for-cloud/defender-for-containers-enable?tabs=aks-deploy-portal%2Ck8s-deploy-asc%2Ck8s-verify-asc%2Ck8s-remove-arc%2Caks-removeprofile-api&pivots=defender-for-container-eks)
    - [How Defender for Containers protects your clusters](https://guillaumeben.xyz/defender-containers.html)
    - Install Kubernetes Goat https://madhuakula.com/kubernetes-goat/docs/
    - Find the various alerts in the portal and discuss
      - [Container Security Mapping Dashboard](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/containers-security-mapping-dashboard/ba-p/3601580)

5. JIT with AWS
   - https://docs.microsoft.com/en-us/azure/defender-for-cloud/just-in-time-access-overview?tabs=defender-for-container-arch-eks#what-permissions-are-needed-to-configure-and-use-jit (unified AAD and MDfC)

## Day Three
1.  Entra Permissions Management (EPM)
    - https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-aws
    - https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-gcp
    - [Defender for Cloud Integration with EPM[(https://www.youtube.com/watch?v=dasixjOOldk)
      - [Permission Creep Index in MDfC](https://docs.microsoft.com/en-us/azure/defender-for-cloud/other-threat-protections#entra-permission-management-formerly-cloudknox)
 
2. Microsoft Sentinel?
   - Overview
   - Connecting up the various data sources used in the hack
   - AWS S3 Connector, too
   - Sample multi-cloud KQL queries

# Outstanding Questions and Decisions
 - Have each session switch between cloud providers? First one AWS, second GCP, etc.? Then have stretch goals to do activities in both 
 - Start straight with identity or talk about getting the basics of MDfC and AAD first before connecting up AWS and GCP for SSO?
 - Add automation with logic apps at the end of CWP session? *How do we automate in multi-cloud for EDR?*
 - Cover landing zones at all?
 - Defender for Cloud Apps? Requires additional licensing or special CDX tenant
 - Defender EASM? Wait for Defender for Cloud integration as it is in rapid development?
 - Cover Sentinel at all? Or just cover threat hunting using MDfC and KQL? Could also just use threat hunting in security.microsoft.com portal as Defender for Servers will be there.
 - Multi-cloud XDR? 
 - How to handle Entra Permissions Management and MD EASM trials in the hack? 

# Stetch goals
 - Same activities, but in GCP
 - Azure Lighthouse? Might be too much for this, so just have  some knowledge point about it
 - Automation with Azure automation? for deployng Defender for servers?
 - Defender for SQL
   - Microsoft Defender for Cloud PoC Series - Microsoft Defender for SQL
 - Azure Key Vault + Azure Arc with non-Azure servers

 # Technical Requirements
  - Azure Tenant
    - Any basic Azure setup we should require?
  - AWS Tenant (and GCP for stretch goal)
  - MDfC Workload Protection / enhanced security enabled, Trial at a minimum
  - Entra Permissions Management or Trial
  - MD EASM or Trial

 # Skill Requirements
  - Familiarity with Defender for Cloud

# TODO
 - Find a script to 'generate sample findings' for MDfC?
 - Check activities to borrow / use from other content:
   - Azure Security management deep dive
   - Days of the Defenders?
   - Multi Cloud/Hybrid Cloud Security sales workshop
   - Defender for Cloud Usage Workshop
 - Advertise for Hack v-team members once the basics are done and a skeleton supporting deck is also done
