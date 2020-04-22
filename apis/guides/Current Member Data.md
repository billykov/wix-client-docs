# Current Member Data `{{maybe should rename it to Current Visitor Data?}}`

`{{summary here}}`
Returns information about the current site visitor (dependent on login as site member).  
Can be accessed via JavaScript on the site's client side.  
Returns a JWT with identifying details about the user/member that is signed with your public key (add link to how we sign data).  

This API should be used if your application needs to check, on the client-side, if the user is currently logged in to the site. 
In addition, it allows you to confirm this customer's identity within the insecure environment of the user's browser.


### Authorization / Permissions `{{choose one}}`
`{{authorization info here - not necessarily about token, but can be link to article about embeded script etc...}}`

### Syntax
```
**GET**  https://{site_domain}/_api/apps/current-member/{app_id}
```

### Request Params

|Name|Description|
|---|---|
|site_domain|Site domain|
|app_id|App ID (ensures the response will be signed with the correct key)|


### Response

|Name|Description|
|---|---|
|**member**|Member data|
| member.**id** | GUID of the user that can be used to accessed more information|
| member.**role**| Site visitor's role: “MEMBER”|
| member.**email**| Email address|
| member.**nickname**| Member's name|
| member.**language**| Member's primary language|
|**signedToken**| A signed JWT token, which you can verify with you public key (available in the Developers Center)|
