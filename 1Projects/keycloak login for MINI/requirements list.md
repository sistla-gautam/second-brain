## Appsmith
- add a login for keycloak into interactive forms
- need to show a keycloak as a button in the same way how we show the other SSO options
- interactive forms to be only available on MINI EVN
- the client ID and client secret are to be extracted from the secrets in a similar way as the SAPCDC login will be

## Sync Service
- need to make a separate endpoint for syncing users
- need to call users from both WAYLAY endpoint and from KEYCLOAK endpoints
- WAYLAY does no have any type of roles and hence all are to be considered as admins
- KEYCLOAK contains roles and will require to map them correspondingly to the roles of the interactive forms
- WAYLAY and KEYCLOAK does not support retrieval of users from a specific time frame
	- will require to pull all the users from WAYLAY and KEYCLOAK and compare with users from interactive forms