### renaming of workspace
```bash
curl 'https://forms.dev.apps.yokogawa.build/api/v1/workspaces/679b08b37e726d47b480d730' \
  -X 'PUT' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'content-type: application/json' \
  -H 'cookie: gig_bootstrap_4_j64tnG1hJXdBLoyoOkSzXA=_gigya_ver4; SESSION=3e150fca-cf8b-45b0-bf80-aeea16794bd3' \
  -H 'origin: https://forms.dev.apps.yokogawa.build' \
  -H 'priority: u=1, i' \
  -H 'referer: https://forms.dev.apps.yokogawa.build/applications' \
  -H 'sec-ch-ua: "Not A(Brand";v="8", "Chromium";v="132", "Google Chrome";v="132"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-origin' \
  -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/132.0.0.0 Safari/537.36' \
  -H 'x-requested-by: Appsmith' \
  --data-raw '{"id":"679b08b37e726d47b480d730","name":"new title"}'
```


### creating a new user
```bash
curl 'https://forms-alpha.dev.apps.yokogawa.build/api/v1/users' \
  -H 'accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'cache-control: max-age=0' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -H 'cookie: gig_bootstrap_4_j64tnG1hJXdBLoyoOkSzXA=_gigya_ver4' \
  -H 'origin: https://forms-alpha.dev.apps.yokogawa.build' \
  -H 'priority: u=0, i' \
  -H 'referer: https://forms-alpha.dev.apps.yokogawa.build/user/signup' \
  -H 'sec-ch-ua: "Not A(Brand";v="8", "Chromium";v="132", "Google Chrome";v="132"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  -H 'sec-fetch-dest: document' \
  -H 'sec-fetch-mode: navigate' \
  -H 'sec-fetch-site: same-origin' \
  -H 'sec-fetch-user: ?1' \
  -H 'upgrade-insecure-requests: 1' \
  -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/132.0.0.0 Safari/537.36' \
  --data-raw 'email=new%40yti.com&password=yokoyoko'
```