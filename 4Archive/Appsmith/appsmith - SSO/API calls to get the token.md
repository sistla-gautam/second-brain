- the `/login` page does multiple API calls 
##### Work flow
- SAPCDD token from YTI
- Jwt from a gigya url
- user info based on the JWT
- platform token from this user info

#### SAPCDC token
url: `config.authorizeUri`
- this is done once the user clicks on the login button
- will lead to YTI login page to get the user credentials
- will return the required SAPCDC token

#### JWT token
url: `config.tokenUri`
- pass the SAPCDC token as a param