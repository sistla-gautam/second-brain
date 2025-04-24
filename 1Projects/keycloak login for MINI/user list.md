# waylay list
https://admin-janydx-minicloud.msa.apps.yokogawa.build/users

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