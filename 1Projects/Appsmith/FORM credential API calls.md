2 step problem
- send a request to `/api/v1/login` 
- send the `SESSION` cookie to the next requests

### getting the session cookie
- this is done by calling the `/api/v1/login`
- pass the username and password in the body of the API call
- the cURL of the API call is as follows
```curl
curl 'https://dev.appsmith.com/api/v1/login' \
  -H 'accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'cache-control: max-age=0' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -H 'origin: https://dev.appsmith.com' \
  -H 'priority: u=0, i' \
  -H 'referer: https://dev.appsmith.com/user/login' \
  -H 'sec-ch-ua: "Chromium";v="130", "Brave";v="130", "Not?A_Brand";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  -H 'sec-fetch-dest: document' \
  -H 'sec-fetch-mode: navigate' \
  -H 'sec-fetch-site: same-origin' \
  -H 'sec-fetch-user: ?1' \
  -H 'sec-gpc: 1' \
  -H 'upgrade-insecure-requests: 1' \
  -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36' \
  --data-raw 'username=yti%40yti.com&password=password' \
  --insecure
```

this will return the cookie and a couple of headers

---
### sending the SESSION cookie
- while making a call to the API, pass the cookie as one of the headers
- the cURL of one of the API is as follows
```curl
curl --location 'https://dev.appsmith.com/api/v1/workspaces/home' \
--header 'accept: application/json, text/plain, */*' \
--header 'accept-language: en-US,en;q=0.9' \
--header 'cookie: SESSION=6bb0649d-19d0-4055-bf8e-cf5c92ce1912' \
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
