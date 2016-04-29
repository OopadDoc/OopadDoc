**SetEMail**
----
   Change status of  a user

* **URL**
  https://fr.oopad.com/WebServices/UserWebService/SetEMail

* **Method:**
  `POST`
  
*  **URL Params**
	none

* **Data Params**

	- identificationId
		`type`: string
		`description`: Identification token from signIn

	- email
		`type`: string
		`description`: user's email

	- permitChangeEMail
		`type`: bool
		`description`: `false` if you do not want to change an already set email
	
	**example: **
```json
{
  "identificationId" :"7d339871-3dee-4607-8ea3-7e60f398c7f6",
  "email": "bob@oopad.com",
  "permitChangeEMail": true
}
```

* **Success Response:**
  
	**Code:** 200 
    **Content:** 

	- *anonym*
		`type`: bool
		`description`: true if operation succeded

	**example:**
```json
{
    "d": true
}
```
 
* **Error Response:**
//TODO

* **Sample Call:**
//TODO

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).