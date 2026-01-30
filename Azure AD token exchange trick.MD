
## Manually Request MS Graph Token

**Step 1:**
Obtain the `User_code` and `Device_code` by sending the following HTTP request:
~~~
POST /common/oauth2/devicecode HTTP/2
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 81

client_id=1950a258-227b-4e31-a9cf-717495945fc2&resource=https://graph.windows.net

~~~

HTTP response will be something like this:

~~~
HTTP/2 200 OK
Cache-Control: no-store, no-cache
Pragma: no-cache
Content-Type: application/json; charset=utf-8
Expires: -1
[SNIPPED....]
Content-Length: 526

{
"user_code":"AB123CDNS",
"device_code":"SAQABIQEAAACvns.............................................................................................IAA",
"verification_url":"https://microsoft.com/devicelogin",
"expires_in":"900",
"interval":"5",
"message":"To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code AB123CDNS to authenticate."}
~~~

**Step 2**

Copy the value of the `user_code` JSON parameter from the HTTP response. In a web browser, navigate to `https://microsoft.com/devicelogin`, enter the copied code, and follow the on-screen instructions to complete user authentication.

Upon successful authentication, copy the value of the `device_code` JSON parameter from the HTTP response in `Step 1` and include it in the following HTTP request:

~~~
POST /common/oauth2/token HTTP/2
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 364

grant_type=urn:ietf:params:oauth:grant-type:device_code&code=SAQABIQEAAA....................................................IAA&client_id=1950a258-227b-4e31-a9cf-717495945fc2
~~~

The HTTP response to the above request will contain an `access_token` for `https://graph.windows.net` and a new `refresh_token`.

Sample HTTP response:

~~~
HTTP/2 200 OK
Cache-Control: no-store, no-cache
Pragma: no-cache
Content-Type: application/json; charset=utf-8
[SNIPPED....]
Content-Length: 4706

{
  "token_type":"Bearer",
  "scope":"62e90394-69f5-4237-9190-012177145e10",
  "expires_in":"4849",
  "ext_expires_in":"4849",
  "expires_on":".......",
  "not_before":"1769680806",
  "resource":"https://graph.windows.net",
  "access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn.....................YXDHA8S-4Ls0wSebPEp8IVDqw",
  "refresh_token":"1.AQUAuWV6Rejl4UWD-4WqQmM-W1...............UOynfXX8ig8",
  "id_token":"eyJ0eXAiOiJKV1QiLCJhbGciO.................mVsIjoiMSAxMiJ9."
}
~~~
The `refresh_token` obtained in this step will be used in the next step to acquire an `access_token` for `https://graph.microsoft.com`.

**Step 3**

From the HTTP response, copy the value of the `refresh_token` JSON parameter and use it as the value of `refresh_token` in the following HTTP request:

~~~
POST /common/oauth2/token HTTP/2
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 1612

grant_type=refresh_token&client_id=1950a258-227b-4e31-a9cf-717495945fc2&refresh_token=1.AQUAuWV.........ynfXX8ig8&resource=https://graph.microsoft.com
~~~

The HTTP response will contain an `access_token` for `https://graph.microsoft.com`.

./Enjoy

