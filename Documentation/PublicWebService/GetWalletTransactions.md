**GetWalletTransactions**
----
  Get last transactions from specified wallet. 
  Some tansaction may be compacted (by month most likely)
  
* **URL**
  https://fr.oopad.com/WebServices/PublicWebService/GetWalletTransactions

* **Method:**
  `POST` 
  
*  **URL Params**
	none

* **Data Params**

  	- WalletId
		`type`: uint
		`description`: Wallet unique Identifier. get it from //TODO
		
  	- WalletTransactionType
		`type`: enum WalletTransactionType
		`description`: possible values { SUBSCRIPTION, BONUS, RELOAD, BET, PRONOSTIC, COMMENT, FEE, EXITFEE, DECAY, CRM, WITHDRAW, DEPOSIT, TRANSFERT, SHOP, COMMISSION, REFER, BID, COMPRESS, TOURNAMENT }
		see also Type [Wallet](/Types/Wallet.md)
		
	- TransactionId
		`type`: uint?
		`description`: Reference specific transaction
		
	- BetId
		`type`: uint?
		`description`: Deprecated, should be `null` 
		
	- CommentId
		`type`: uint?
		`description`: Deprecated, should be `null` 
		
	- TournamentId
		`type`: uint?
		`description`: Deprecated, should be `null`
		
	- ItemsCount
		`type`: uint
		`description`: Expected number of transactions returned. (max 500)
		
	- PageNumber
		`type`: uint
		`description`: Start returning transaction from (PageNumber*ItemsCount). Newest to oldest.
		
	- ApplicationKey
		`type`: string
		`description`: Key used to authentify your request
		
	- Locale
		`type`: string
		`description`: Locale of user
		
* **Success Response:**
	**Code:** 200
    **Content:** 

	- Locale
		`type`: string
		`description`: Locale of user

	- WalletTransactions
		`type`: [WalletTransaction](/Types/WalletTransaction.md)[]
		`description`: Requested transactions 
	
	- HaveMore
		`type`: bool
		`description`: indicate whether there are more transactions available. If so, you can get them by incrementing page number.
		
	- NewSessionKey
		`type`: string
		`description`: *ignore*
		
	- Error
		`type`: enum: ResponseError
		`description`: possible values: { NO_ERROR, INVALID_SESSION, INVALID_CREDENTIALS }
 
* **Error Response:**
	//TODO

* **Sample Call:**
	//TODO

* **Notes:**
	//TODO


> Written with [StackEdit](https://stackedit.io/).