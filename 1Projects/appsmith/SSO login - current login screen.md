- the main page that gets rendered for the setup screen is the ==`UserWelcomeScreen.tsx`==
- Needs to be replaced with the screen that is similar to YDX login

##### Things to note
- Every string message that needs to be displayed is part of a ==`StringConstants`== file
- the constants are of arrow function type
	- each constant is an arrow function that accepts no input values and returns the required string
		```javascript
		export const MESSAGE = ()=>"This is a message"
		```
- the form is placed in ==`DetailsForm.tsx`== file

```
=The+redirect+URI+in+the+request:+https://seed-webapp-sso.msa.apps.yokogawa.dev/callback+did+not+match+a+registered+redirect+URI.&code=invalid_request&skipConsent=false
```
---
###### Changes done
- Main changes done to the `config.json` in `UserAuth` dir
	```JSON
	{
    "redirectUri": "https://dev.appsmith.com/callback", 
    "adminUrl": "https://sso.msa.apps.yokogawa.dev/admin/auth/user?tenant=YDX",
    "scope": "openid email profile tenant",
    "responseType": "code",
    "responseMode": "query",
    "platformTokenServiceUri": "https://api.msa.apps.yokogawa.dev/tokens/v1/",
        "clientId":"redZClCiq003bqsBt8aMMNM3",
"clientSecret":"MIsfNP7UTEwm0viZ4Sm98eNGnLY4JTqgrCsT6mQstStbWs9p3Li_SCKnmAiiI0szokCuBAvsksFqsDanVyUL9A",
    "authorizeUri":"https://fidm.us1.gigya.com/oidc/op/v1.0/4_j64tnG1hJXdBLoyoOkSzXA/authorize",
    "tokenUri":"https://fidm.us1.gigya.com/oidc/op/v1.0/4_j64tnG1hJXdBLoyoOkSzXA/token",
    "userInfoUri":"https://fidm.us1.gigya.com/oidc/op/v1.0/4_j64tnG1hJXdBLoyoOkSzXA/userinfo",
    "logOutUri":"https://sso-static.dev.apps.yokogawa.build/oidcLogout.html"
}
	```


`https://dev.appsmith.com/callback?code=st2.s.AtLtpzsD3Q.Q6-HChP5oT-OYPemGnkczNtJvxpr8RRwYOrqdLWNOtwR3eqgeG71JvKGzI30CKH9WrPGI2D66JskmR9hJaiqOlV948aMkHSEWnbgl-jEJJeYGKjSp5GVSBAId3Tz7P1C.vi84kVjZl6tiXg4GbjfI7fOBaliZa1bGVVWhiye3f7J2KOLIR9TbfzjetOoYeXnuXPHJVAibUHKWkReoxlxbhQ.sc3`