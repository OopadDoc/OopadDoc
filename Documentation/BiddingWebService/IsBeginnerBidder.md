**IsBeginnerBidder**
----
	Check if the identified user is regarded as beginner


* **URL**
 https://fr.oopad.com/WebServices/BiddingWebService/IsBeginnerBidder

* **Method:**
	`POST`
  
*  **URL Params**
	none

* **Data Params**

	* SessionKey
		`type`: string
		`description`: Identify the user. Use the result from [SignIn](/PublicWebService/SignIn.md) to fill this field.


* **Success Response:**
	**Code:** 200
	**Content:**

	* *anonym*
		`type`: bool
		`description`: true if user is regarded as beginner
	
	**example:**
```JSON
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