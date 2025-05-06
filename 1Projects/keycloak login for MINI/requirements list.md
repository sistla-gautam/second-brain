## Appsmith
- will launch from engineering console
	- this will be WAYLAY login
- add a login for keycloak into interactive forms
	- need to support WAYLAY login also
- need to show a keycloak, WAYLAY as a button in the same way how we show the other SSO options
- keycloak and WAYLAY login interactive forms to be only available on MINI ENV
- the client ID and client secret are to be extracted from the secrets in a similar way as the SAPCDC login will be

## Sync Service
- need to make a separate endpoint for syncing users for different providers - SAPCDC, WAYLAY, keycloak (3 different endpoints)
- need to call users from both WAYLAY endpoint and from KEYCLOAK endpoints separately
- implement this sync service not only for MINI ENV, but for all ENVs
- keycloak does no have any type of roles and hence all are to be considered as admins
	- this can be hardcoded in a similar way to SAPCDC roles
- WAYLAY contains roles and will require to map them correspondingly to the roles of the interactive forms
	- ![[Pasted image 20250506110041.png]]
	- API keys administrator, Admin, organisation administrator - APPSMITH ADMIN
	- IP manager, operator, provisioner, QA - APPSMITH APPLICATION DEVELOPER
- WAYLAY and KEYCLOAK does not support retrieval of users from a specific time frame
	- will require to pull all the users from WAYLAY and KEYCLOAK and compare with users from interactive forms

---

