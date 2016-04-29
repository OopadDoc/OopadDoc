**GetCountryLike**
----
	Get unique identifier of a country with a name containing specified string. Search done in all available language.
	Only first result is returned.

* **URL**
  https://fr.oopad.com/WebServices/SignUpWebService/GetCountryLike

* **Method:**
  `POST`
  
*  **URL Params**
	none

* **Data Params**

	- prefixText
	 `type`: string
	 `description` : part of country name

	**example:**
```json
{
  "prefixText" :"ranc"
}
```

* **Success Response:**
	**Code:** 200 
    **Content:**
  
  - *anonym*
	  `type`: uint
	  `description`: unique identifier of country

	**example:**
result for "france"
```json
{
    "d": 77
}
```
  
* **Error Response:**
  //TODO

* **Sample Call:**
//TODO

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).