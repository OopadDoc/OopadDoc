Type Auction
============

 Note
----------------

This object describe an auction given a specific locale and currency info. Different state of the auction may exist for differents locale and currency. Price may change with currency or the auction may not be available for a specific country.


Composition
----------------
	

- Id
	`type` : uint
	`description`: Unique identifier of the auction

- AuctionCost 
	`type`: double
	`description`: Current price of the auction

- DateStart
	`type`: DateTime
	`description`: When the auction is supposed to start, or started.

- DateStartServerTime
	`type`: long
	`description`:  Timestamp of server when auction will/has start(ed). 

- BidStep
	`type`: double
	`description`: value by which the auction price is incremented at each bid

- BidTime
	`type`: uint
	`description`: How long a bidder has to wait in order to win the auction. Include 4 seconds of verification that is not displayed.

- BidCurrencyId	
		`type`: uint
		`description`: Currency selected by user to buy products. Most likely 10 for "euros". For more information see [Currencies List](../Types/CurrenciesList.md). 

- WalletCurrencyId
		`type`: uint
		`desciption`: Currency selected by user to bid. Most likely 1 for "oopad". For more information see [Currencies List](../Types/CurrenciesList.md)

- MaxBidsCount
	`type`: uint?
	`description`: Auction will stop if this number of bid is reached.

- DealAuction
	`type`: bool
	`description`: `True` if this auction is a deal auction. Bids are not available on a deal auction, only direct purchase.

- DisableAutoBids
	`type`: bool
	`description`: `True` if autobid system is disabled on this auction. Only manual bid remain.

- BeginnerAuction
	`type`: bool
	`description`: `True` if only beginner bidders can participate to the auction.

- DirectBuy
	`type`: bool
	`description`: `True` if bidder can directly purchase the product displayed on the auction. This does not end the auction, since there are multiple item in stock.

- CanBeStar
	`type`: bool
	`description`: `True` if the auction must be displayed with more weight.

- Status
	`type`: string
	`description`: Current status of the auction. Possibles values :	 {'INVISIBLE', 'PENDING', 'INPLAY', 'SUSPENDED', 'TERMINATED', 'PAID', 'CANCELED', 'REFUNDED', 'PAID_PARITY' }
	See [auction status](../Type/AuctionsStatus) for more info.

- DateLastBid
	`type`: DateTime?
	`description`: Last time the auction received a bid. 
	You should rather use [GetBestBid](../BIddingWebService/GetBestBid.md) or any query returning a [Bid](/Types/Bid.md) type for up to date informations.

- DateLastBidServerTime
	`type`: long?
	`description`: Server timestamp (seconds) for DateLastBid

- CurrentWinnerId
	`type`: uint?
	`description`: Unique identifier of the current best bidder. 
	You should rather use [GetBestBidder](../BIddingWebService/GetBestBidder.md) or any query returning a [Bidder](/Types/Bidder.md) type for up to date informations.

- BidAmountMultiplier
	`type`: double
	`description`: Used to define the current price and value of each step depending of the currency.

- NormalCost
	`type`: double?
	`description`: Price of the product displayed

- QuantityLeft
	`type`: uint?
	`description`: How many units of this product is available

- QuantityTotal
	`type`: uint?
	`description`: How many units of this product were available at the start of the auction. Used for deal auctions

- GiftId
	`type`: uint
	`description`: unique identifer of the product displayed

- Name
	`type`: string
	`description`: Title displayed

- Description
	`type`: string
	`description`: Text descripting auction

- PictureName
	`type`: string
	`description`: relative url of the picture

- WinnerPublicName
	`type`: string
	`description`: Current winner's plublic name. Can also be obtain in a [bidder](../Types/Bidder.md) type query.


Example
-----------

```json
{
	"Id": 54492,
	"AuctionCost": 899,
	"DateStart": "\/Date(1461845450000)\/",
	"BidStep": 0.01,
	"BidTime": 49,
	"BidCurrencyId": 10,
	"WalletCurrencyId": 1,
	"MaxBidsCount": null,
	"DealAuction": false,
	"DisableAutoBids": false,
	"BeginnerAuction": false,
	"DirectBuy": true,
	"CanBeStar": true,
	"Status": "INPLAY",
	"DateLastBid": "\/Date(1461926149181)\/",
	"CurrentWinnerId": 4084346,
	"BidAmountMultiplier": 1,
	"NormalCost": null,
	"QuantityLeft": 9969,
	"QuantityTotal": null,
	"GiftId": 1289,
	"Name": "SAMSUNG Smart LED TV 3D 55\" (138cm)",
	"Description": null,
	"PictureName": "1289.jpg",
	"WinnerPublicName": null,   <--- value not up to date
	"Debug": null,
	"DateStartServerTime": 1461852650,
	"DateLastBidServerTime": 1461933349
}
```


> Written with [StackEdit](https://stackedit.io/).