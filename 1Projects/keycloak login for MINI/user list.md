# waylay list
https://admin-janydx-minicloud.msa.apps.yokogawa.build/users

```
Username: ops@apps.yokogawa.com
Password: s2E^Hp6F15
```

called using the API
```curl
curl 'https://admin-api-janydx-minicloud.msa.apps.yokogawa.build/users' \
  -H 'Accept: application/json, text/plain, */*' \
  -H 'Accept-Language: en-US,en;q=0.8' \
  -H 'Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IjAwMDAwMDAwLTAwMDAtNDAwMC1hMDAwLTAwMDAwMDAwMDAwMiJ9.eyJ0ZW5hbnQiOiIwMDAwMDAwMC0wMDAwLTQwMDAtYTAwMC0wMDAwMDAwMDAwMDIiLCJsaWNlbnNlcyI6W10sImV4cCI6MTc0NTUzNjMzNCwiZG9tYWluIjoiamFueWR4LW1pbmljbG91ZC5tc2EuYXBwcy55b2tvZ2F3YS5idWlsZCIsImdyb3VwcyI6W10sInBlcm1pc3Npb25zIjpbImJ1Y2tldHM6bWU6Y3J1ZCIsImJ1Y2tldHM6YWxsOmNydWQiLCJzdWRvIl0sImlhdCI6MTc0NTQ5MzEzNCwiaXNzIjoiQHdheWxheS9hdXRoIiwic3ViIjoidXNlcnMvMmQyMWM5MGItYzk5Ny00OWY4LTkxOTUtN2IzZmM1MmNkYzVhIn0.JPErmNWeHwvRKZH1Jk5iUjnXLV7Yhhpu-NF4_w55y3BTnzdMTqV1yEdCocceNRBzUOjtBudFn1nC8PCU2PBDw06IPNtkl7UHJzZ4yLEPsq51ytN4b2Y0mTJpdGko3v2DwRMEAxp04Nrev475LAsgwsBquxb5Xe5QEEfEYKV7AKNoIJCk7A8y0vzs07QYVxHEYKwDoxc3UymAAmijhiyzrrEQhtRAmzm4h7AAbsvmP51b25kd_FEpZwC4eFk_dFWm8kQUMBuh0PgFAN_YWSlo8BQepnBelsy8P_HVbH3Piw36PAXJ4V1lr8tERyHIFfR1yP-nydSYOP98VPB0gGQSNA' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Origin: https://admin-janydx-minicloud.msa.apps.yokogawa.build' \
  -H 'Pragma: no-cache' \
  -H 'Referer: https://admin-janydx-minicloud.msa.apps.yokogawa.build/' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-site' \
  -H 'Sec-GPC: 1' \
  -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Brave";v="135", "Not-A.Brand";v="8", "Chromium";v="135"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"'
```

- dependent on the token
	- use the username and password to get the token to do the API call
	- or do a basic auth using the username and password

---

# portal endpoints
```curl
curl '[https://api.dev.apps.yokogawa.build/idpt-authz/auth/admin/realms/TDEC/admin-ui-brute-force-user?briefRepresentation=true&first=0&max=11](https://api.dev.apps.yokogawa.build/idpt-authz/auth/admin/realms/TDEC/admin-ui-brute-force-user?briefRepresentation=true&first=0&max=11)' \ -H 'accept: */*' \ -H 'accept-language: en-US,en;q=0.9' \ -H 'authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJPMnlubUYtM1FFSF9kR2dGN3JLdG12aTJnY0UzWjlTQThiNDZZbzFxdGowIn0.eyJleHAiOjE3NDU1Mjk0MTQsImlhdCI6MTc0NTQ5MzcxOCwiYXV0aF90aW1lIjoxNzQ1NDkzNDE0LCJqdGkiOiJlZTM4YTZjNi0zYzlkLTQ3ZTktOGNiZi0wMzg3OTg4NTJjODEiLCJpc3MiOiJodHRwczovL2FwaS5kZXYuYXBwcy55b2tvZ2F3YS5idWlsZC9pZHB0LWF1dGh6L2F1dGgvcmVhbG1zL21hc3RlciIsInN1YiI6IjkwYjYwNDhiLWQxNTEtNDQ4Mi05OTJjLTVlNzJkYzAyZWJhMyIsInR5cCI6IkJlYXJlciIsImF6cCI6InNlY3VyaXR5LWFkbWluLWNvbnNvbGUiLCJub25jZSI6IjY1YjIzMGQwLTQ5ODItNDAxMC04NjI4LTJjMzc5MzE3ZjdiMCIsInNlc3Npb25fc3RhdGUiOiI5OTRjZTg4YS0wYjcwLTQ5NmEtYjA2NS0wYTIwNTk1OThmMjQiLCJhY3IiOiIwIiwiYWxsb3dlZC1vcmlnaW5zIjpbImh0dHBzOi8vYXBpLmRldi5hcHBzLnlva29nYXdhLmJ1aWxkIl0sInNjb3BlIjoib3BlbmlkIGVtYWlsIHByb2ZpbGUiLCJzaWQiOiI5OTRjZTg4YS0wYjcwLTQ5NmEtYjA2NS0wYTIwNTk1OThmMjQiLCJlbWFpbF92ZXJpZmllZCI6ZmFsc2UsInByZWZlcnJlZF91c2VybmFtZSI6ImFkbWluIn0.eC0zEZMQmgwV8dcqCdaLEnymJTFQUC4cv21jTg_Dut75ZgG6NyIPDs34qq4jfC8qsclxeG71XOuk7KjJ8TiPJRRJ8wd_MZ_inobxbAsTyAG0MaahGL77AjlwFu7vxdCNtKwbTVaCwrgEnexehcGDRj6SKF8IXSFFZGKEyCnnptlnFGS6LWZXeRDcwSUHX4bxw9hJiUEbM4ZD8xhpJhIsYtPuH8TSr2OPg6Bc7xB9JrHigZIMnd3QDMB_iqeBgOdh1IfdPxKMwd_YOAvjN7WxjeVKKPzRcZ4VWVkqN49dB4lP0z726ZQuwlkJPMYY1oiPWDEz_uNaM99fTPwn_51_TQ' \ -b 'gig_bootstrap_4_j64tnG1hJXdBLoyoOkSzXA=_gigya_ver4' \ -H 'priority: u=1, i' \ -H 'referer: [https://api.dev.apps.yokogawa.build/idpt-authz/auth/admin/master/console/](https://api.dev.apps.yokogawa.build/idpt-authz/auth/admin/master/console/)' \ -H 'sec-ch-ua: "Brave";v="135", "Not-A.Brand";v="8", "Chromium";v="135"' \ -H 'sec-ch-ua-mobile: ?0' \ -H 'sec-ch-ua-platform: "Windows"' \ -H 'sec-fetch-dest: empty' \ -H 'sec-fetch-mode: cors' \ -H 'sec-fetch-site: same-origin' \ -H 'sec-gpc: 1' \ -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36'
```
- also has a dependency on token
	- use the username and password as a basic auth if possible