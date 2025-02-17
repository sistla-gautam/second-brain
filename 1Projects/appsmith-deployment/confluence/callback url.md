- the `workspace.sh` file needs to be called with the following parameters
	- username - use the `APPSMITH_USERNAME` value from the sync service secrets
	- password - use the `APPSMITH_PASSWORD` value from the sync service secrets
	- tenant name - name of the tenant name to which interactive forms will be deployed
	- tenant-url - the base url  where the interactive forms is deployed
- the `TENANT_LIST` secret in sync service should also be updated with the new tenant and the tenant URL
	- the `TENANT_LIST` is an array of JSON object which contains the following structure
```
[ { "tenantname" : "tenant1", "URL" : "https://forms-tenant1.dev.apps.yokogawa.build/" }, { "tenantname" : "tenant2", "URL" : "https://forms-tenant2.dev.apps.yokogawa.build/" }]
```
- the new tenant name and the URL for the same needs to be updated into the array 