
**GetBiddingEverything**
------

  Get auctions,biders and bid informations as soon as an auction has changed.
  Long polling method.

* **URL**
  https://fr.oopad.com/WebServices/BiddingWebService/GetBiddingEverything

* **Method:**
     `POST` 
  
*  **URL Params**
   none
 
* **Data Params**
	* AuctionId		
		`type`: uint?
		`description`: signal which auction do you wish to watch
			
	* GetAuctions
		`type`: bool
		`description`: set to true to get auction informations (name, description, product...)

	* GetBids
		`type`: bool
		`description`: set to true to get some latest (ex: top 10) bids on an auction
		**`require`**: AuctionId
			
	* GetBestBids
		`type`: bool
		`description`: set to true to get the best (current) bid of every auctions

	* GetBestBidders
		`type`: bool
		`description`: set to true to get the list of user who have the highest number (not the most valuable) of bids 
		**`require`**: AuctionId

	* BidCurrencyId	
		`type`: uint?
		`description`: Currency selected by user to buy products. Most likely 10 for "euros". For more information see [Currencies List](/Types/CurrenciesList.md)

	* WalletCurrencyId
		`type`: uint?
		`desciption`: Currency selected by user to bid. Most likely 1 for "oopad". For more information see [Currencies List](/Types/CurrenciesList.md)

	* SinceUpdateId
		`type`: string
		`description`: Define which front server handled the last update and when it occured. Use the result from the previous [GetBiddingEverything](GetBiddingEverything.md) to fill this field. **Set "0" for the first update**

	* SessionKey
		`type`: string
		`description`: Identify the user. Use the result from [SignIn](../PublicWebService/SignIn.md) to fill this field.
		 
	* Locale
		`type`: string
		`description`: define which language will be used for some results (auction Name, current avaiable auctions...)


	**example :** 
	
get global information:
```json
	{
		"req" : {
			"AuctionId" : 0,
			"GetAuctions" : "true",
			"GetBids" : "false",
			"GetBestBids" : "true",
			"GetBestBidders" : "false",
			"BidCurrencyId" : 10,
			"WalletCurrencyId" : 1,
			
			"SinceUpdateId" : "www1|635971972727057908",
			"SessionKey" : "b6d69f54-caca-4027-b5e6-c7dc8a8bd408",
			"Locale" : "fr-FR"
		}
	}	
```
 get information for a specific auction:
```json
	{
		"req" : {
			"AuctionId" : 4300,  <---
			"GetAuctions" : "true",
			"GetBids" : "true",  <---
			"GetBestBids" : "true",
			"GetBestBidders" : "true",  <---
			"BidCurrencyId" : 10,
			"WalletCurrencyId" : 1,
			
			"SinceUpdateId" : "www1|635971972727057908",
			"SessionKey" : "b6d69f54-caca-4027-b5e6-c7dc8a8bd408",
			"Locale" : "fr-FR"
		}
	}	
```
	
 
* **Success Response:**
  
   **Code:** 200
   **Content:** 
  * Auctions:
		`type`: [Auction](/Types/Auction.md)[]
		`description`: Current auctions informations.

	* Bids: 
		`type`: [Bid](/Types/Bid.md)[]
		`description`: Some latest bid on a specific auction. (Specified by auctionId request) //TODO

	* BestBids
		`type`: [Bid](/Types/Bid.md)[]
		`description`: Every current bids on every current auctions.

	* BidsCount
		`type`: [BidCount](/Types/BidCount.md)[]
		`description`: Top best bidders (in quantity, not value) informations
	
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
		`description`: Use this in the next [GetBiddingEverything](GetBiddingEverything.md) query as "SinceUpdateId".
  
	 **example:**
```json
{  
	"d":{ 
		"__type":"TGB.WebServices.Bidding.BiddingWebService+GetBiddingEverythingResp",
		"Auctions":[  
	        {  
	           "Id":54389,
	           "AuctionCost":189,
	           "DateStart":"\/Date(1934274395000)\/",
	           "BidStep":0.01,
	           "BidTime":49,
	           "BidCurrencyId":10,
	           "WalletCurrencyId":1,
	           "MaxBidsCount":null,
	           "DealAuction":false,
	           "DisableAutoBids":false,
	           "BeginnerAuction":false,
	           "DirectBuy":true,
	           "CanBeStar":true,
	           "Status":"PENDING",
	           "DateLastBid":null,
	           "CurrentWinnerId":null,
	           "BidAmountMultiplier":1,
	           "NormalCost":null,
	           "QuantityLeft":10000,
	           "QuantityTotal":null,
	           "GiftId":1661,
	           "Name":"UE BOOM 2 - Enceinte Bluetooth ",
	           "Description":null,
	           "PictureName":"1661.jpg",
	           "WinnerPublicName":null,
	           "Debug":null,
	           "DateStartServerTime":1934281595,
	           "DateLastBidServerTime":null
	        },
	        {...}
	     ],
	     "Bids":null,
	     "BestBids":[  
	        {  
	           "BidId":41236236,
	           "AuctionId":54531,
	           "BidPrice":9.42,
	           "AutoBidId":2605064,
	           "BidStatus":"PENDING",
	           "UserId":4084346,
	           "PublicName":"laracroft77",
	           "BidServerTimeMs":1461602847199,
	           "BidServerTime":1461602847,
	           "AuctionDateLastBidServerTimeMs":0,
	           "DateCreation":"\/Date(1461595647199)\/",
	           "AuctionDateLastBid":null
	        },
	        {...}
	     ],
	     "BidsCounts":null,
	     "LastUpdateIdWithoutPrepend":"635971996690438536",
	     "NewSessionKey":"b6d69f79-caca-6451-c5e6-b7dc8a8bd408",
	     "Error":0,
	     "ServerTime":1461602870,
	     "LastUpdateId":"www1|635971996690438536"
	}
}
```
 
* **Error Response:**
	//TODO
	
* **Sample Call:**

  from ajax:
  ```javascript
function getEverything()
{
	  jQuery.ajax({
		url: "/WebServices/BiddingWebService.asmx/GetBiddingEverything",
		
		data: 
		'{ 
			"req": {
				"SessionKey":"'+IdentificationId+'",
				"AuctionId":"'+pageAuctionId+'",
				"GetAuctions":"'+getBoolString(startGetAuctions)+'",
				"GetBids":"'+getBoolString(startGetBids)+'",
				"GetBestBidders":"'+getBoolString(startGetBidsCounts)+'",
				"SinceUpdateId":"'+lastUpdateId+'",
				"BidCurrencyId":"'+PaidCurrencyId+'",
				"WalletCurrencyId":"'+CurrencyId+'",
				"Locale":"'+Culture+'" 
			} 
		}',
		success: function (result)
		{
			//DO STUFF
			setTimeout("getEverything()",1);
		},
		error: function (XMLHttpRequest,textStatus,errorThrown)
		{
			//signal error here
			setTimeout("getEverything()",3000);	//Retry every 3 seconds
		}
	});
}
```

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).