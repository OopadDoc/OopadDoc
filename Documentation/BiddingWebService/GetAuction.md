
**GetAuction**
----
	Get informations for a specific auction.

* **URL**
   https://fr.oopad.com/WebServices/BiddingWebService/GetAuction

* **Method:**
   `POST` 
  
*  **URL Params**
	none

* **Data Params**
	* AuctionId		
		`type`: uint?
		`description`: signal which auction do you wish to watch

	* BidCurrencyId	
		`type`: uint?
		`description`: Currency selected by user to buy products. Most likely 10 for "euros". For more information see [Currencies List](../Types/CurrenciesList.md)

	* WalletCurrencyId
		`type`: uint?
		`desciption`: Currency selected by user to bid. Most likely 1 for "oopad". For more information see [Currencies List](../Types/CurrenciesList.md)

	* SinceUpdateId
		`type`: string
		`description`: Define which front server handled the last update and when it occured. Use the result from the previous [GetBiddingEverything](GetBiddingEverything.md) to fill this field. **Set "0" for the first update**

	* SessionKey
		`type`: string
		`description`: Identify the user. Use the result from [SignIn](../PublicWebService/SignIn.md) to fill this field.
		 
	* Locale
		`type`: string
		`description`: define which language will be used for some results (auction Name, current avaiable auctions...)

	**example**
	see [GetBiddingEverything](GetBiddingEverything.md)
 
* **Success Response:**
   **Code:** 200
    **Content:** 
    *  Auction
		  `type`: [Auction](../Types/Auction.md)
		  `description`: auction information

	* ServerTime
		`type`: long
		`description`: Timestamp of the server when response was handled. May be used to correct lattency.

	* LastUpdateIdWithoutPrepend
		`type`: string
		`description`: Last update Id without server informations

	* LastUpdateId
		`type`: string
		`description`: Use this in the next query as "SinceUpdateId".
  
	**example**:
	see [GetBiddingEverything](GetBiddingEverything.md)
 
* **Error Response:**
//TODO

* **Sample Call:**
//TODO

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).