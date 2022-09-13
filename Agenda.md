# Agenda for the Hack

## Session one: Using Azure AD in multi-cloud environments
1. Azure Active Directory (AAD)
   - Overview
   - Preparing your AAD tenant
2. Amazon Web Services (AWS)
   - [Deploying Microsoft security solutions in AWS](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/aws/aws-azure-security-solutions)
   - [AAD IAM for AWS](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/aws/aws-azure-ad-security)
   - [Multi-cloud security and identity with Azure and Amazon web services (AWS)](https://docs.microsoft.com/en-us/azure/architecture/aws-professional/security-identity)
   - [Tutorial: Azure AD SSO integration with AWS Single-Account Access](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/amazon-web-service-tutorial)

3. Google Cloud Platform (GCP)
   - [Tutorial: AAD SSO Integration with GCP/G Suite](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/google-apps-tutorial)
 
4. General
   - SSO: cloud platforms + show MFA
   - SSO: VMs

## Session Two: Azure Arc and Microsoft Defender for Cloud
1. Defender for Cloud Basics
   - Overview
   - [Planning your Defender for Cloud Deployment](https://docs.microsoft.com/en-us/azure/defender-for-cloud/security-center-planning-and-operations-guide)
   - Enable and Configure Defender for Cloud (Initial Environment settings blade in Azure)

2. Defender for Cloud CSPM
   - Azure AD SSO during connector setup
   - [Connect to AWS](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-aws)
   - [Connect to GCP](https://docs.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-gcp) (perhaps just show one or the other in the hack as it will require a lot of effort. Or have as an extra option for those who want to do it?)
   - [Custom Standards and Assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/custom-assessments-and-standards-in-microsoft-defender-for-cloud/ba-p/3066575)
   - [Setting up governance in Defender for Cloud](https://docs.microsoft.com/en-us/azure/defender-for-cloud/governance-rules)

3. Azure Arc+Defender for Cloud
   - Azure Arc Basics
   - Connect Azure Arc-enabled Servers to Microsoft Defender for Cloud
     - [Via auto-enrolment in MDfC](https://docs.microsoft.com/en-gb/azure/defender-for-cloud/enable-data-collection?WT.mc_id=Portal-Microsoft_Azure_Security&tabs=autoprovision-feature)
     - [Azure Arc Jumpstart Method](https://azurearcjumpstart.io/azure_arc_jumpstart/azure_arc_servers/day2/arc_defender/#connect-azure-arc-enabled-servers-to-microsoft-defender-for-cloud)
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
    - [Install Kubernetes Goat](https://madhuakula.com/kubernetes-goat/docs/)
    - Find the various alerts in the portal and discuss
      - [Container Security Mapping Dashboard](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/containers-security-mapping-dashboard/ba-p/3601580)

5. JIT with AWS
   - [How to configure and use JIT with AWS](https://docs.microsoft.com/en-us/azure/defender-for-cloud/just-in-time-access-overview?tabs=defender-for-container-arch-eks#what-permissions-are-needed-to-configure-and-use-jit) (unifies AAD and MDfC topics)

## Session Three: Entra Permissions Management and Microsoft Sentinel
1.  Entra Permissions Management (EPM)
    - [Onboarding AWS into EPM](https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-aws)
    - [Onboarding GCP into EPM](https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-gcp)
    - [Defender for Cloud Integration with EPM](https://www.youtube.com/watch?v=dasixjOOldk)
      - [Permission Creep Index in MDfC](https://docs.microsoft.com/en-us/azure/defender-for-cloud/other-threat-protections#entra-permission-management-formerly-cloudknox)
 
2. Microsoft Sentinel
   - Overview
   - Connecting up the various data sources used in the hack
     - [Microsoft Defender for Cloud](https://docs.microsoft.com/en-us/azure/sentinel/connect-defender-for-cloud)
     - [Azure AD](https://docs.microsoft.com/en-us/azure/sentinel/connect-azure-active-directory)
   - [AWS S3 Connector](https://docs.microsoft.com/en-us/azure/sentinel/connect-aws?tabs=s3), too
   - Sample multi-cloud KQL queries

# Outstanding Questions and Decisions
 - Have each session switch between cloud providers? First one AWS, second GCP, etc.? Then have stretch goals to do activities in both 
 - Add automation with logic apps at the end of CWP session? *How do we automate in multi-cloud for EDR?*
 - Cover landing zones at all?
 - Defender for Cloud Apps? Requires additional licensing or special CDX tenant
 - How to handle Entra Permissions Management trial in the hack? 

# Stetch goals
 - Same activities, but in GCP
 - Azure Lighthouse? Might be too much for this, so just have  some knowledge point about it
 - Automation with Azure automation? for deployng Defender for servers?
 - Defender for SQL
   - Microsoft Defender for Cloud PoC Series - Microsoft Defender for SQL
 - Azure Key Vault + Azure Arc with non-Azure servers

 # Technical Requirements / Pre-requisites
  - Azure Tenant
    - AAD P2 / M365 E5 or Trial
  - AWS Tenant *(and GCP for stretch goal)*
  - MDfC Workload Protection / enhanced security enabled, Trial at a minimum
  - Entra Permissions Management or Trial
  - *Once there is MDfC Integration: MD EASM or Trial*
  - Mobile phone with Microsoft Authenticator App

 # Skill Requirements
  - Familiar with Defender for Cloud
  - Comfortable with command line interface
  - Familiar with the Azure Portal

# TODO
 - ~~Find a script to 'generate sample findings' for MDfC~~Found and Agenda has links
 - Check activities to borrow / use from other content:
   - ~~Azure Security management deep dive~~ Day 2 has some slides worth borrowing
   - ~~Days of the Defenders~~
   - Multi Cloud/Hybrid Cloud Security sales workshop
   - Defender for Cloud Usage Workshop
 - Advertise for Hack v-team members once the basics are done and a skeleton supporting deck is also done

# Future Content / Topics
 - Defender EASM once there is MDfC integration
