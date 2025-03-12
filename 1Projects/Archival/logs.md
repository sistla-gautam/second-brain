### time series data

```
curl ^"https://api.dev.apps.yokogawa.build/queries/v1/data^" ^
  -H ^"accept: application/json, text/plain, */*^" ^
  -H ^"accept-language: en-US,en;q=0.5^" ^
  -H ^"authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6ImRlOTc4OGVjLWJmMWQtNGMzMy1iMTEyLTgyMDk5Njc5MGY3YiJ9.eyJ0ZW5hbnQiOiJkZTk3ODhlYy1iZjFkLTRjMzMtYjExMi04MjA5OTY3OTBmN2IiLCJsaWNlbnNlcyI6WyJyYmFjIiwidHNhbmFseXRpY3MiXSwiZXhwIjoxNzQxODAwNDk2LCJkb21haW4iOiJ5ZHguZGV2LmFwcHMueW9rb2dhd2EuYnVpbGQiLCJncm91cHMiOltdLCJwZXJtaXNzaW9ucyI6WyJhcmNoaXZhbDphbGw6cmQiLCJidWNrZXRzOmFsbDpjcnVkIiwiZW5yb2xsbWVudDphbGw6Y3J1ZCIsInJkYm1zOmFsbDpjcnVkIiwiZmlsZTphbGw6Y3J1ZCIsImJ1Y2tldG9iamVjdDphbGw6Y3J1ZCIsInVzZXJpbmZvOmFsbDpydSIsImF1ZGl0aW5mbzphbGw6ciIsImNvbGxlY3RvcjphbGw6Y3IiLCJuaWZpcGVybWlzc2lvbjphbGw6Y3J1ZCIsImRldmljZWNvbm5lY3Rpb246YWxsOnIiLCJlbWFpbDphbGw6YyIsImNtczphbGw6Y3J1ZCIsImxvZ2Rhc2hib2FyZDphbGw6Y3IiLCJleHBvcnRpbXBvcnQ6YWxsOnIiLCJ5ZHgycGk6YWxsOmNyIiwidmlzc3ZjOmFsbDpjcnVkIiwib3ZlcnRoZWFpcnVwZGF0ZTphbGw6YyIsImZlYXR1cmVzOmFsbDpjcnVkIiwic2NhbjphbGw6Y3IiLCJlc29zOmFsbDpjcnVkIiwidW5pdGNvbnZlcnNpb246YWxsOmNyIiwib3BjdWE6YWxsOmNydWQiLCJhbGFybXM6bWU6Y3J1ZCIsImFsYXJtczphbGw6Y3J1ZCIsImJpbGxpbmc6YWxsOmNydWQiLCJiaWxsaW5nOm1lOmNydWQiLCJleHBvcnQ6bWU6Y3J1ZCIsImV4cG9ydDphbGw6Y3J1ZCIsImpvYnM6bWU6Y3J1ZCIsImpvYnM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6bWU6Y3J1ZCIsIm1pZ3JhdGlvbjptZTpjcnVkIiwibWlncmF0aW9uOmFsbDpjcnVkIiwicGx1Z3M6YWxsOmNydWQiLCJwbHVnczptZTpjcnVkIiwicmVzb3VyY2VzOm1lOmNydWQiLCJyZXNvdXJjZXM6YWxsOmNydWQiLCJzZXR0aW5nczptZTpjcnVkIiwic2V0dGluZ3M6YWxsOmNydWQiLCJ0YXNrczptZTpjcnVkIiwidGFza3M6YWxsOmNydWQiLCJ0ZW1wbGF0ZXM6bWU6Y3J1ZCIsInRlbXBsYXRlczphbGw6Y3J1ZCIsInRva2VuczptZTpjcnVkIiwidG9rZW5zOmFsbDpjcnVkIiwidXNlcnM6YWxsOmNydWQiLCJyb2xlczphbGw6Y3J1ZCIsInZhdWx0OmFsbDpjcnVkIiwidmF1bHQ6bWU6Y3J1ZCIsImFwaWtleXM6YWxsOmNydWQiLCJhcGlrZXlzOm1lOmNydWQiLCJvcmdhbmlzYXRpb25zOmFsbDpjcnVkIiwib3JnYW5pc2F0aW9uczptZTpjcnVkIiwiYnlvbWw6bWU6Y3J1ZCIsImJ5b21sOmFsbDpjcnVkIiwicHVic3ViOmFsbDpjcnVkIl0sImlhdCI6MTc0MTc1NzI5NiwiaXNzIjoiQHdheWxheS9hdXRoIiwic3ViIjoidXNlcnMvNDBkMDJjYjYtN2IzNi00YzIxLTk5ZGUtYjQyMTUwZTY2YzI3In0.b-Hq8rafy4RQiXB2s3QMFBB8eTt1OEqaxoXNm1bw4IpX6Smea-MOvL9QtG61KL4gu3R-TFfg5IPHN1zpcRILvFZxtCgvODZpj3jbLozDLcAhee7w9WzNNoSF6bkkMIUHOk6lW_MaveEOox7JnLWOhLN_cajPwqx6SibUFe0f57PS-Eo3gu_Pw8RMibB-QHn6kBASY7qoIBlhENc4MaljB8FKpBEH__dL4xXNRH4v99ZYprUDdr9D7CqMeV28-KOSzi360MA41oOhACy3c7v6RZ8Yr0tQtdN_LUJugdc4nJtjx7K4cBwDkk4gI_lPKoW55xlqBrOg6gUPqoI2--F5fg^" ^
  -H ^"content-type: application/json^" ^
  -H ^"origin: http://127.0.0.1:5500^" ^
  -H ^"priority: u=1, i^" ^
  -H ^"referer: http://127.0.0.1:5500/^" ^
  -H ^"sec-ch-ua: ^\^"Chromium^\^";v=^\^"134^\^", ^\^"Not:A-Brand^\^";v=^\^"24^\^", ^\^"Brave^\^";v=^\^"134^\^"^" ^
  -H ^"sec-ch-ua-mobile: ?0^" ^
  -H ^"sec-ch-ua-platform: ^\^"Windows^\^"^" ^
  -H ^"sec-fetch-dest: empty^" ^
  -H ^"sec-fetch-mode: cors^" ^
  -H ^"sec-fetch-site: cross-site^" ^
  -H ^"sec-gpc: 1^" ^
  -H ^"user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36^" ^
  --data-raw ^"^{^\^"data^\^":^[^{^\^"resource^\^":^\^"4cb23498-f8c1-4e0e-b89a-e7632a58d59f^\^",^\^"metric^\^":^\^"Temperature^\^"^}^],^\^"aggregates^\^":^[^\^"mean^\^"^],^\^"until^\^":1740637800000,^\^"from^\^":1730442600000,^\^"freq^\^":^\^"PT1700M^\^"^}^"
```


##### body

```
{
    "data": [
        {
            "resource": "4cb23498-f8c1-4e0e-b89a-e7632a58d59f",
            "metric": "Temperature"
        }
    ],
    "aggregates": [
        "mean"
    ],
    "until": 1740637800000,
    "from": 1730442600000,
    "freq": "PT1700M"
}
```
---

# archival

### curl
```
curl --location 'https://api.dev.apps.yokogawa.build/archival/v1/series/sensor_3-8ef741c4-1a40-46d8-8fb7-c2795bed0fe9/temperature?from=888883275000&until=888883335000&limit=10&order=ascending' \
--header 'Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6ImRlOTc4OGVjLWJmMWQtNGMzMy1iMTEyLTgyMDk5Njc5MGY3YiJ9.eyJ0ZW5hbnQiOiJkZTk3ODhlYy1iZjFkLTRjMzMtYjExMi04MjA5OTY3OTBmN2IiLCJsaWNlbnNlcyI6WyJyYmFjIiwidHNhbmFseXRpY3MiXSwiZXhwIjoxNzQxODAwNDk2LCJkb21haW4iOiJ5ZHguZGV2LmFwcHMueW9rb2dhd2EuYnVpbGQiLCJncm91cHMiOltdLCJwZXJtaXNzaW9ucyI6WyJhcmNoaXZhbDphbGw6cmQiLCJidWNrZXRzOmFsbDpjcnVkIiwiZW5yb2xsbWVudDphbGw6Y3J1ZCIsInJkYm1zOmFsbDpjcnVkIiwiZmlsZTphbGw6Y3J1ZCIsImJ1Y2tldG9iamVjdDphbGw6Y3J1ZCIsInVzZXJpbmZvOmFsbDpydSIsImF1ZGl0aW5mbzphbGw6ciIsImNvbGxlY3RvcjphbGw6Y3IiLCJuaWZpcGVybWlzc2lvbjphbGw6Y3J1ZCIsImRldmljZWNvbm5lY3Rpb246YWxsOnIiLCJlbWFpbDphbGw6YyIsImNtczphbGw6Y3J1ZCIsImxvZ2Rhc2hib2FyZDphbGw6Y3IiLCJleHBvcnRpbXBvcnQ6YWxsOnIiLCJ5ZHgycGk6YWxsOmNyIiwidmlzc3ZjOmFsbDpjcnVkIiwib3ZlcnRoZWFpcnVwZGF0ZTphbGw6YyIsImZlYXR1cmVzOmFsbDpjcnVkIiwic2NhbjphbGw6Y3IiLCJlc29zOmFsbDpjcnVkIiwidW5pdGNvbnZlcnNpb246YWxsOmNyIiwib3BjdWE6YWxsOmNydWQiLCJhbGFybXM6bWU6Y3J1ZCIsImFsYXJtczphbGw6Y3J1ZCIsImJpbGxpbmc6YWxsOmNydWQiLCJiaWxsaW5nOm1lOmNydWQiLCJleHBvcnQ6bWU6Y3J1ZCIsImV4cG9ydDphbGw6Y3J1ZCIsImpvYnM6bWU6Y3J1ZCIsImpvYnM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6YWxsOmNydWQiLCJtZWFzdXJlbWVudHM6bWU6Y3J1ZCIsIm1pZ3JhdGlvbjptZTpjcnVkIiwibWlncmF0aW9uOmFsbDpjcnVkIiwicGx1Z3M6YWxsOmNydWQiLCJwbHVnczptZTpjcnVkIiwicmVzb3VyY2VzOm1lOmNydWQiLCJyZXNvdXJjZXM6YWxsOmNydWQiLCJzZXR0aW5nczptZTpjcnVkIiwic2V0dGluZ3M6YWxsOmNydWQiLCJ0YXNrczptZTpjcnVkIiwidGFza3M6YWxsOmNydWQiLCJ0ZW1wbGF0ZXM6bWU6Y3J1ZCIsInRlbXBsYXRlczphbGw6Y3J1ZCIsInRva2VuczptZTpjcnVkIiwidG9rZW5zOmFsbDpjcnVkIiwidXNlcnM6YWxsOmNydWQiLCJyb2xlczphbGw6Y3J1ZCIsInZhdWx0OmFsbDpjcnVkIiwidmF1bHQ6bWU6Y3J1ZCIsImFwaWtleXM6YWxsOmNydWQiLCJhcGlrZXlzOm1lOmNydWQiLCJvcmdhbmlzYXRpb25zOmFsbDpjcnVkIiwib3JnYW5pc2F0aW9uczptZTpjcnVkIiwiYnlvbWw6bWU6Y3J1ZCIsImJ5b21sOmFsbDpjcnVkIiwicHVic3ViOmFsbDpjcnVkIl0sImlhdCI6MTc0MTc1NzI5NiwiaXNzIjoiQHdheWxheS9hdXRoIiwic3ViIjoidXNlcnMvNDBkMDJjYjYtN2IzNi00YzIxLTk5ZGUtYjQyMTUwZTY2YzI3In0.b-Hq8rafy4RQiXB2s3QMFBB8eTt1OEqaxoXNm1bw4IpX6Smea-MOvL9QtG61KL4gu3R-TFfg5IPHN1zpcRILvFZxtCgvODZpj3jbLozDLcAhee7w9WzNNoSF6bkkMIUHOk6lW_MaveEOox7JnLWOhLN_cajPwqx6SibUFe0f57PS-Eo3gu_Pw8RMibB-QHn6kBASY7qoIBlhENc4MaljB8FKpBEH__dL4xXNRH4v99ZYprUDdr9D7CqMeV28-KOSzi360MA41oOhACy3c7v6RZ8Yr0tQtdN_LUJugdc4nJtjx7K4cBwDkk4gI_lPKoW55xlqBrOg6gUPqoI2--F5fg'
```

###### URL
```
https://api.dev.apps.yokogawa.build/archival/v1/series/sensor_3-8ef741c4-1a40-46d8-8fb7-c2795bed0fe9/temperature?from=888883275000&until=888883335000&limit=10&order=ascending
```