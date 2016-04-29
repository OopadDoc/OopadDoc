**IsPublicNameAvailableForUser**
----
  Check whether the specified suer can change his publicName to a specified one.

* **URL**
  https://fr.oopad.com/WebServices/SignUpWebService/IsPublicNameAvailableForUser

* **Method:**
	`POST`
  
*  **URL Params**
	none

* **Data Params**
	- userId
		`type`: uint
		`description`: specified user
	
	- publicName
		`type`: string
		`description`: requested publicName

**example:**

```json
{
  "publicName" : "tretrey",
  "userId" : 1
}
```

* **Success Response:**
    **Code:** 200
    **Content:** 

	- *anonym*
		`type`: bool
		`description`: true if available

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