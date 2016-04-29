**GetWalletAmount**
----
  Get wallet of an authentified user.
  see also type [Wallet](/Types/Wallet.md)
  
* **URL**
  https://fr.oopad.com/WebServices/UserWebService/GetWalletAmount

* **Method:**
   `POST`
  
*  **URL Params**
	none  
   
* **Data Params**
	- identificationId
		`type`: string
		`description`: Authentification token from SignIn query.

	- walletId
		`type`: uint
		`description`: Wallet unique identifier

	**example:**
```json
{
  "identificationId" :"7d339891-3dee-4607-8ec3-7e60f337b7f6",
  "walletId" : 4405176
}
```
	
  
* **Success Response:**

    **Code:** 200 
    **Content:** 

	- Amount
			`type`: double
			`description`: Amount usable by user
	
	- AmountInPlay
		`type`: double
		`description`: **deprecated**

**example**
```json
{
    "d": {
        "__type": "TGB.WebServices.BeterZ.UserWebService+WalletAmounts",
        "Amount": 1000000,
        "AmountInPlay": 0
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