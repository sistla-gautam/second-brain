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

