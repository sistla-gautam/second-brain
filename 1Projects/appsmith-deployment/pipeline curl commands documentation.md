# shell script
```shell
#!/bin/bash

# Enable debug mode to see what's happening
set -x

# Accept parameters from the command line
BASE_URL="${1%/}"  # Remove trailing slash if present
EMAIL="$2"
PASSWORD="$3"
WORKSPACE_NAME="$4"

# Check if all parameters are provided
if [ -z "$BASE_URL" ] || [ -z "$EMAIL" ] || [ -z "$PASSWORD" ] || [ -z "$WORKSPACE_NAME" ]; then
    echo "Usage: $0 <base_url> <email> <password> <workspace_name>"
    exit 1
fi

# Check if curl is installed
if ! command -v curl >/dev/null 2>&1; then
    echo "Error: curl is not installed. Please install it first."
    exit 1
fi

# Construct the URLs
SIGNUP_URL="$BASE_URL/api/v1/users"
WORKSPACE_URL="$BASE_URL/api/v1/workspaces/home"

# Function to handle curl errors
check_curl_error() {
    if [ $? -ne 0 ]; then
        echo "Error: curl request failed"
        echo "Curl exit code: $?"
        return 1
    fi
    return 0
}

# Get the session cookie
echo "Attempting to get session cookie..."
CURL_RESPONSE=$(curl --location --silent --include \
    --header 'accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7' \
    --header 'content-type: application/x-www-form-urlencoded' \
    --header "origin: $BASE_URL" \
    --header "referer: $BASE_URL/user/signup" \
    --data-urlencode "email=$EMAIL" \
    --data-urlencode "password=$PASSWORD" \
    "$SIGNUP_URL")
check_curl_error || exit 1

# Extract just the SESSION value from the cookie
COOKIE=$(echo "$CURL_RESPONSE" | grep -i 'Set-Cookie: SESSION=' | sed -n 's/.*SESSION=\([^;]*\).*/\1/p')
if [ -z "$COOKIE" ]; then
    echo "Error: Failed to capture SESSION cookie"
    echo "Server response:"
    echo "$CURL_RESPONSE"
    exit 1
fi

echo "Captured SESSION cookie: $COOKIE"

# Get workspace information
echo "Fetching workspace information..."
RESPONSE=$(curl --location --silent \
    --header 'accept: application/json, text/plain, */*' \
    --header 'accept-language: en-US,en;q=0.9' \
    --header "cookie: SESSION=$COOKIE" \
    --header "referer: $BASE_URL/applications" \
    "$WORKSPACE_URL")
check_curl_error || exit 1

# Extract workspace ID using grep and sed
WORKSPACE_ID=$(echo "$RESPONSE" | grep -o '"id":"[^"]*"' | head -1 | sed 's/"id":"\([^"]*\)"/\1/')
if [ -z "$WORKSPACE_ID" ]; then
    echo "Error: Failed to extract workspace ID"
    echo "Server response:"
    echo "$RESPONSE"
    exit 1
fi

echo "Captured Workspace ID: $WORKSPACE_ID"

# Update workspace title
echo "Updating workspace title..."
UPDATE_URL="$BASE_URL/api/v1/workspaces/$WORKSPACE_ID"
UPDATE_RESPONSE=$(curl --location --silent \
    --request PUT "$UPDATE_URL" \
    --header 'accept: application/json, text/plain, */*' \
    --header 'accept-language: en-US,en;q=0.9' \
    --header 'content-type: application/json' \
    --header "cookie: SESSION=$COOKIE" \
    --header "origin: $BASE_URL" \
    --header "referer: $BASE_URL/applications" \
    --data-raw "{\"id\":\"$WORKSPACE_ID\",\"name\":\"$WORKSPACE_NAME\"}")
check_curl_error || exit 1

echo "Workspace Update Response: $UPDATE_RESPONSE"

# Check if update response contains an error message
if echo "$UPDATE_RESPONSE" | grep -q '"error"'; then
    echo "Error: Update request failed"
    exit 1
fi

echo "Workspace update completed successfully"

```
- save this file as ==`workspace.sh`==
 
#### usage of shell script

- make it executable
```shell
 chmod +x workspace.sh 
```
- call the script with the required parameters
```shell
 sudo bash ./workspace.sh "https://forms.dev.apps.yokogawa.build" "newuser2@yti.com" "yokoyoko" "new-tenant"
```
**format/syntax**
```shell
 sudo bash ./workspace.sh <tenant-base-url>  <admin email> <admin password> <tenant name>
```
