**SetFormUserAnswer**
----
   Used to gather anwser for the quality form, completed by users.

* **URL**
  https://fr.oopad.com/WebServices/UserWebService/SetFormUserAnswer

* **Method:**
  `POST`
  
*  **URL Params**
	none

* **Data Params**

	- identificationId
		`type`: string
		`description`: Authentification token from SignIn query.

	- questionKey
		`type`: string
		`desription`: Identifier of a question

	- answerValue
		`type`: string
		`description`: user's answer. Depending of the question, there may be a check

	**example:**
```json
{
 "identificationId" :"7d339891-3dee-4607-8ec3-7e60f337b7f6",
 "questionKey" : "BIRTHDATE",
 "answerValue" : "bob!"
}
``` 


* **Success Response:**
  
    **Code:** 200
    **Content:** 

	- *anonym*
		`type`: bool
		`description`: true if operation succeeded
	
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