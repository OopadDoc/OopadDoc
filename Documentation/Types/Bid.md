Type Bid
============

 Note
----------------

This object describe a bid set on an auction. The last bid is the winning bid. Auction end when a bid stay at the top for a long enough ([Auction](/Types/Auction.md).BidTime).


Composition
----------------

- BidId
	`type`: uint
	`description`: Unique identifier of the Bid

- AuctionId
	`type`: uint
	`description`: Unique identifier of the auction on which the bid has been set

- BidPice
	`type`: double
	`description`: Value that must be paid if the bid is the winning bid at the end of the auction

- DateCreation:
	`type`: DateTime
	`description`: Date at which the bid was created

- AutoBidId
	`type`: uint?
	`description`: Unique identifier of the autobid which emited this bid, if there is one.

- BidStatus
	`type`: string
	`description`: Status of the bid. POssibles values : { 'PENDING', 'WIN', 'LOSE', 'REFUNDED', 'REFUNDED_PRIZE', 'REFUNDED_CASH', 'REFUNDED_AUCTION' }

- UserId
	`type`: uint
	`description`: Unique identifier of the bidder

- PublicName
	`type`: string
	`description`: Public name of the bidder at the time the bid was created

- BidServerTimeMs
	`type`: long
	`description`: ServerTimestamp (miliseconds) when the bid was created

- BidServerTime
	`type`: long
	`description`: ServerTimestamp (seconds) when the bid was created

Example
-----------

```json
{
	"BidId": 41255726,
	"AuctionId": 54782,
	"BidPrice": 15.21,
	"AutoBidId": 2607926,
	"BidStatus": "PENDING",
	"UserId": 4118752,
	"PublicName": "bob",
	"BidServerTimeMs": 1461936258637,
	"BidServerTime": 1461936258,
	"AuctionDateLastBidServerTimeMs": 1461936258637,
	"DateCreation": "\/Date(1461929058637)\/",
	"AuctionDateLastBid": null
}
```




> Written with [StackEdit](https://stackedit.io/).