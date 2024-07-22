- the `/login` page does multiple API calls 
##### Work flow
- redirect to the SAPCDC login page
- asks the user to login
- once logged in, the sapcdc token is returned back
- this is in the URL as `code=...`
- this `code` is then passed another API to get the correct login token