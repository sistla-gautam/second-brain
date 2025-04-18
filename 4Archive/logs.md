```
export default {

  async fetch(request) {

    const url = new URL(request.url);

  

    if (url.pathname === "/auth/github/callback") {

      const code = url.searchParams.get("code");

      if (!code) {

        return new Response("Missing authorization code", { status: 400 });

      }

  

      // Exchange the code for an access token

      const tokenResponse = await fetch("https://github.com/login/oauth/access_token", {

        method: "POST",

        headers: { "Content-Type": "application/json", "Accept": "application/json" },

        body: JSON.stringify({

          client_id: "Iv23ctGNeQ6GKQ4nxbeP",

          client_secret: "3a9c1a990a817fd7105ff136520083827aae68d7",

          code

        })

      });

  

      const { access_token } = await tokenResponse.json();

      if (!access_token) {

        return new Response("Failed to obtain access token", { status: 400 });

      }

  

      // Fetch user details

      const userResponse = await fetch("https://api.github.com/user", {

        headers: { Authorization: `Bearer ${access_token}` }

      });

  

      const userData = await userResponse.json();

      return new Response(JSON.stringify(userData), {

        headers: { "Content-Type": "application/json" }

      });

    }

  

    return new Response("Not Found", { status: 404 });

  }

};
```


---

# assets
**Assets**
asset-id
type
model
manufacturer
OS version
license number
office/vsstudio
date purchased
usage start date
usage end date
screen size
CPU
original memory
current memory
RAM type
storage type
OS
current problems
price
active?
usable?
express service code
remarks


**employee**
emp_id
first name
last name
phone number

**asset-history**
asset-id
asset-model
start date
end date
start/end
user-id
user-name
reason to start
reason to end