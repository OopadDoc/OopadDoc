**PlaceBid**
----
Use it to place a bid on an auction for a user.

* **URL**
  https://fr.oopad.com/WebServices/BiddingWebService/PlaceBid

* **Method:**
  `POST`
  
*  **URL Params**
none

* **Data Params**
	* AuctionId
		`type`: uint
		`description`: Auction on which you want to bid

	* SessionKey
		`type`: string
		`description`: Identify the user. Use the result from [SignIn](../PublicWebService/SignIn.md) to fill this field.

	**example:**
```JSON
	{
		req: 
		{ 
			SessionKey: "7d338791-3dee-4467-8ec3-7e60f897b7f6",
			 AuctionId: "16223", 
			 Locale: "fr-FR"
		}
	}
```

* **Success Response:**
	**Code:** 200 
    **Content:**

	* Success
		`type`: bool
		`description`: true if operation succeeded

	* Status
		`type`: string
		`description`: operation status. You should expect "SUCCES".

  **example:**
```JSON
{
	"d":
	{
		"__type":"TGB.WebServices.Bidding.BiddingWebService+PlaceBidResp",
		"Success":true,
		"Status":"SUCCESS",
		"NewSessionKey":"7d338791-3dee-4467-8ec3-7e60f897b7f6",
		"Error":0
	}
}
```

* **Error Response:**
//TODO

* **Sample Call:**
	From ajax:
	
```javascript
jQuery.ajax({
	url: "/WebServices/BiddingWebService.asmx/PlaceBid",
	data: '
		{
			"req": {"SessionKey": "'+IdentificationId+'",
			"AuctionId": "'+auctionId+'",
			"Locale": "'+Culture+'"}
		}',
	success: function (result)
	{					
		if(result&&result.d&&result.d.Success)
		{
			//Handle success
		}
		else
		{
			//Error occured, you don't hold the auction!
		}
	}
});
```

* **Notes:**
//TODO

> Written with [StackEdit](https://stackedit.io/).