### list of users
- `https://dev.appsmith.com/api/v1/workspaces/<workspace_id>/members`
- requires a cookie called `SESSION` to call the API

**curl command**
```curl
curl 'https://dev.appsmith.com/api/v1/workspaces/672dc3714b27066d6482dac9/members' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'cookie: SESSION=21d57027-4474-4678-b772-62b3943e2a01' \
  -H 'priority: u=1, i' \
  -H 'referer: https://dev.appsmith.com/applications' \
  -H 'sec-ch-ua: "Google Chrome";v="131", "Chromium";v="131", "Not_A Brand";v="24"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-origin' \
  -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36' \
  --insecure
```

**response**
```JSON
{
    "responseMeta": {
        "status": 200,
        "success": true
    },
    "data": [
        {
            "userId": "672dc3714b27066d6482dac6",
            "username": "602a144d2ae243efad91a525eba38813",
            "name": "602a144d2ae243efad91a525eba38813",
            "roles": [
                {
                    "id": "672dc3714b27066d6482daca",
                    "name": "Administrator - 602a144d2ae243efad91a525eba38813's apps",
                    "description": "Can modify all workspace settings including editing applications, inviting other users to the workspace and exporting applications from the workspace",
                    "entityType": "Workspace"
                }
            ]
        }
    ],
    "errorDisplay": ""
}
```
---
### adding users to a workspace
- 