https://tpsdev.centenarybank.co.ug:6010/api/merchant_inquiry


> POST /api/merchant_inquiry HTTP/1.1
> Host: tpsdev.centenarybank.co.ug:6010
> User-Agent: insomnia/13.2.0
> apiKey: 65638527-84db-4281-b370-85fcbeb80e5c
> Content-Type: application/xml
> Accept: */*
> Content-Length: 394
```
<tpsRequest>
<accountNo>HLlRlpBJ3EHm58i+abGcYBXhMhtc+QA4r8SvLFYG13IE1c9dDEep9+HOUVMUhih90/AQj5r1NjPYgMshX/M5Mxw39kEpJWYSmLGiOnwz7dd3WtE2m/GR7Ef09Ls7V9tFRj8zOlzQCJJ0hFc8wiNWGLkbq2kg66+gyTeRH1NSJxDKmOKD0IMcAmmOhaQSm9YgWioBNFqyT1eYm6+vQT/cnHGDqZKrQf2FN3p9SqakqvP6o11vayDFUOVTMveqDu8MCv2Sxw5o5YvjH4R886tu5QmLxaxnrhUwQfIFlR4rEuAYJGh+hDzhnyKW73zTDOq4CH8sg7Gf2vyaBDiRLp7CFA==</accountNo>
</tpsRequest>
```

```
<?xml version="1.0" encoding="UTF-8"?>
<tpsResponse>
	<serviceId>MERCHANT_INQ</serviceId>
	<responseCode>404</responseCode>
	<responseMessage>Account 32019693150 not found</responseMessage>
	<transactionId>REQ-MERCHANT</transactionId>
</tpsResponse>
```

A successful request
```
<tpsRequest>
<accountNo>UC0E1lqt/auF68QGihJg8620FFMkhiy1zoSWgnLs9V44/KUwh38O0YmQvtdcJmix3B71HraDPdIlsVkAPUoytbn21JQ4h3/6WdFnVI5geOg5NzyoP5IIFOOXF6ItEQdZxeleEcVhiOHFxxEiwNAjHCV941q2BSeEtTg86jWKHbwdNdsh6af2kPycBzyB1Bqd1R12FLF+zF24E700ERFlMsVnlEkudiPZE4696j8HSHbgj2oqRkGndXB66+J7nq0jfengts6DAETJMv9DETsbUncLLPVzJXOUQTw9yMV1CJ20uA/4tSYpQ3YdGSXg/S4HanyoajNz8TDjvSjOCPQVeg==</accountNo>
</tpsRequest>
```

```
<?xml version="1.0" encoding="UTF-8"?>
<tpsResponse>
	<responseStatus>success</responseStatus>
	<responseCode>200</responseCode>
	<responseMessage>Success</responseMessage>
	<title>MR.</title>
	<firstName>IGNATIUS</firstName>
	<lastName>KISEKKA</lastName>
	<nin>CM84098100AVDG</nin>
	<address>MASAKA</address>
	<city>MASAKA</city>
	<phone>567123456</phone>
	<account>3201969315</account>
	<category>OTHER</category>
	<tin></tin>
</tpsResponse>
```

this feature is to be added in this application, used to get customer information when an account number is provided,
the account number is provided by user but encrypted before contacting tps;

the implementation should display correct messages to the client in case of any issue

the information to be represented well, on the front