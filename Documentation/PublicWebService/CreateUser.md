**CreateUser**
----
  Create a new user

* **URL**
  https://fr.oopad.com/WebServices/PublicWebService/CreateUser

* **Method:**
   `POST` 
   
*  **URL Params**
	none

* **Data Params**
	- PublicName
		`type`: string
		`description`: Name display to other users

	- Login
		`type`: string
		`description`: Login
		
	- Password
		`type`: string
		`description`: Password
		
	- Email
		`type`: string
		`description`: Email
		
	- FirstName
		`type`: string
		`description`: FirstName 
		
	- MiddleName
		`type`: string
		`description`: MiddleName 
		
	- LastName
		`type`: string
		`description`: LastName

	- BirthDate
		`type`: DateTime?
		`description`: BirthDate

	- CountryId
		`type`: uint?
		`description`: see country table for Id list
		
	- TimezoneId
		`type`: uint?
		`description`: see timezone table for Id list

	- RefererId
		`type`: uint?
		`description`: used for the referal marketing system

	- RemindCredentialsInActivationEMail
		`type`: bool
		`description`: Set to true to include credentials in the inscription mail
	
	- PromotionalCode
		`type`: string
		`description`:  promotionalcode used at subscription

	- WlId
		`type`: uint?
		`description`: Identifier used for some rules. 1 for global, 2 for UK, 3 for Bresil

	- CorrectPublicNameIfExists
		`type`: bool
		`description`: Set to true to avoid receiving failure if public name is already used. PublicName will be modified.

	- ApplicationKey
		`type`: string
		`description`:  Key used to authentify your request

	- Locale
		`type`: string
		`description`: Locale of the user.

* **Success Response:**
    **Code:** 200 
    **Content:** 

	- UserId
		`type`: uint
		`description`: return the unique identifier of the created User

	- Success
		`type`: bool
		`description`: True if operation succeeded 
	
	- NewSessionKey
		`type`: string
		`description`: Key used for futur operation. Session key can change (when rights changes)

	- Error
		`type`: uint
		`description`: Possibles values: { NO_ERROR, INVALID_SESSION, INVALID_CREDENTIALS }
	 
* **Error Response:**
	//TODO

* **Sample Call:**
	//TODO

* **Notes:**
	//TODO

> Written with [StackEdit](https://stackedit.io/).