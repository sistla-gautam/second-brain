### finding the list of all the files
- the SVG files are in the specific folder
- use this to find the list of all the given files that are in the SVG folder

#### curl command
> has a dependency on the token
```bash
curl 'https://api.dev.apps.yokogawa.build/vis-file-svc/v1/resource/' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6ImRlOTc4OGVjLWJmMWQtNGMzMy1iMTEyLTgyMDk5Njc5MGY3YiJ9.eyJ0ZW5hbnQiOiJkZTk3ODhlYy1iZjFkLTRjMzMtYjExMi04MjA5OTY3OTBmN2IiLCJsaWNlbnNlcyI6WyJyYmFjIiwidHNhbmFseXRpY3MiXSwiZXhwIjoxNzQ0OTEzMDEwLCJkb21haW4iOiJ5ZHguZGV2LmFwcHMueW9rb2dhd2EuYnVpbGQiLCJncm91cHMiOltdLCJwZXJtaXNzaW9ucyI6WyJhcmNoaXZhbDphbGw6cmQiLCJidWNrZXRzOmFsbDpjcnVkIiwiZW5yb2xsbWVudDphbGw6Y3J1ZCIsInJkYm1zOmFsbDpjcnVkIiwiZmlsZTphbGw6Y3J1ZCIsImJ1Y2tldG9iamVjdDphbGw6Y3J1ZCIsInVzZXJpbmZvOmFsbDpydSIsImF1ZGl0aW5mbzphbGw6ciIsImNvbGxlY3RvcjphbGw6Y3IiLCJuaWZpcGVybWlzc2lvbjphbGw6Y3J1ZCIsImRldmljZWNvbm5lY3Rpb246YWxsOnIiLCJlbWFpbDphbGw6YyIsImNtczphbGw6Y3J1ZCIsImxvZ2Rhc2hib2FyZDphbGw6Y3IiLCJleHBvcnRpbXBvcnQ6YWxsOnIiLCJ5ZHgycGk6YWxsOmNyIiwidmlzc3ZjOmFsbDpjcnVkIiwib3ZlcnRoZWFpcnVwZGF0ZTphbGw6YyIsImZlYXR1cmVzOmFsbDpjcnVkIiwic2NhbjphbGw6Y3IiLCJlc29zOmFsbDpjcnVkIiwidW5pdGNvbnZlcnNpb246YWxsOmNyIiwib3BjdWE6YWxsOmNydWQiLCJhbGFybXM6bWU6Y3J1ZCIsImFsYXJtczphbGw6Y3J1ZCIsImJpbGxpbmc6YWxsOmNydWQiLCJiaWxsaW5nOm1lOmNydWQiLCJleHBvcnQ6bWU6Y3J1ZCIsImV4cG9ydDphbGw6Y3J1ZCIsImpvYnM6bWU6Y3J1ZCIsImpvYnM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6bWU6Y3J1ZCIsIm1pZ3JhdGlvbjptZTpjcnVkIiwibWlncmF0aW9uOmFsbDpjcnVkIiwicGx1Z3M6YWxsOmNydWQiLCJwbHVnczptZTpjcnVkIiwicmVzb3VyY2VzOm1lOmNydWQiLCJyZXNvdXJjZXM6YWxsOmNydWQiLCJzZXR0aW5nczptZTpjcnVkIiwic2V0dGluZ3M6YWxsOmNydWQiLCJ0YXNrczptZTpjcnVkIiwidGFza3M6YWxsOmNydWQiLCJ0ZW1wbGF0ZXM6bWU6Y3J1ZCIsInRlbXBsYXRlczphbGw6Y3J1ZCIsInRva2VuczptZTpjcnVkIiwidG9rZW5zOmFsbDpjcnVkIiwidXNlcnM6YWxsOmNydWQiLCJyb2xlczphbGw6Y3J1ZCIsInZhdWx0OmFsbDpjcnVkIiwidmF1bHQ6bWU6Y3J1ZCIsImFwaWtleXM6YWxsOmNydWQiLCJhcGlrZXlzOm1lOmNydWQiLCJvcmdhbmlzYXRpb25zOmFsbDpjcnVkIiwib3JnYW5pc2F0aW9uczptZTpjcnVkIiwiYnlvbWw6bWU6Y3J1ZCIsImJ5b21sOmFsbDpjcnVkIiwicHVic3ViOmFsbDpjcnVkIl0sImlhdCI6MTc0NDg2OTgxMCwiaXNzIjoiQHdheWxheS9hdXRoIiwic3ViIjoidXNlcnMvNDBkMDJjYjYtN2IzNi00YzIxLTk5ZGUtYjQyMTUwZTY2YzI3In0.cqNwDokObN-YZIotzzfFeZv-2nvG1VgBw36gSwioQyXtcvpemayQ0F7SN328NkyccJqa7t131LlaDE3oAgG7g1hSo49l3M_iiSGXjICiMQjXtOgEwq4tJkeb6LX7gKk_AYaX0cxUkMNS5NbcxXhOlgnEWrUTZAUDW5K-z5hjKh3jx5RfPCvh4c1FpScYD7LX4hRpsecahtmmXbGSoCGKKC-uQ_chHZksr7AZPq2o2ZmkmHQVO9PV4ZM6u4LWvXBKufImVAqq1mzTeQqk-uWut3VooOIzDAfJelsVmA16T7YxoWL0ocyoLMEI-0YzH7sf6UGlBW8vXw_i8M4y5vEMnQ' \
  -H 'if-none-match: W/"61e3-sEK7m7XM4WcCEPCaBdS7ujdUeVc"' \
  -H 'origin: https://cloud.dev.apps.yokogawa.build' \
  -H 'priority: u=1, i' \
  -H 'sec-ch-ua: "Brave";v="135", "Not-A.Brand";v="8", "Chromium";v="135"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-site' \
  -H 'sec-gpc: 1' \
  -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36' \
  -H 'x-dt-domain: ydx.dev.apps.yokogawa.build' \
  -H 'x-dt-tenantid: de9788ec-bf1d-4c33-b112-820996790f7b' \
  -H 'x-dt-userid: users/40d02cb6-7b36-4c21-99de-b42150e66c27'
```

#### response

```JSON
[

    {

        "name": "01GR002-n9xMN3RBQs4kkBbxiHXF1M.svg",

        "lastModified": "2025-01-09T09:34:59.344Z",

        "versionId": "null",

        "isDeleteMarker": false,

        "isLatest": true,

        "fileType": "SVG"

    },

    {

        "name": "1random-svgrepo-com-pPtdF1uxMH5PngoZhUEoph-idCGs7DJGYiHtfG16ypw71.svg",

        "lastModified": "2025-01-09T09:34:59.376Z",

        "versionId": "null",

        "isDeleteMarker": false,

        "isLatest": true,

        "fileType": "SVG"

    },

    {

        "name": "2Sushma_Test_rectangle2-s17bFtmsNonvSbnn15Y1pb.svg",

        "lastModified": "2025-01-09T09:34:59.372Z",

        "versionId": "null",

        "isDeleteMarker": false,

        "isLatest": true,

        "fileType": "SVG"

    },
]
```

---

## List of all dashboards

## curl command

```bash
curl 'https://api.dev.apps.yokogawa.build/vis-file-svc/v1/dashboard/' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6ImRlOTc4OGVjLWJmMWQtNGMzMy1iMTEyLTgyMDk5Njc5MGY3YiJ9.eyJ0ZW5hbnQiOiJkZTk3ODhlYy1iZjFkLTRjMzMtYjExMi04MjA5OTY3OTBmN2IiLCJsaWNlbnNlcyI6WyJyYmFjIiwidHNhbmFseXRpY3MiXSwiZXhwIjoxNzQ0OTEzMDEwLCJkb21haW4iOiJ5ZHguZGV2LmFwcHMueW9rb2dhd2EuYnVpbGQiLCJncm91cHMiOltdLCJwZXJtaXNzaW9ucyI6WyJhcmNoaXZhbDphbGw6cmQiLCJidWNrZXRzOmFsbDpjcnVkIiwiZW5yb2xsbWVudDphbGw6Y3J1ZCIsInJkYm1zOmFsbDpjcnVkIiwiZmlsZTphbGw6Y3J1ZCIsImJ1Y2tldG9iamVjdDphbGw6Y3J1ZCIsInVzZXJpbmZvOmFsbDpydSIsImF1ZGl0aW5mbzphbGw6ciIsImNvbGxlY3RvcjphbGw6Y3IiLCJuaWZpcGVybWlzc2lvbjphbGw6Y3J1ZCIsImRldmljZWNvbm5lY3Rpb246YWxsOnIiLCJlbWFpbDphbGw6YyIsImNtczphbGw6Y3J1ZCIsImxvZ2Rhc2hib2FyZDphbGw6Y3IiLCJleHBvcnRpbXBvcnQ6YWxsOnIiLCJ5ZHgycGk6YWxsOmNyIiwidmlzc3ZjOmFsbDpjcnVkIiwib3ZlcnRoZWFpcnVwZGF0ZTphbGw6YyIsImZlYXR1cmVzOmFsbDpjcnVkIiwic2NhbjphbGw6Y3IiLCJlc29zOmFsbDpjcnVkIiwidW5pdGNvbnZlcnNpb246YWxsOmNyIiwib3BjdWE6YWxsOmNydWQiLCJhbGFybXM6bWU6Y3J1ZCIsImFsYXJtczphbGw6Y3J1ZCIsImJpbGxpbmc6YWxsOmNydWQiLCJiaWxsaW5nOm1lOmNydWQiLCJleHBvcnQ6bWU6Y3J1ZCIsImV4cG9ydDphbGw6Y3J1ZCIsImpvYnM6bWU6Y3J1ZCIsImpvYnM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6bWU6Y3J1ZCIsIm1pZ3JhdGlvbjptZTpjcnVkIiwibWlncmF0aW9uOmFsbDpjcnVkIiwicGx1Z3M6YWxsOmNydWQiLCJwbHVnczptZTpjcnVkIiwicmVzb3VyY2VzOm1lOmNydWQiLCJyZXNvdXJjZXM6YWxsOmNydWQiLCJzZXR0aW5nczptZTpjcnVkIiwic2V0dGluZ3M6YWxsOmNydWQiLCJ0YXNrczptZTpjcnVkIiwidGFza3M6YWxsOmNydWQiLCJ0ZW1wbGF0ZXM6bWU6Y3J1ZCIsInRlbXBsYXRlczphbGw6Y3J1ZCIsInRva2VuczptZTpjcnVkIiwidG9rZW5zOmFsbDpjcnVkIiwidXNlcnM6YWxsOmNydWQiLCJyb2xlczphbGw6Y3J1ZCIsInZhdWx0OmFsbDpjcnVkIiwidmF1bHQ6bWU6Y3J1ZCIsImFwaWtleXM6YWxsOmNydWQiLCJhcGlrZXlzOm1lOmNydWQiLCJvcmdhbmlzYXRpb25zOmFsbDpjcnVkIiwib3JnYW5pc2F0aW9uczptZTpjcnVkIiwiYnlvbWw6bWU6Y3J1ZCIsImJ5b21sOmFsbDpjcnVkIiwicHVic3ViOmFsbDpjcnVkIl0sImlhdCI6MTc0NDg2OTgxMCwiaXNzIjoiQHdheWxheS9hdXRoIiwic3ViIjoidXNlcnMvNDBkMDJjYjYtN2IzNi00YzIxLTk5ZGUtYjQyMTUwZTY2YzI3In0.cqNwDokObN-YZIotzzfFeZv-2nvG1VgBw36gSwioQyXtcvpemayQ0F7SN328NkyccJqa7t131LlaDE3oAgG7g1hSo49l3M_iiSGXjICiMQjXtOgEwq4tJkeb6LX7gKk_AYaX0cxUkMNS5NbcxXhOlgnEWrUTZAUDW5K-z5hjKh3jx5RfPCvh4c1FpScYD7LX4hRpsecahtmmXbGSoCGKKC-uQ_chHZksr7AZPq2o2ZmkmHQVO9PV4ZM6u4LWvXBKufImVAqq1mzTeQqk-uWut3VooOIzDAfJelsVmA16T7YxoWL0ocyoLMEI-0YzH7sf6UGlBW8vXw_i8M4y5vEMnQ' \
  -H 'origin: https://cloud.dev.apps.yokogawa.build' \
  -H 'priority: u=1, i' \
  -H 'sec-ch-ua: "Brave";v="135", "Not-A.Brand";v="8", "Chromium";v="135"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-site' \
  -H 'sec-gpc: 1' \
  -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36' \
  -H 'x-dt-domain: ydx.dev.apps.yokogawa.build' \
  -H 'x-dt-tenantid: de9788ec-bf1d-4c33-b112-820996790f7b' \
  -H 'x-dt-userid: users/40d02cb6-7b36-4c21-99de-b42150e66c27'
```


## response
```bash
[
    {
        "name": "1.1",
        "filePath": "visualization_config/dashboards/1.1/1.1.json",
        "lastModified": "2024-12-16T05:13:52.857Z",
        "etag": "87b2a6c838742fb1ba221948a9080891",
        "isDeleteMarker": false,
        "isLatest": true,
        "fileType": "DASHBOARD"
    },
    {
        "name": "1Feb",
        "filePath": "visualization_config/dashboards/1Feb/1Feb.json",
        "lastModified": "2025-04-11T06:22:30.006Z",
        "etag": "eb8025d83a556fa998d65f1d2ff72ca7",
        "isDeleteMarker": false,
        "isLatest": true,
        "fileType": "DASHBOARD"
    },
    {
        "name": "1feb",
        "filePath": "visualization_config/dashboards/1feb/1feb.json",
        "lastModified": "2025-04-17T08:06:33.645Z",
        "etag": "e9f7f9e542e4cb027c2a723dfd607b8e",
        "isDeleteMarker": false,
        "isLatest": true,
        "fileType": "DASHBOARD"
    },
]
```


---

## Iterating through a dashboard dashboard
