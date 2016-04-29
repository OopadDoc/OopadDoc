**IsEMailAvailable**
----
Tells whether or not a PUBLIC NAME is available


* **URL**
  https://fr.oopad.com/WebServices/SignUpWebService/IsEMailAvailable

* **Method:**
  `POST` 
  
*  **URL Params**
	none 

* **Data Params**

	  - email
		  `type`: string
		  `description`: requested email

	**example:**
```json
{
  "email" : "bob@oopad.com"
}
```
  
* **Success Response:**
     **Code:** 200 
    **Content:** 

	- *anonym*
		`type`: bool
		`description`: `True` if available

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