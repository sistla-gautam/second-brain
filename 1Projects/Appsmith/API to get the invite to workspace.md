# API to get the user roles
- this permission groups are string values that are set on the sever side
- these values need to be retrieved from the server using an API
- there are 3 different roles
	- administrator
	- developer
	- app viewer
- the API endpoint for calling these are at `/api/v1/workspaces/<workspace_id>/permissionGroups`
- sample curl command for the same
```curl
curl --location 'https://dev.appsmith.com//api/v1/workspaces/6718e2f75b99ed1fc50aa4f9/permissionGroups' \
--header 'accept: application/json, text/plain, */*' \
--header 'accept-language: en-US,en;q=0.9' \
--header 'cookie: SESSION=f8b6e43a-4c36-4c53-a5dd-9c65bf6fc45a' \
--header 'priority: u=1, i' \
--header 'sec-ch-ua: "Chromium";v="130", "Brave";v="130", "Not?A_Brand";v="99"' \
--header 'sec-ch-ua-mobile: ?0' \
--header 'sec-ch-ua-platform: "Windows"' \
--header 'sec-fetch-dest: empty' \
--header 'sec-fetch-mode: cors' \
--header 'sec-fetch-site: same-origin' \
--header 'sec-gpc: 1' \
--header 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36'
```

# API to invite them to the workspace
- this is done with a call to the `/api/v1/users/invite` API
- this API takes a payload which takes the following parameters 
	- permissionGroupId (String)
	- usernames (Array)
- the sample curl command for the same is
```curl
curl --location 'https://dev.appsmith.com/api/v1/users/invite' \
--header 'accept: application/json, text/plain, */*' \
--header 'accept-language: en-US,en;q=0.9' \
--header 'content-type: application/json' \
--header 'cookie: SESSION=f8b6e43a-4c36-4c53-a5dd-9c65bf6fc45a; mp_70b8ea94d623dd857fb555a76d11f944_mixpanel=%7B%22distinct_id%22%3A%20%22%24device%3A192b81de7ef584-0d55091e7754db-26011951-24af80-192b81de7ef584%22%2C%22%24device_id%22%3A%20%22192b81de7ef584-0d55091e7754db-26011951-24af80-192b81de7ef584%22%2C%22%24initial_referrer%22%3A%20%22%24direct%22%2C%22%24initial_referring_domain%22%3A%20%22%24direct%22%2C%22__mps%22%3A%20%7B%7D%2C%22__mpso%22%3A%20%7B%22%24initial_referrer%22%3A%20%22%24direct%22%2C%22%24initial_referring_domain%22%3A%20%22%24direct%22%7D%2C%22__mpus%22%3A%20%7B%7D%2C%22__mpa%22%3A%20%7B%7D%2C%22__mpu%22%3A%20%7B%7D%2C%22__mpr%22%3A%20%5B%5D%2C%22__mpap%22%3A%20%5B%5D%7D; ajs_anonymous_id=c8fabc31-566c-4e64-aa9d-498ee57eff9c; signals-sdk-user-id=2100e534-4ef9-42a8-a51b-e997cd65d088' \
--header 'origin: https://dev.appsmith.com' \
--header 'priority: u=1, i' \
--header 'referer: https://dev.appsmith.com/applications' \
--header 'sec-ch-ua: "Chromium";v="130", "Brave";v="130", "Not?A_Brand";v="99"' \
--header 'sec-ch-ua-mobile: ?0' \
--header 'sec-ch-ua-platform: "Windows"' \
--header 'sec-fetch-dest: empty' \
--header 'sec-fetch-mode: cors' \
--header 'sec-fetch-site: same-origin' \
--header 'sec-gpc: 1' \
--header 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36' \
--header 'x-requested-by: Appsmith' \
--data-raw '{"usernames":["developer@yti.com"],"permissionGroupId":"6710f74ff732a32fafec4284"}'
```