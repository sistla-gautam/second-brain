### Tenant info
- single tenant
	- optional
- URL - tenant name will be part of the URL

## user flow
###### creation of new tenant
- logs in with a form user as the tenant admin
- once logged in, the user will then be directed to a workspace
- this workspace will contain a default application
- the username and password used to log in, needs to be stored in the vault
- these values will be used by sync service

#### updating (new) users to tenant (workspace)
- once a new user is allowed access to appsmith for that tenant, then sync service will invite them to the required workspace
- once the user is invited, the user will be given different type of access based on the permissions in SAPCDC
- similar approach is used for update and remove operations

## SSO login
- integrated SAPCDC SSO login
- all users will be logging in with SSO login
- based on the role provided in SAPCDC, the roles in appsmith will be assigned

## creation of workspaces
- one workspace is created per tenant. this workspace will be used only for that tenant
- every user who has access to the tenant, will be invited to the workspace from sync service
- every user can be part of multiple workspaces, if they have access to different tenants from SAPCDC