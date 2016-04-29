**SignIn**
----
  Used to connect user to the system.
  `return`: token used by other webservices for user authentification

* **URL**
  https://fr.oopad.com/WebServices/PublicWebService/SignIn

* **Method:**
   `POST`
  
*  **URL Params**
	none
	
* **Data Params**
	- Email
		`type`: string
		`description`: Email or login of the user

	- Password
		`type`: string
		`description`: Email or login of the user

	- Persistent
		`type`: bool
		`description`: Set to true for persistent connection

	**example**

```json
{
  "req":{
  "EMail":"testAccount@oopad.com",
  "Password":"testtest",
  "Persistant":true
  }
}
```

* **Success Response:**
    **Code:** 200
    **Content:** 

	- SignInInfos
		`type`: SignInInfos
		`description`: Contain UserId, Sessionkey and possible error infos. In case of conflict with other session key, **use this one**.

	- NewSessionKey
		`type`: string
		`description`: Key used for futur operation. Session key can change (when rights changes)

	**example**

```json
{
    "d": {
        "__type": "TGB.WebServices.BeterZ.Public.v1_0.PublicWebService+SignInResp",
        "SignInInfos": {
            "UserId": 1,
            "SessionKey": "1599c837-f40d-42c2-806b-37918b26e2d2",
            "Error": 0
        },
        "NewSessionKey": "1599c837-f40d-42c2-806b-37918b26e2d2",
        "Error": 0
    }
}
```

 
* **Error Response:**
//TODO

* **Sample Call:**
//TODO

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).