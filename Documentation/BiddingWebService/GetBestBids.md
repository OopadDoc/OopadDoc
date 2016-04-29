
**GetBestBids**
----
   Get the best (current) bid of every auctions

* **URL**
https://fr.oopad.com/WebServices/BiddingWebService/GetBestBids

* **Method:**
    `POST` 
  
*  **URL Params**


* **Data Params**
  * SinceUpdateId
		`type`: string
		`description`: Define which front server handled the last update and when it occured. Use the result from the previous [GetBiddingEverything](GetBiddingEverything.md) to fill this field. **Set "0" for the first update**

	* SessionKey
		`type`: string
		`description`: Identify the user. Use the result from [SignIn](../PublicWebService/SignIn.md) to fill this field.
		 
	* Locale
		`type`: string
		`description`: define which language will be used for some results (auction Name, current avaiable auctions...)

	**example:**
	see [GetBiddingEverything](GetBiddingEveryThing.md)

* **Success Response:**
	**Code:** 200 
    **Content:** 

	* Bids: 
		`type`: [Bid](../Types/Bid.md)[]
		`description`: Every current bids on every current auctions

	* LastUpdateIdWithoutPrepend
		`type`: string
		`description`: Last update Id without server informations
		
	* NewSessionKey
		`type`: string
		`description`: Use this in the next query as the SessionKey.

	* Error
		`type`: enum: ResponseError
		`description`: possible values: { NO_ERROR, INVALID_SESSION, INVALID_CREDENTIALS }

	* ServerTime
		`type`: long
		`description`: Timestamp of the server when response was handled. May be used to correct lattency.

	* LastUpdateId
		`type`: string
		`description`: Use this in the next query as "SinceUpdateId".
 
* **Error Response:**
  //TODO

* **Sample Call:**
	**example:**
	see [GetBiddingEverything](GetBiddingEveryThing.md)
 
* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).