**IsPublicNameAvailable**
----
	Tells whether or not a PUBLIC NAME is available

* **URL**
  https://fr.oopad.com/WebServices/SignUpWebService/IsPublicNameAvailable

* **Method:**
   `POST` 
  
*  **URL Params**
	none
	
* **Data Params**
	- publicName
		`type`: string
		`description`: publicname to check

	**example:**
```json
{
  "publicName" : "test"
}
```

* **Success Response:**
    **Code:** 200 
    **Content:** 
    
    - anonym
	    `type`: bool
	    `description`: true if available

	**example:**
```json
{
    "d": false
}
```

* **Error Response:**
//TODO

* **Sample Call:**
//TODO

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).

