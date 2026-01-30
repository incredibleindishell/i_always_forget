
## Manually Request MS Graph Token

**Step 1:**
Obtain `User_code` and `Device_code`
~~~
POST /common/oauth2/devicecode HTTP/2
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 81

client_id=1950a258-227b-4e31-a9cf-717495945fc2&resource=https://graph.windows.net

~~~
