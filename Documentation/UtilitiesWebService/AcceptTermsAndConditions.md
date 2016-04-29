**AcceptTermsAndConditions**
----
  Signal that user accepted terms and conditions. 
  Should be called from client browser only.

* **URL**
  https://fr.oopad.com/WebServices/UtilitiesWebService/AcceptTermsAndConditions

* **Method:**
  `POST`
  
*  **URL Params**
	none
	
* **Data Params**

	- sessionKey
		`type`: string
		`description`: Authentification token from SignIn query.

	**example:**
```json
{
  "sessionKey" :"7d987491-3dee-4607-8ac3-7e60f987b7f6"
}
```

* **Success Response:**
    **Code:** 200 
    **Content:** `null`

	**example:**
```json
{
    "d": null
}
```
 
* **Error Response:**
//TODO

* **Sample Call:**
//TODO

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).