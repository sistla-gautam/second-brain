discussed with shubam regarding enabling of oauth 2 and SSO login in Appsmith application

---
- either oauth2 is not implemented properly, or, they are not using oauth in the way we think it as. the API calls do not contain the JWT at all. the header requests do not contain any field for accepting the jwt itself
- there should be some config where the APIs are filtered. some are secured and require some authentication, where as some dont. we need to find that filter
- if the github and google oauth is being used, then we need to find where it is getting used. We tried searching for it, but we couldnt find out anything as to where it is getting used
- if oauth is not being used, then we need to implement the oauth using the dependencies and stuff in our server
