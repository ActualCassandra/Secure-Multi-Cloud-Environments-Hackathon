# Common Entra Permissions Management Procedures

## Procedure: Remove a role from an identity
### Azure and GCP
*For user, group, application, or managed identity.*

This will remove the role from the identity in the Azure/GCP portal immediately.  The change will be reflected by EPM within 4 hours, unless you trigger the data collection sooner.


1. Navigate to Remediation > Permissions > Filter by:
```Auth System Type: Azure or GCP
Auth System: all (or choose a specific one)
Search For: user, group, application, or managed identity
User Status: Active,
PCI: i.e. High, 
Task Usage: Any
```
> Click Apply

2. Select identity
3. Select the role/s that are to be removed
4. Select Remove Role
5. Select role from Available Roles
6. Submit

### AWS
*For user, group, or role.*

This will remove the role/policy from the identity in the AWS portal immediately.  The change will be reflected by EPM within 4 hours, unless you trigger the data collection sooner.


1. Navigate to Remediation > Permissions > Filter by:
Auth System Type: AWS
Auth System: all (or choose a specific one), 
Search For: user, group, or role
User Status: Active,
PCI: i.e. High, 
Task Usage: Any
> Click Apply
2. Select identity
3. Select Detach Policies
4. Select policies from Available Policies
5. Submit
