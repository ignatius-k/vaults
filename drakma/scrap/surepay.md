validation

request
{
  "accountNumber": "1696000001",
  "accountType": "SCHOOLFEES",
  "accountCategory": "SCHOOLFEES"
}
responses
student not found
{
	"accountCategory": "",
	"accountName": "",
	"accountNumber": "",
	"accountProvider": "",
	"accountType": "None",
	"addendum": null,
	"airtelOva": null,
	"bankAccountCurrency": null,
	"bankAccountNumber": null,
	"bankId": null,
	"bankName": null,
	"convertedOutstandingBalance": null,
	"dollarRate": null,
	"minimumBalance": null,
	"minimumFees": null,
	"mtnOva": null,
	"outstandingBalance": "0",
	"processId": null,
	"schoolCode": null,
	"statusCode": "FAILED",
	"statusDesc": "Student Details Not Found",
	"studentGrade": null,
	"type": null
}

student found
{
	"accountCategory": "SCHOOLFEES",
	"accountName": "KIRYA JOASH",
	"accountNumber": "1731400002",
	"accountProvider": "NEW STANDARD KALEEGERO PRIMARY SCHOOL",
	"accountType": "SCHOOLFEES",
	"addendum": "Baby",
	"airtelOva": null,
	"bankAccountCurrency": "UGX",
	"bankAccountNumber": "3203912209",
	"bankId": "",
	"bankName": "CENTENARY BANK",
	"convertedOutstandingBalance": "68000.0",
	"dollarRate": null,
	"minimumBalance": 0,
	"minimumFees": null,
	"mtnOva": null,
	"outstandingBalance": "68000.0",
	"processId": null,
	"schoolCode": "17314",
	"statusCode": "SUCCESS",
	"statusDesc": "SUCCESS",
	"studentGrade": "Baby",
	"type": null
}

student found
{
	"accountCategory": "SCHOOLFEES",
	"accountName": "JOPIO TIMOTHY",
	"accountNumber": "1696000001",
	"accountProvider": "TRUST NURSERY AND PRIMARY SCHOOL",
	"accountType": "SCHOOLFEES",
	"addendum": "P.6",
	"airtelOva": null,
	"bankAccountCurrency": "UGX",
	"bankAccountNumber": "3205107040",
	"bankId": "",
	"bankName": "CENTENARY BANK",
	"convertedOutstandingBalance": "0.0",
	"dollarRate": null,
	"minimumBalance": 20000,
	"minimumFees": null,
	"mtnOva": null,
	"outstandingBalance": "0.0",
	"processId": null,
	"schoolCode": "16960",
	"statusCode": "SUCCESS",
	"statusDesc": "SUCCESS",
	"studentGrade": "P.6",
	"type": null
}


transaction status

request

transaction not found
{
	"accountName": "",
	"accountNumber": "",
	"accountType": "",
	"bankCode": null,
	"currency": "",
	"gatewayReference": "",
	"statusCode": "FAILED",
	"statusDescription": "Transaction Not Found",
	"tranAmount": "",
	"transactionDescription": "Transaction Not Found",
	"transactionId": "20261112100002",
	"transactionStatus": "NOT FOUND"
}

transaction found
{
	"accountName": "KIRYA JOASH",
	"accountNumber": "1731400002",
	"accountType": "SCHOOLFEES",
	"bankCode": "CENTENARY_GONZAPAY",
	"currency": "UGX",
	"gatewayReference": "331084310881",
	"statusCode": "SUCCESS",
	"statusDescription": "Status Retrieved",
	"tranAmount": "2000",
	"transactionDescription": "Transaction Notified Successfully",
	"transactionId": "20261112100001",
	"transactionStatus": "SUCCESS"
}


make payment

successfult payment