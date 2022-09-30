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
 - [It depends](https://learn.microsoft.com/en-us/azure/defender-for-cloud/permissions#roles-and-allowed-actions), but for the purposes of this lab, Owner to the subscription being used will be make things simpler.
### AWS Permissions
 - Administrator on the AWS account being used
### GCP Permissions
 - Owner on the GCP organization or project being used

## Services
You will have to ensure you have enabled the following services, trial or otherwise.
 - [Defender for Cloud Enhanced Security Features](https://learn.microsoft.com/en-us/azure/defender-for-cloud/enable-enhanced-security)
 - [Entra Permissions Management](https://learn.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/onboard-enable-tenant)
 - [Azure AD P2](https://learn.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-get-started-premium)

## Checks
