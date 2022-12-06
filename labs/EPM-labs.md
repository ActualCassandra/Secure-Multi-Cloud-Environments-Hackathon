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
```Auth System Type: AWS
Auth System: all (or choose a specific one), 
Search For: user, group, or role
User Status: Active,
PCI: i.e. High, 
Task Usage: Any
```
> Click Apply
2. Select identity
3. Select Detach Policies
4. Select policies from Available Policies
5. Submit


## Procedure: Assign Read-Only Status
### Azure and GCP
*For user, group, application, managed identity*

This will remove the directly assigned roles from the identity in the Azure/GCP portal immediately.  The change will be reflected by EPM within 4 hours, unless you trigger the data collection sooner.
1. Navigate to Remediation > Permissions > Filter by:
```
Auth System Type: Azure or GCP
Auth System: all, 
Search For: user, group, application, managed identity
User Status: Active,
PCI: High, 
Task Usage: Any
```
> Click Apply
2. Select identity
3. Select the directly assigned role/s 
4. Select Assign Read-Only Status
5. Select Execute

### AWS
*For user, group, role*

This will remove the policies from the identity in the AWS portal immediately.  The change will be reflected by EPM within 4 hours, unless you trigger the data collection sooner.
1. Navigate to Remediation > Permissions > Filter by:
```
Auth System Type: AWS
Auth System: all, 
Search For: user, group, role
User Status: Active,
PCI: High, 
Task Usage: Any
```
> Click Apply
2. Select identity
3. Select Detach Policies
4. Select policies from Available Policies
5. Submit

## Procedure: How to use Permissions On Demand
### Azure and GCP
*For users and managed identities*

This will provide Just In Time access for the requested identity to have the selected permissions.  The permissions will be automatically removed as soon as the time duration has elapsed.

1. Navigate to Remediation > My Requests > New Request
2. Select the Auth System Type and the Auth System. Only Auth Systems with the controller enabled will be available to select. 
3. Select the identity that the request is for. Identities available to submit requests on behalf of can be managed under in the user management section.
4. Select the scope
5. Select the Role, Task or Template for the request
6. Click Next *(top of screen will then show 2 confirmation)*
7. Enter the request summary
8. Schedule the frequency and duration the permissions should be available for. Click Schedule
9. Review the Selected Roles and Selected Scope
10. Click Submit

### AWS
*For users and managed identities*

This will provide Just In Time access for the requested identity to have the selected permissions.  The permissions will be automatically removed as soon as the time duration has elapsed.

1. Navigate to Remediation > My Requests > New Request
2. Select the Auth System Type and the Auth System. Only Auth Systems with the controller enabled will be available to select. 
3. Select the identity that the request is for. Identities available to submit requests on behalf of can be managed under in the user management section.
4. Select the Role. Review the Role Summary by clicking on the eye symbol next to the role.
5. Select the Policy, Task or Template for the request
6.  Click Next *(top of screen will then show 2 confirmation)*
7. *If Policy was selected: skip to step 9*
8. If Task was selected: Select the Scope, add any Request Conditions, and the Effect to allow or deny. Click Next
9. Enter the request summary
10. Schedule the frequency and duration the permissions should be available for. Click Schedule
11. Review the Selected Policies or Tasks
12. Click Submit

## Procedure: Set up Alerts
