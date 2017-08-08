---
title: ETHdb API v?
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - python: Python
  - ruby: Ruby
  - java: Java
toc_footers:
  - '<a href="http://ethdb.io/docs/api">API Documentation</a>'
includes: []
search: true
highlight_theme: darkula
---

# ETHdb API v?

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Ethereum Blockchain explorer

Base URLs:

* <a href="http://localhost:3001/api/v1">http://localhost:3001/api/v1</a>



Email: <a href="mailto:contact@etheraccounting.com">EtherAccounting</a> Web: <a href="http://etheraccounting.com">EtherAccounting</a> 

# Account

## Account#show

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/account/{Address} \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/account/{Address} HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/account/{Address}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/account/{Address}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/account/{Address}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/account/{Address}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/account/{Address}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /account/{Address}`

*show Account*

Returns Account information

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Address|path|string|true|Account address


> Example responses

```json
{
  "Address": "Eligendi nisi.",
  "Balance": "Quaerat voluptatem non alias a in omnis.",
  "Contract": {
    "Code": {
      "ABI": "Eum quos.",
      "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
      "Verified": false
    },
    "CreatedBy": "Ut rerum omnis corporis adipisci facilis.",
    "CreationBlockHash": "Sed et officiis quo est numquam.",
    "CreationBlockHeight": 7885687097374916000,
    "CreationTimestamp": 7072314242291326000,
    "CreationTransaction": "Voluptas hic ullam inventore.",
    "SourcePackage": {
      "Name": "Alias distinctio sed.",
      "Type": "Quia voluptatem eum dolores officia.",
      "URL": "Voluptas amet."
    }
  },
  "MessageCount": 2362536009182212000,
  "MinedBlockCount": 3769039475084015600,
  "MinedUncleCount": 4349567159630496000,
  "Network": "Voluptas accusantium fugiat eos aut adipisci.",
  "Nickname": "Est porro sint dignissimos doloribus pariatur maiores.",
  "Nonce": "Similique accusantium.",
  "TransactionCount": 159856759856627170
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Address>Eligendi nisi.</Address>
<Balance>Quaerat voluptatem non alias a in omnis.</Balance>
<Contract>
  <Code>
    <ABI>Eum quos.</ABI>
    <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
    <Verified>false</Verified>
  </Code>
  <CreatedBy>Ut rerum omnis corporis adipisci facilis.</CreatedBy>
  <CreationBlockHash>Sed et officiis quo est numquam.</CreationBlockHash>
  <CreationBlockHeight>7885687097374916000</CreationBlockHeight>
  <CreationTimestamp>7072314242291326000</CreationTimestamp>
  <CreationTransaction>Voluptas hic ullam inventore.</CreationTransaction>
  <SourcePackage>
    <Name>Alias distinctio sed.</Name>
    <Type>Quia voluptatem eum dolores officia.</Type>
    <URL>Voluptas amet.</URL>
  </SourcePackage>
</Contract>
<MessageCount>2362536009182212000</MessageCount>
<MinedBlockCount>3769039475084015600</MinedBlockCount>
<MinedUncleCount>4349567159630496000</MinedUncleCount>
<Network>Voluptas accusantium fugiat eos aut adipisci.</Network>
<Nickname>Est porro sint dignissimos doloribus pariatur maiores.</Nickname>
<Nonce>Similique accusantium.</Nonce>
<TransactionCount>159856759856627170</TransactionCount>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbAccount](#schemaethdbaccount)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

## Account#code

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/account/{Address}/code \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/account/{Address}/code HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/account/{Address}/code',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/account/{Address}/code',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/account/{Address}/code',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/account/{Address}/code', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/account/{Address}/code");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /account/{Address}/code`

*code Account*

Returns code for contract.  Returns not found if Account is not a contract

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Address|path|string|true|Account address


> Example responses

```json
{
  "ABI": "Eum quos.",
  "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
  "Verified": false
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<ABI>Eum quos.</ABI>
<Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
<Verified>false</Verified>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbContractcode](#schemaethdbcontractcode)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

## Account#mined_blocks

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/account/{Address}/mined_blocks \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/account/{Address}/mined_blocks HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/account/{Address}/mined_blocks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/account/{Address}/mined_blocks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/account/{Address}/mined_blocks',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/account/{Address}/mined_blocks', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/account/{Address}/mined_blocks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /account/{Address}/mined_blocks`

*mined_blocks Account*

Returns list of blocks mined by this Account

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Address|path|string|true|Account address
block|query|integer|false|Return mined blocks begining from Block number
previous|query|boolean|false|When set to true, returns transactions Previous to the specified block number and transaction index


> Example responses

```json
{
  "First": true,
  "Limit": 8813805051874942000,
  "Result": [
    {
      "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
      "CreationTime": 7052733826006029000,
      "Difficulty": "Sit aut.",
      "ExtraData": "Molestiae quidem.",
      "GasLimit": "Aut molestias magnam sunt doloremque.",
      "GasUsed": "Qui aut.",
      "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
      "LogsBloom": "Vel consequatur reprehenderit id neque.",
      "MinedInSeconds": 7897712511802021000,
      "Miner": "Autem veritatis repudiandae.",
      "MixHash": "Officia ad aut dolores.",
      "Network": "Aut tempora enim sit corporis esse nihil.",
      "Nonce": "Omnis et similique.",
      "Number": 8737398717635499000,
      "ParentHash": "Optio iure vel libero earum vitae et.",
      "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
      "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
      "Size": "Aliquid quia.",
      "StateRoot": "Eos harum.",
      "Timestamp": 7483662194381612000,
      "TotalDifficulty": "Distinctio architecto perferendis quae.",
      "TransactionCount": 1234215781114073300,
      "TransactionFees": "Sunt doloremque ex quasi aut quo.",
      "Transactions": {
        "First": false,
        "Limit": 7551599146550128000,
        "MessagesIncluded": true,
        "Result": [
          {
            "BlockHash": "Voluptatem laboriosam quidem.",
            "BlockNumber": 2775752852696174000,
            "Confirmations": 6532019680679138000,
            "ContractCodes": {
              "Sint deleniti est est quibusdam et quis.": {
                "ABI": "Eum quos.",
                "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                "Verified": false
              }
            },
            "ContractCreation": true,
            "Error": "Aut vel minus molestiae aut aliquam.",
            "Events": [
              {
                "Address": "Rerum dolorum sit aut sit.",
                "Data": "Vel in consequatur odio numquam ut.",
                "Index": 2440912512905109500,
                "Topics": [
                  "Voluptatem enim ducimus et."
                ],
                "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
              }
            ],
            "From": "Tempore voluptates voluptas aut.",
            "Gas": "Qui aut provident et neque.",
            "GasPrice": "Esse labore quo non consequatur quis molestiae.",
            "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
            "Hash": "Dolorum unde est omnis velit assumenda.",
            "Index": 9096248114404918000,
            "Input": "In distinctio doloremque magni totam possimus.",
            "Messages": [
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              },
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              }
            ],
            "Network": "Qui culpa quis laudantium molestias consequatur.",
            "Nonce": "Voluptatem magnam ea.",
            "Output": "Dicta velit debitis ea temporibus nemo.",
            "Timestamp": 4092050381628505000,
            "To": "Accusantium neque debitis numquam molestiae aut.",
            "Value": "Blanditiis est ex quos distinctio eligendi totam."
          }
        ]
      },
      "UncleReward": "Tempore voluptatem neque nisi est.",
      "Uncles": [
        "Dicta aspernatur.",
        "Dicta aspernatur.",
        "Dicta aspernatur."
      ]
    },
    {
      "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
      "CreationTime": 7052733826006029000,
      "Difficulty": "Sit aut.",
      "ExtraData": "Molestiae quidem.",
      "GasLimit": "Aut molestias magnam sunt doloremque.",
      "GasUsed": "Qui aut.",
      "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
      "LogsBloom": "Vel consequatur reprehenderit id neque.",
      "MinedInSeconds": 7897712511802021000,
      "Miner": "Autem veritatis repudiandae.",
      "MixHash": "Officia ad aut dolores.",
      "Network": "Aut tempora enim sit corporis esse nihil.",
      "Nonce": "Omnis et similique.",
      "Number": 8737398717635499000,
      "ParentHash": "Optio iure vel libero earum vitae et.",
      "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
      "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
      "Size": "Aliquid quia.",
      "StateRoot": "Eos harum.",
      "Timestamp": 7483662194381612000,
      "TotalDifficulty": "Distinctio architecto perferendis quae.",
      "TransactionCount": 1234215781114073300,
      "TransactionFees": "Sunt doloremque ex quasi aut quo.",
      "Transactions": {
        "First": false,
        "Limit": 7551599146550128000,
        "MessagesIncluded": true,
        "Result": [
          {
            "BlockHash": "Voluptatem laboriosam quidem.",
            "BlockNumber": 2775752852696174000,
            "Confirmations": 6532019680679138000,
            "ContractCodes": {
              "Sint deleniti est est quibusdam et quis.": {
                "ABI": "Eum quos.",
                "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                "Verified": false
              }
            },
            "ContractCreation": true,
            "Error": "Aut vel minus molestiae aut aliquam.",
            "Events": [
              {
                "Address": "Rerum dolorum sit aut sit.",
                "Data": "Vel in consequatur odio numquam ut.",
                "Index": 2440912512905109500,
                "Topics": [
                  "Voluptatem enim ducimus et."
                ],
                "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
              }
            ],
            "From": "Tempore voluptates voluptas aut.",
            "Gas": "Qui aut provident et neque.",
            "GasPrice": "Esse labore quo non consequatur quis molestiae.",
            "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
            "Hash": "Dolorum unde est omnis velit assumenda.",
            "Index": 9096248114404918000,
            "Input": "In distinctio doloremque magni totam possimus.",
            "Messages": [
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              },
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              }
            ],
            "Network": "Qui culpa quis laudantium molestias consequatur.",
            "Nonce": "Voluptatem magnam ea.",
            "Output": "Dicta velit debitis ea temporibus nemo.",
            "Timestamp": 4092050381628505000,
            "To": "Accusantium neque debitis numquam molestiae aut.",
            "Value": "Blanditiis est ex quos distinctio eligendi totam."
          }
        ]
      },
      "UncleReward": "Tempore voluptatem neque nisi est.",
      "Uncles": [
        "Dicta aspernatur.",
        "Dicta aspernatur.",
        "Dicta aspernatur."
      ]
    }
  ],
  "TotalRecords": 7269848697550577000
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<First>true</First>
<Limit>8813805051874942000</Limit>
<Result>
  <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
  <CreationTime>7052733826006029000</CreationTime>
  <Difficulty>Sit aut.</Difficulty>
  <ExtraData>Molestiae quidem.</ExtraData>
  <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
  <GasUsed>Qui aut.</GasUsed>
  <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
  <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
  <MinedInSeconds>7897712511802021000</MinedInSeconds>
  <Miner>Autem veritatis repudiandae.</Miner>
  <MixHash>Officia ad aut dolores.</MixHash>
  <Network>Aut tempora enim sit corporis esse nihil.</Network>
  <Nonce>Omnis et similique.</Nonce>
  <Number>8737398717635499000</Number>
  <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
  <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
  <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
  <Size>Aliquid quia.</Size>
  <StateRoot>Eos harum.</StateRoot>
  <Timestamp>7483662194381612000</Timestamp>
  <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
  <TransactionCount>1234215781114073300</TransactionCount>
  <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
  <Transactions>
    <First>false</First>
    <Limit>7551599146550128000</Limit>
    <MessagesIncluded>true</MessagesIncluded>
    <Result>
      <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
      <BlockNumber>2775752852696174000</BlockNumber>
      <Confirmations>6532019680679138000</Confirmations>
      <ContractCodes>
        <Sint deleniti est est quibusdam et quis.>
          <ABI>Eum quos.</ABI>
          <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
          <Verified>false</Verified>
        </Sint deleniti est est quibusdam et quis.>
      </ContractCodes>
      <ContractCreation>true</ContractCreation>
      <Error>Aut vel minus molestiae aut aliquam.</Error>
      <Events>
        <Address>Rerum dolorum sit aut sit.</Address>
        <Data>Vel in consequatur odio numquam ut.</Data>
        <Index>2440912512905109500</Index>
        <Topics>Voluptatem enim ducimus et.</Topics>
        <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
      </Events>
      <From>Tempore voluptates voluptas aut.</From>
      <Gas>Qui aut provident et neque.</Gas>
      <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
      <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
      <Hash>Dolorum unde est omnis velit assumenda.</Hash>
      <Index>9096248114404918000</Index>
      <Input>In distinctio doloremque magni totam possimus.</Input>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Network>Qui culpa quis laudantium molestias consequatur.</Network>
      <Nonce>Voluptatem magnam ea.</Nonce>
      <Output>Dicta velit debitis ea temporibus nemo.</Output>
      <Timestamp>4092050381628505000</Timestamp>
      <To>Accusantium neque debitis numquam molestiae aut.</To>
      <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
    </Result>
  </Transactions>
  <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
</Result>
<Result>
  <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
  <CreationTime>7052733826006029000</CreationTime>
  <Difficulty>Sit aut.</Difficulty>
  <ExtraData>Molestiae quidem.</ExtraData>
  <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
  <GasUsed>Qui aut.</GasUsed>
  <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
  <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
  <MinedInSeconds>7897712511802021000</MinedInSeconds>
  <Miner>Autem veritatis repudiandae.</Miner>
  <MixHash>Officia ad aut dolores.</MixHash>
  <Network>Aut tempora enim sit corporis esse nihil.</Network>
  <Nonce>Omnis et similique.</Nonce>
  <Number>8737398717635499000</Number>
  <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
  <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
  <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
  <Size>Aliquid quia.</Size>
  <StateRoot>Eos harum.</StateRoot>
  <Timestamp>7483662194381612000</Timestamp>
  <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
  <TransactionCount>1234215781114073300</TransactionCount>
  <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
  <Transactions>
    <First>false</First>
    <Limit>7551599146550128000</Limit>
    <MessagesIncluded>true</MessagesIncluded>
    <Result>
      <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
      <BlockNumber>2775752852696174000</BlockNumber>
      <Confirmations>6532019680679138000</Confirmations>
      <ContractCodes>
        <Sint deleniti est est quibusdam et quis.>
          <ABI>Eum quos.</ABI>
          <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
          <Verified>false</Verified>
        </Sint deleniti est est quibusdam et quis.>
      </ContractCodes>
      <ContractCreation>true</ContractCreation>
      <Error>Aut vel minus molestiae aut aliquam.</Error>
      <Events>
        <Address>Rerum dolorum sit aut sit.</Address>
        <Data>Vel in consequatur odio numquam ut.</Data>
        <Index>2440912512905109500</Index>
        <Topics>Voluptatem enim ducimus et.</Topics>
        <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
      </Events>
      <From>Tempore voluptates voluptas aut.</From>
      <Gas>Qui aut provident et neque.</Gas>
      <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
      <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
      <Hash>Dolorum unde est omnis velit assumenda.</Hash>
      <Index>9096248114404918000</Index>
      <Input>In distinctio doloremque magni totam possimus.</Input>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Network>Qui culpa quis laudantium molestias consequatur.</Network>
      <Nonce>Voluptatem magnam ea.</Nonce>
      <Output>Dicta velit debitis ea temporibus nemo.</Output>
      <Timestamp>4092050381628505000</Timestamp>
      <To>Accusantium neque debitis numquam molestiae aut.</To>
      <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
    </Result>
  </Transactions>
  <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
</Result>
<TotalRecords>7269848697550577000</TotalRecords>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbBlocks](#schemaethdbblocks)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

## Account#mined_uncles

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/account/{Address}/mined_uncles \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/account/{Address}/mined_uncles HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/account/{Address}/mined_uncles',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/account/{Address}/mined_uncles',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/account/{Address}/mined_uncles',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/account/{Address}/mined_uncles', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/account/{Address}/mined_uncles");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /account/{Address}/mined_uncles`

*mined_uncles Account*

Returns list of blocks mined by this Account

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Address|path|string|true|Account address
block|query|integer|false|Return mined uncles begining from Block number
previous|query|boolean|false|When set to true, returns transactions Previous to the specified block number and transaction index


> Example responses

```json
{
  "First": true,
  "Limit": 6916214044123517000,
  "Result": [
    {
      "BeneficiaryReward": "Mollitia omnis necessitatibus et.",
      "BlockNumber": 6948539910358115000,
      "CreationTime": 2533265886652186000,
      "Difficulty": "Eaque saepe.",
      "ExtraData": "Voluptate expedita saepe voluptates.",
      "GasLimit": "Eius est ea odit repellat est.",
      "Hash": "Asperiores et facere nostrum omnis consequuntur.",
      "Index": 4134083501788099000,
      "LogsBloom": "Ut nihil ipsam alias debitis qui.",
      "Miner": "Ea quasi assumenda.",
      "MixHash": "Ducimus maiores beatae.",
      "Nonce": "Molestiae suscipit quam dolore sit eum.",
      "Number": 7066559540085266000,
      "ParentHash": "Consectetur excepturi molestias quibusdam autem incidunt fugiat.",
      "ReceiptsRoot": "Itaque accusantium sunt.",
      "SHA3Uncles": "Architecto modi.",
      "Size": "Laudantium totam consectetur nihil repudiandae.",
      "StateRoot": "Provident facere consequatur explicabo est voluptatem.",
      "TotalDifficulty": "Voluptatibus dolorem."
    }
  ],
  "TotalRecords": 2078329725000681500
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<First>true</First>
<Limit>6916214044123517000</Limit>
<Result>
  <BeneficiaryReward>Mollitia omnis necessitatibus et.</BeneficiaryReward>
  <BlockNumber>6948539910358115000</BlockNumber>
  <CreationTime>2533265886652186000</CreationTime>
  <Difficulty>Eaque saepe.</Difficulty>
  <ExtraData>Voluptate expedita saepe voluptates.</ExtraData>
  <GasLimit>Eius est ea odit repellat est.</GasLimit>
  <Hash>Asperiores et facere nostrum omnis consequuntur.</Hash>
  <Index>4134083501788099000</Index>
  <LogsBloom>Ut nihil ipsam alias debitis qui.</LogsBloom>
  <Miner>Ea quasi assumenda.</Miner>
  <MixHash>Ducimus maiores beatae.</MixHash>
  <Nonce>Molestiae suscipit quam dolore sit eum.</Nonce>
  <Number>7066559540085266000</Number>
  <ParentHash>Consectetur excepturi molestias quibusdam autem incidunt fugiat.</ParentHash>
  <ReceiptsRoot>Itaque accusantium sunt.</ReceiptsRoot>
  <SHA3Uncles>Architecto modi.</SHA3Uncles>
  <Size>Laudantium totam consectetur nihil repudiandae.</Size>
  <StateRoot>Provident facere consequatur explicabo est voluptatem.</StateRoot>
  <TotalDifficulty>Voluptatibus dolorem.</TotalDifficulty>
</Result>
<TotalRecords>2078329725000681500</TotalRecords>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbUncles](#schemaethdbuncles)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

## Account#transactions

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/account/{Address}/transactions \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/account/{Address}/transactions HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/account/{Address}/transactions',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/account/{Address}/transactions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/account/{Address}/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/account/{Address}/transactions', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/account/{Address}/transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /account/{Address}/transactions`

*transactions Account*

Returns list of transactions with the From or To fields matching Address

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Address|path|string|true|Account address
block|query|integer|false|Return transactions begining from Block number. Defaults to latest block if not specified
internals|query|boolean|false|Include transaction messages (internal transactions) in results
previous|query|boolean|false|When set to true, returns transactions Previous to the specified block number and transaction index
txindex|query|integer|false|Return transactions after transaction index in Block


> Example responses

```json
{
  "First": false,
  "Limit": 7551599146550128000,
  "MessagesIncluded": true,
  "Result": [
    {
      "BlockHash": "Voluptatem laboriosam quidem.",
      "BlockNumber": 2775752852696174000,
      "Confirmations": 6532019680679138000,
      "ContractCodes": {
        "Sint deleniti est est quibusdam et quis.": {
          "ABI": "Eum quos.",
          "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
          "Verified": false
        }
      },
      "ContractCreation": true,
      "Error": "Aut vel minus molestiae aut aliquam.",
      "Events": [
        {
          "Address": "Rerum dolorum sit aut sit.",
          "Data": "Vel in consequatur odio numquam ut.",
          "Index": 2440912512905109500,
          "Topics": [
            "Voluptatem enim ducimus et."
          ],
          "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
        }
      ],
      "From": "Tempore voluptates voluptas aut.",
      "Gas": "Qui aut provident et neque.",
      "GasPrice": "Esse labore quo non consequatur quis molestiae.",
      "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
      "Hash": "Dolorum unde est omnis velit assumenda.",
      "Index": 9096248114404918000,
      "Input": "In distinctio doloremque magni totam possimus.",
      "Messages": [
        {
          "Error": "Quo culpa voluptatem.",
          "From": "Quo optio.",
          "Gas": "Eum in a libero esse voluptas aut.",
          "GasUsed": "Sit fugit molestiae.",
          "Input": "Et soluta.",
          "Nonce": "Odit sunt.",
          "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
          "To": "Dolor temporibus placeat.",
          "Value": "Nisi a consequatur nulla saepe voluptas."
        },
        {
          "Error": "Quo culpa voluptatem.",
          "From": "Quo optio.",
          "Gas": "Eum in a libero esse voluptas aut.",
          "GasUsed": "Sit fugit molestiae.",
          "Input": "Et soluta.",
          "Nonce": "Odit sunt.",
          "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
          "To": "Dolor temporibus placeat.",
          "Value": "Nisi a consequatur nulla saepe voluptas."
        }
      ],
      "Network": "Qui culpa quis laudantium molestias consequatur.",
      "Nonce": "Voluptatem magnam ea.",
      "Output": "Dicta velit debitis ea temporibus nemo.",
      "Timestamp": 4092050381628505000,
      "To": "Accusantium neque debitis numquam molestiae aut.",
      "Value": "Blanditiis est ex quos distinctio eligendi totam."
    }
  ]
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<First>false</First>
<Limit>7551599146550128000</Limit>
<MessagesIncluded>true</MessagesIncluded>
<Result>
  <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
  <BlockNumber>2775752852696174000</BlockNumber>
  <Confirmations>6532019680679138000</Confirmations>
  <ContractCodes>
    <Sint deleniti est est quibusdam et quis.>
      <ABI>Eum quos.</ABI>
      <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
      <Verified>false</Verified>
    </Sint deleniti est est quibusdam et quis.>
  </ContractCodes>
  <ContractCreation>true</ContractCreation>
  <Error>Aut vel minus molestiae aut aliquam.</Error>
  <Events>
    <Address>Rerum dolorum sit aut sit.</Address>
    <Data>Vel in consequatur odio numquam ut.</Data>
    <Index>2440912512905109500</Index>
    <Topics>Voluptatem enim ducimus et.</Topics>
    <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
  </Events>
  <From>Tempore voluptates voluptas aut.</From>
  <Gas>Qui aut provident et neque.</Gas>
  <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
  <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
  <Hash>Dolorum unde est omnis velit assumenda.</Hash>
  <Index>9096248114404918000</Index>
  <Input>In distinctio doloremque magni totam possimus.</Input>
  <Messages>
    <Error>Quo culpa voluptatem.</Error>
    <From>Quo optio.</From>
    <Gas>Eum in a libero esse voluptas aut.</Gas>
    <GasUsed>Sit fugit molestiae.</GasUsed>
    <Input>Et soluta.</Input>
    <Nonce>Odit sunt.</Nonce>
    <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
    <To>Dolor temporibus placeat.</To>
    <Value>Nisi a consequatur nulla saepe voluptas.</Value>
  </Messages>
  <Messages>
    <Error>Quo culpa voluptatem.</Error>
    <From>Quo optio.</From>
    <Gas>Eum in a libero esse voluptas aut.</Gas>
    <GasUsed>Sit fugit molestiae.</GasUsed>
    <Input>Et soluta.</Input>
    <Nonce>Odit sunt.</Nonce>
    <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
    <To>Dolor temporibus placeat.</To>
    <Value>Nisi a consequatur nulla saepe voluptas.</Value>
  </Messages>
  <Network>Qui culpa quis laudantium molestias consequatur.</Network>
  <Nonce>Voluptatem magnam ea.</Nonce>
  <Output>Dicta velit debitis ea temporibus nemo.</Output>
  <Timestamp>4092050381628505000</Timestamp>
  <To>Accusantium neque debitis numquam molestiae aut.</To>
  <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
</Result>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbTransactions](#schemaethdbtransactions)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

# Block

## Block#show

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/block/{HashOrHeight} \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/block/{HashOrHeight} HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/block/{HashOrHeight}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/block/{HashOrHeight}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/block/{HashOrHeight}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/block/{HashOrHeight}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/block/{HashOrHeight}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /block/{HashOrHeight}`

*show Block*

Retuns Block information

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
HashOrHeight|path|string|true|Block hash or height


> Example responses

```json
{
  "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
  "CreationTime": 7052733826006029000,
  "Difficulty": "Sit aut.",
  "ExtraData": "Molestiae quidem.",
  "GasLimit": "Aut molestias magnam sunt doloremque.",
  "GasUsed": "Qui aut.",
  "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
  "LogsBloom": "Vel consequatur reprehenderit id neque.",
  "MinedInSeconds": 7897712511802021000,
  "Miner": "Autem veritatis repudiandae.",
  "MixHash": "Officia ad aut dolores.",
  "Network": "Aut tempora enim sit corporis esse nihil.",
  "Nonce": "Omnis et similique.",
  "Number": 8737398717635499000,
  "ParentHash": "Optio iure vel libero earum vitae et.",
  "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
  "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
  "Size": "Aliquid quia.",
  "StateRoot": "Eos harum.",
  "Timestamp": 7483662194381612000,
  "TotalDifficulty": "Distinctio architecto perferendis quae.",
  "TransactionCount": 1234215781114073300,
  "TransactionFees": "Sunt doloremque ex quasi aut quo.",
  "Transactions": {
    "First": false,
    "Limit": 7551599146550128000,
    "MessagesIncluded": true,
    "Result": [
      {
        "BlockHash": "Voluptatem laboriosam quidem.",
        "BlockNumber": 2775752852696174000,
        "Confirmations": 6532019680679138000,
        "ContractCodes": {
          "Sint deleniti est est quibusdam et quis.": {
            "ABI": "Eum quos.",
            "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
            "Verified": false
          }
        },
        "ContractCreation": true,
        "Error": "Aut vel minus molestiae aut aliquam.",
        "Events": [
          {
            "Address": "Rerum dolorum sit aut sit.",
            "Data": "Vel in consequatur odio numquam ut.",
            "Index": 2440912512905109500,
            "Topics": [
              "Voluptatem enim ducimus et."
            ],
            "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
          }
        ],
        "From": "Tempore voluptates voluptas aut.",
        "Gas": "Qui aut provident et neque.",
        "GasPrice": "Esse labore quo non consequatur quis molestiae.",
        "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
        "Hash": "Dolorum unde est omnis velit assumenda.",
        "Index": 9096248114404918000,
        "Input": "In distinctio doloremque magni totam possimus.",
        "Messages": [
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          },
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          }
        ],
        "Network": "Qui culpa quis laudantium molestias consequatur.",
        "Nonce": "Voluptatem magnam ea.",
        "Output": "Dicta velit debitis ea temporibus nemo.",
        "Timestamp": 4092050381628505000,
        "To": "Accusantium neque debitis numquam molestiae aut.",
        "Value": "Blanditiis est ex quos distinctio eligendi totam."
      }
    ]
  },
  "UncleReward": "Tempore voluptatem neque nisi est.",
  "Uncles": [
    "Dicta aspernatur.",
    "Dicta aspernatur.",
    "Dicta aspernatur."
  ]
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
<CreationTime>7052733826006029000</CreationTime>
<Difficulty>Sit aut.</Difficulty>
<ExtraData>Molestiae quidem.</ExtraData>
<GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
<GasUsed>Qui aut.</GasUsed>
<Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
<LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
<MinedInSeconds>7897712511802021000</MinedInSeconds>
<Miner>Autem veritatis repudiandae.</Miner>
<MixHash>Officia ad aut dolores.</MixHash>
<Network>Aut tempora enim sit corporis esse nihil.</Network>
<Nonce>Omnis et similique.</Nonce>
<Number>8737398717635499000</Number>
<ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
<ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
<SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
<Size>Aliquid quia.</Size>
<StateRoot>Eos harum.</StateRoot>
<Timestamp>7483662194381612000</Timestamp>
<TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
<TransactionCount>1234215781114073300</TransactionCount>
<TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
<Transactions>
  <First>false</First>
  <Limit>7551599146550128000</Limit>
  <MessagesIncluded>true</MessagesIncluded>
  <Result>
    <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
    <BlockNumber>2775752852696174000</BlockNumber>
    <Confirmations>6532019680679138000</Confirmations>
    <ContractCodes>
      <Sint deleniti est est quibusdam et quis.>
        <ABI>Eum quos.</ABI>
        <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
        <Verified>false</Verified>
      </Sint deleniti est est quibusdam et quis.>
    </ContractCodes>
    <ContractCreation>true</ContractCreation>
    <Error>Aut vel minus molestiae aut aliquam.</Error>
    <Events>
      <Address>Rerum dolorum sit aut sit.</Address>
      <Data>Vel in consequatur odio numquam ut.</Data>
      <Index>2440912512905109500</Index>
      <Topics>Voluptatem enim ducimus et.</Topics>
      <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
    </Events>
    <From>Tempore voluptates voluptas aut.</From>
    <Gas>Qui aut provident et neque.</Gas>
    <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
    <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
    <Hash>Dolorum unde est omnis velit assumenda.</Hash>
    <Index>9096248114404918000</Index>
    <Input>In distinctio doloremque magni totam possimus.</Input>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Network>Qui culpa quis laudantium molestias consequatur.</Network>
    <Nonce>Voluptatem magnam ea.</Nonce>
    <Output>Dicta velit debitis ea temporibus nemo.</Output>
    <Timestamp>4092050381628505000</Timestamp>
    <To>Accusantium neque debitis numquam molestiae aut.</To>
    <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
  </Result>
</Transactions>
<UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
<Uncles>Dicta aspernatur.</Uncles>
<Uncles>Dicta aspernatur.</Uncles>
<Uncles>Dicta aspernatur.</Uncles>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbBlock](#schemaethdbblock)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

# Networks

## Networks#list

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/networks \
  -H 'Accept: application/vnd.ethdb.network+json; type=collection'

```

```http
GET http://localhost:3001/api/v1/networks HTTP/1.1
Host: localhost:3001

Accept: application/vnd.ethdb.network+json; type=collection

```

```javascript
var headers = {
  'Accept':'application/vnd.ethdb.network+json; type=collection'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/networks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.ethdb.network+json; type=collection'

};

fetch('http://localhost:3001/api/v1/networks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.ethdb.network+json; type=collection'
}

result = RestClient.get 'http://localhost:3001/api/v1/networks',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.ethdb.network+json; type=collection'
}

r = requests.get('http://localhost:3001/api/v1/networks', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/networks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /networks`

*list Networks*

Retuns a list of supported Ethereum networks

> Example responses

```json
[
  {
    "BlockHeight": 2249756891723881000,
    "BlockReward": "Facere consequatur numquam labore.",
    "Blocks": {
      "First": true,
      "Limit": 8813805051874942000,
      "Result": [
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        },
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        }
      ],
      "TotalRecords": 7269848697550577000
    },
    "Difficulty": "Maiores aut dolorem.",
    "GasLimit": "Nulla eligendi libero modi et et iusto.",
    "GenesisHash": "Fugit harum deleniti.",
    "HashRate": "Quam ut unde et.",
    "ID": "Quas voluptas nostrum quos.",
    "Name": "Voluptatem voluptas autem earum quaerat similique sint.",
    "PendingTransactions": {
      "First": false,
      "Limit": 7551599146550128000,
      "MessagesIncluded": true,
      "Result": [
        {
          "BlockHash": "Voluptatem laboriosam quidem.",
          "BlockNumber": 2775752852696174000,
          "Confirmations": 6532019680679138000,
          "ContractCodes": {
            "Sint deleniti est est quibusdam et quis.": {
              "ABI": "Eum quos.",
              "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
              "Verified": false
            }
          },
          "ContractCreation": true,
          "Error": "Aut vel minus molestiae aut aliquam.",
          "Events": [
            {
              "Address": "Rerum dolorum sit aut sit.",
              "Data": "Vel in consequatur odio numquam ut.",
              "Index": 2440912512905109500,
              "Topics": [
                "Voluptatem enim ducimus et."
              ],
              "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
            }
          ],
          "From": "Tempore voluptates voluptas aut.",
          "Gas": "Qui aut provident et neque.",
          "GasPrice": "Esse labore quo non consequatur quis molestiae.",
          "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
          "Hash": "Dolorum unde est omnis velit assumenda.",
          "Index": 9096248114404918000,
          "Input": "In distinctio doloremque magni totam possimus.",
          "Messages": [
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            },
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            }
          ],
          "Network": "Qui culpa quis laudantium molestias consequatur.",
          "Nonce": "Voluptatem magnam ea.",
          "Output": "Dicta velit debitis ea temporibus nemo.",
          "Timestamp": 4092050381628505000,
          "To": "Accusantium neque debitis numquam molestiae aut.",
          "Value": "Blanditiis est ex quos distinctio eligendi totam."
        }
      ]
    }
  },
  {
    "BlockHeight": 2249756891723881000,
    "BlockReward": "Facere consequatur numquam labore.",
    "Blocks": {
      "First": true,
      "Limit": 8813805051874942000,
      "Result": [
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        },
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        }
      ],
      "TotalRecords": 7269848697550577000
    },
    "Difficulty": "Maiores aut dolorem.",
    "GasLimit": "Nulla eligendi libero modi et et iusto.",
    "GenesisHash": "Fugit harum deleniti.",
    "HashRate": "Quam ut unde et.",
    "ID": "Quas voluptas nostrum quos.",
    "Name": "Voluptatem voluptas autem earum quaerat similique sint.",
    "PendingTransactions": {
      "First": false,
      "Limit": 7551599146550128000,
      "MessagesIncluded": true,
      "Result": [
        {
          "BlockHash": "Voluptatem laboriosam quidem.",
          "BlockNumber": 2775752852696174000,
          "Confirmations": 6532019680679138000,
          "ContractCodes": {
            "Sint deleniti est est quibusdam et quis.": {
              "ABI": "Eum quos.",
              "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
              "Verified": false
            }
          },
          "ContractCreation": true,
          "Error": "Aut vel minus molestiae aut aliquam.",
          "Events": [
            {
              "Address": "Rerum dolorum sit aut sit.",
              "Data": "Vel in consequatur odio numquam ut.",
              "Index": 2440912512905109500,
              "Topics": [
                "Voluptatem enim ducimus et."
              ],
              "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
            }
          ],
          "From": "Tempore voluptates voluptas aut.",
          "Gas": "Qui aut provident et neque.",
          "GasPrice": "Esse labore quo non consequatur quis molestiae.",
          "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
          "Hash": "Dolorum unde est omnis velit assumenda.",
          "Index": 9096248114404918000,
          "Input": "In distinctio doloremque magni totam possimus.",
          "Messages": [
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            },
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            }
          ],
          "Network": "Qui culpa quis laudantium molestias consequatur.",
          "Nonce": "Voluptatem magnam ea.",
          "Output": "Dicta velit debitis ea temporibus nemo.",
          "Timestamp": 4092050381628505000,
          "To": "Accusantium neque debitis numquam molestiae aut.",
          "Value": "Blanditiis est ex quos distinctio eligendi totam."
        }
      ]
    }
  }
]
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<BlockHeight>2249756891723881000</BlockHeight>
<BlockReward>Facere consequatur numquam labore.</BlockReward>
<Blocks>
  <First>true</First>
  <Limit>8813805051874942000</Limit>
  <Result>
    <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
    <CreationTime>7052733826006029000</CreationTime>
    <Difficulty>Sit aut.</Difficulty>
    <ExtraData>Molestiae quidem.</ExtraData>
    <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
    <GasUsed>Qui aut.</GasUsed>
    <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
    <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
    <MinedInSeconds>7897712511802021000</MinedInSeconds>
    <Miner>Autem veritatis repudiandae.</Miner>
    <MixHash>Officia ad aut dolores.</MixHash>
    <Network>Aut tempora enim sit corporis esse nihil.</Network>
    <Nonce>Omnis et similique.</Nonce>
    <Number>8737398717635499000</Number>
    <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
    <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
    <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
    <Size>Aliquid quia.</Size>
    <StateRoot>Eos harum.</StateRoot>
    <Timestamp>7483662194381612000</Timestamp>
    <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
    <TransactionCount>1234215781114073300</TransactionCount>
    <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
    <Transactions>
      <First>false</First>
      <Limit>7551599146550128000</Limit>
      <MessagesIncluded>true</MessagesIncluded>
      <Result>
        <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
        <BlockNumber>2775752852696174000</BlockNumber>
        <Confirmations>6532019680679138000</Confirmations>
        <ContractCodes>
          <Sint deleniti est est quibusdam et quis.>
            <ABI>Eum quos.</ABI>
            <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
            <Verified>false</Verified>
          </Sint deleniti est est quibusdam et quis.>
        </ContractCodes>
        <ContractCreation>true</ContractCreation>
        <Error>Aut vel minus molestiae aut aliquam.</Error>
        <Events>
          <Address>Rerum dolorum sit aut sit.</Address>
          <Data>Vel in consequatur odio numquam ut.</Data>
          <Index>2440912512905109500</Index>
          <Topics>Voluptatem enim ducimus et.</Topics>
          <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
        </Events>
        <From>Tempore voluptates voluptas aut.</From>
        <Gas>Qui aut provident et neque.</Gas>
        <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
        <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
        <Hash>Dolorum unde est omnis velit assumenda.</Hash>
        <Index>9096248114404918000</Index>
        <Input>In distinctio doloremque magni totam possimus.</Input>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Network>Qui culpa quis laudantium molestias consequatur.</Network>
        <Nonce>Voluptatem magnam ea.</Nonce>
        <Output>Dicta velit debitis ea temporibus nemo.</Output>
        <Timestamp>4092050381628505000</Timestamp>
        <To>Accusantium neque debitis numquam molestiae aut.</To>
        <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
      </Result>
    </Transactions>
    <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
  </Result>
  <Result>
    <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
    <CreationTime>7052733826006029000</CreationTime>
    <Difficulty>Sit aut.</Difficulty>
    <ExtraData>Molestiae quidem.</ExtraData>
    <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
    <GasUsed>Qui aut.</GasUsed>
    <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
    <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
    <MinedInSeconds>7897712511802021000</MinedInSeconds>
    <Miner>Autem veritatis repudiandae.</Miner>
    <MixHash>Officia ad aut dolores.</MixHash>
    <Network>Aut tempora enim sit corporis esse nihil.</Network>
    <Nonce>Omnis et similique.</Nonce>
    <Number>8737398717635499000</Number>
    <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
    <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
    <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
    <Size>Aliquid quia.</Size>
    <StateRoot>Eos harum.</StateRoot>
    <Timestamp>7483662194381612000</Timestamp>
    <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
    <TransactionCount>1234215781114073300</TransactionCount>
    <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
    <Transactions>
      <First>false</First>
      <Limit>7551599146550128000</Limit>
      <MessagesIncluded>true</MessagesIncluded>
      <Result>
        <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
        <BlockNumber>2775752852696174000</BlockNumber>
        <Confirmations>6532019680679138000</Confirmations>
        <ContractCodes>
          <Sint deleniti est est quibusdam et quis.>
            <ABI>Eum quos.</ABI>
            <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
            <Verified>false</Verified>
          </Sint deleniti est est quibusdam et quis.>
        </ContractCodes>
        <ContractCreation>true</ContractCreation>
        <Error>Aut vel minus molestiae aut aliquam.</Error>
        <Events>
          <Address>Rerum dolorum sit aut sit.</Address>
          <Data>Vel in consequatur odio numquam ut.</Data>
          <Index>2440912512905109500</Index>
          <Topics>Voluptatem enim ducimus et.</Topics>
          <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
        </Events>
        <From>Tempore voluptates voluptas aut.</From>
        <Gas>Qui aut provident et neque.</Gas>
        <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
        <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
        <Hash>Dolorum unde est omnis velit assumenda.</Hash>
        <Index>9096248114404918000</Index>
        <Input>In distinctio doloremque magni totam possimus.</Input>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Network>Qui culpa quis laudantium molestias consequatur.</Network>
        <Nonce>Voluptatem magnam ea.</Nonce>
        <Output>Dicta velit debitis ea temporibus nemo.</Output>
        <Timestamp>4092050381628505000</Timestamp>
        <To>Accusantium neque debitis numquam molestiae aut.</To>
        <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
      </Result>
    </Transactions>
    <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
  </Result>
  <TotalRecords>7269848697550577000</TotalRecords>
</Blocks>
<Difficulty>Maiores aut dolorem.</Difficulty>
<GasLimit>Nulla eligendi libero modi et et iusto.</GasLimit>
<GenesisHash>Fugit harum deleniti.</GenesisHash>
<HashRate>Quam ut unde et.</HashRate>
<ID>Quas voluptas nostrum quos.</ID>
<Name>Voluptatem voluptas autem earum quaerat similique sint.</Name>
<PendingTransactions>
  <First>false</First>
  <Limit>7551599146550128000</Limit>
  <MessagesIncluded>true</MessagesIncluded>
  <Result>
    <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
    <BlockNumber>2775752852696174000</BlockNumber>
    <Confirmations>6532019680679138000</Confirmations>
    <ContractCodes>
      <Sint deleniti est est quibusdam et quis.>
        <ABI>Eum quos.</ABI>
        <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
        <Verified>false</Verified>
      </Sint deleniti est est quibusdam et quis.>
    </ContractCodes>
    <ContractCreation>true</ContractCreation>
    <Error>Aut vel minus molestiae aut aliquam.</Error>
    <Events>
      <Address>Rerum dolorum sit aut sit.</Address>
      <Data>Vel in consequatur odio numquam ut.</Data>
      <Index>2440912512905109500</Index>
      <Topics>Voluptatem enim ducimus et.</Topics>
      <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
    </Events>
    <From>Tempore voluptates voluptas aut.</From>
    <Gas>Qui aut provident et neque.</Gas>
    <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
    <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
    <Hash>Dolorum unde est omnis velit assumenda.</Hash>
    <Index>9096248114404918000</Index>
    <Input>In distinctio doloremque magni totam possimus.</Input>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Network>Qui culpa quis laudantium molestias consequatur.</Network>
    <Nonce>Voluptatem magnam ea.</Nonce>
    <Output>Dicta velit debitis ea temporibus nemo.</Output>
    <Timestamp>4092050381628505000</Timestamp>
    <To>Accusantium neque debitis numquam molestiae aut.</To>
    <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
  </Result>
</PendingTransactions>
<BlockHeight>2249756891723881000</BlockHeight>
<BlockReward>Facere consequatur numquam labore.</BlockReward>
<Blocks>
  <First>true</First>
  <Limit>8813805051874942000</Limit>
  <Result>
    <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
    <CreationTime>7052733826006029000</CreationTime>
    <Difficulty>Sit aut.</Difficulty>
    <ExtraData>Molestiae quidem.</ExtraData>
    <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
    <GasUsed>Qui aut.</GasUsed>
    <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
    <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
    <MinedInSeconds>7897712511802021000</MinedInSeconds>
    <Miner>Autem veritatis repudiandae.</Miner>
    <MixHash>Officia ad aut dolores.</MixHash>
    <Network>Aut tempora enim sit corporis esse nihil.</Network>
    <Nonce>Omnis et similique.</Nonce>
    <Number>8737398717635499000</Number>
    <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
    <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
    <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
    <Size>Aliquid quia.</Size>
    <StateRoot>Eos harum.</StateRoot>
    <Timestamp>7483662194381612000</Timestamp>
    <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
    <TransactionCount>1234215781114073300</TransactionCount>
    <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
    <Transactions>
      <First>false</First>
      <Limit>7551599146550128000</Limit>
      <MessagesIncluded>true</MessagesIncluded>
      <Result>
        <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
        <BlockNumber>2775752852696174000</BlockNumber>
        <Confirmations>6532019680679138000</Confirmations>
        <ContractCodes>
          <Sint deleniti est est quibusdam et quis.>
            <ABI>Eum quos.</ABI>
            <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
            <Verified>false</Verified>
          </Sint deleniti est est quibusdam et quis.>
        </ContractCodes>
        <ContractCreation>true</ContractCreation>
        <Error>Aut vel minus molestiae aut aliquam.</Error>
        <Events>
          <Address>Rerum dolorum sit aut sit.</Address>
          <Data>Vel in consequatur odio numquam ut.</Data>
          <Index>2440912512905109500</Index>
          <Topics>Voluptatem enim ducimus et.</Topics>
          <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
        </Events>
        <From>Tempore voluptates voluptas aut.</From>
        <Gas>Qui aut provident et neque.</Gas>
        <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
        <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
        <Hash>Dolorum unde est omnis velit assumenda.</Hash>
        <Index>9096248114404918000</Index>
        <Input>In distinctio doloremque magni totam possimus.</Input>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Network>Qui culpa quis laudantium molestias consequatur.</Network>
        <Nonce>Voluptatem magnam ea.</Nonce>
        <Output>Dicta velit debitis ea temporibus nemo.</Output>
        <Timestamp>4092050381628505000</Timestamp>
        <To>Accusantium neque debitis numquam molestiae aut.</To>
        <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
      </Result>
    </Transactions>
    <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
  </Result>
  <Result>
    <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
    <CreationTime>7052733826006029000</CreationTime>
    <Difficulty>Sit aut.</Difficulty>
    <ExtraData>Molestiae quidem.</ExtraData>
    <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
    <GasUsed>Qui aut.</GasUsed>
    <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
    <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
    <MinedInSeconds>7897712511802021000</MinedInSeconds>
    <Miner>Autem veritatis repudiandae.</Miner>
    <MixHash>Officia ad aut dolores.</MixHash>
    <Network>Aut tempora enim sit corporis esse nihil.</Network>
    <Nonce>Omnis et similique.</Nonce>
    <Number>8737398717635499000</Number>
    <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
    <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
    <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
    <Size>Aliquid quia.</Size>
    <StateRoot>Eos harum.</StateRoot>
    <Timestamp>7483662194381612000</Timestamp>
    <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
    <TransactionCount>1234215781114073300</TransactionCount>
    <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
    <Transactions>
      <First>false</First>
      <Limit>7551599146550128000</Limit>
      <MessagesIncluded>true</MessagesIncluded>
      <Result>
        <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
        <BlockNumber>2775752852696174000</BlockNumber>
        <Confirmations>6532019680679138000</Confirmations>
        <ContractCodes>
          <Sint deleniti est est quibusdam et quis.>
            <ABI>Eum quos.</ABI>
            <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
            <Verified>false</Verified>
          </Sint deleniti est est quibusdam et quis.>
        </ContractCodes>
        <ContractCreation>true</ContractCreation>
        <Error>Aut vel minus molestiae aut aliquam.</Error>
        <Events>
          <Address>Rerum dolorum sit aut sit.</Address>
          <Data>Vel in consequatur odio numquam ut.</Data>
          <Index>2440912512905109500</Index>
          <Topics>Voluptatem enim ducimus et.</Topics>
          <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
        </Events>
        <From>Tempore voluptates voluptas aut.</From>
        <Gas>Qui aut provident et neque.</Gas>
        <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
        <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
        <Hash>Dolorum unde est omnis velit assumenda.</Hash>
        <Index>9096248114404918000</Index>
        <Input>In distinctio doloremque magni totam possimus.</Input>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Network>Qui culpa quis laudantium molestias consequatur.</Network>
        <Nonce>Voluptatem magnam ea.</Nonce>
        <Output>Dicta velit debitis ea temporibus nemo.</Output>
        <Timestamp>4092050381628505000</Timestamp>
        <To>Accusantium neque debitis numquam molestiae aut.</To>
        <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
      </Result>
    </Transactions>
    <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
  </Result>
  <TotalRecords>7269848697550577000</TotalRecords>
</Blocks>
<Difficulty>Maiores aut dolorem.</Difficulty>
<GasLimit>Nulla eligendi libero modi et et iusto.</GasLimit>
<GenesisHash>Fugit harum deleniti.</GenesisHash>
<HashRate>Quam ut unde et.</HashRate>
<ID>Quas voluptas nostrum quos.</ID>
<Name>Voluptatem voluptas autem earum quaerat similique sint.</Name>
<PendingTransactions>
  <First>false</First>
  <Limit>7551599146550128000</Limit>
  <MessagesIncluded>true</MessagesIncluded>
  <Result>
    <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
    <BlockNumber>2775752852696174000</BlockNumber>
    <Confirmations>6532019680679138000</Confirmations>
    <ContractCodes>
      <Sint deleniti est est quibusdam et quis.>
        <ABI>Eum quos.</ABI>
        <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
        <Verified>false</Verified>
      </Sint deleniti est est quibusdam et quis.>
    </ContractCodes>
    <ContractCreation>true</ContractCreation>
    <Error>Aut vel minus molestiae aut aliquam.</Error>
    <Events>
      <Address>Rerum dolorum sit aut sit.</Address>
      <Data>Vel in consequatur odio numquam ut.</Data>
      <Index>2440912512905109500</Index>
      <Topics>Voluptatem enim ducimus et.</Topics>
      <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
    </Events>
    <From>Tempore voluptates voluptas aut.</From>
    <Gas>Qui aut provident et neque.</Gas>
    <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
    <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
    <Hash>Dolorum unde est omnis velit assumenda.</Hash>
    <Index>9096248114404918000</Index>
    <Input>In distinctio doloremque magni totam possimus.</Input>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Network>Qui culpa quis laudantium molestias consequatur.</Network>
    <Nonce>Voluptatem magnam ea.</Nonce>
    <Output>Dicta velit debitis ea temporibus nemo.</Output>
    <Timestamp>4092050381628505000</Timestamp>
    <To>Accusantium neque debitis numquam molestiae aut.</To>
    <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
  </Result>
</PendingTransactions>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbNetworkCollection](#schemaethdbnetworkcollection)

<aside class="success">
This operation does not require authentication
</aside>

## Networks#show

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/networks/{ID} \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/networks/{ID} HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/networks/{ID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/networks/{ID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/networks/{ID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/networks/{ID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/networks/{ID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /networks/{ID}`

*show Networks*

Network details

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
ID|path|string|true|No description


> Example responses

```json
{
  "BlockHeight": 2249756891723881000,
  "BlockReward": "Facere consequatur numquam labore.",
  "Blocks": {
    "First": true,
    "Limit": 8813805051874942000,
    "Result": [
      {
        "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
        "CreationTime": 7052733826006029000,
        "Difficulty": "Sit aut.",
        "ExtraData": "Molestiae quidem.",
        "GasLimit": "Aut molestias magnam sunt doloremque.",
        "GasUsed": "Qui aut.",
        "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
        "LogsBloom": "Vel consequatur reprehenderit id neque.",
        "MinedInSeconds": 7897712511802021000,
        "Miner": "Autem veritatis repudiandae.",
        "MixHash": "Officia ad aut dolores.",
        "Network": "Aut tempora enim sit corporis esse nihil.",
        "Nonce": "Omnis et similique.",
        "Number": 8737398717635499000,
        "ParentHash": "Optio iure vel libero earum vitae et.",
        "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
        "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
        "Size": "Aliquid quia.",
        "StateRoot": "Eos harum.",
        "Timestamp": 7483662194381612000,
        "TotalDifficulty": "Distinctio architecto perferendis quae.",
        "TransactionCount": 1234215781114073300,
        "TransactionFees": "Sunt doloremque ex quasi aut quo.",
        "Transactions": {
          "First": false,
          "Limit": 7551599146550128000,
          "MessagesIncluded": true,
          "Result": [
            {
              "BlockHash": "Voluptatem laboriosam quidem.",
              "BlockNumber": 2775752852696174000,
              "Confirmations": 6532019680679138000,
              "ContractCodes": {
                "Sint deleniti est est quibusdam et quis.": {
                  "ABI": "Eum quos.",
                  "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                  "Verified": false
                }
              },
              "ContractCreation": true,
              "Error": "Aut vel minus molestiae aut aliquam.",
              "Events": [
                {
                  "Address": "Rerum dolorum sit aut sit.",
                  "Data": "Vel in consequatur odio numquam ut.",
                  "Index": 2440912512905109500,
                  "Topics": [
                    "Voluptatem enim ducimus et."
                  ],
                  "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                }
              ],
              "From": "Tempore voluptates voluptas aut.",
              "Gas": "Qui aut provident et neque.",
              "GasPrice": "Esse labore quo non consequatur quis molestiae.",
              "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
              "Hash": "Dolorum unde est omnis velit assumenda.",
              "Index": 9096248114404918000,
              "Input": "In distinctio doloremque magni totam possimus.",
              "Messages": [
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                },
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                }
              ],
              "Network": "Qui culpa quis laudantium molestias consequatur.",
              "Nonce": "Voluptatem magnam ea.",
              "Output": "Dicta velit debitis ea temporibus nemo.",
              "Timestamp": 4092050381628505000,
              "To": "Accusantium neque debitis numquam molestiae aut.",
              "Value": "Blanditiis est ex quos distinctio eligendi totam."
            }
          ]
        },
        "UncleReward": "Tempore voluptatem neque nisi est.",
        "Uncles": [
          "Dicta aspernatur.",
          "Dicta aspernatur.",
          "Dicta aspernatur."
        ]
      },
      {
        "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
        "CreationTime": 7052733826006029000,
        "Difficulty": "Sit aut.",
        "ExtraData": "Molestiae quidem.",
        "GasLimit": "Aut molestias magnam sunt doloremque.",
        "GasUsed": "Qui aut.",
        "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
        "LogsBloom": "Vel consequatur reprehenderit id neque.",
        "MinedInSeconds": 7897712511802021000,
        "Miner": "Autem veritatis repudiandae.",
        "MixHash": "Officia ad aut dolores.",
        "Network": "Aut tempora enim sit corporis esse nihil.",
        "Nonce": "Omnis et similique.",
        "Number": 8737398717635499000,
        "ParentHash": "Optio iure vel libero earum vitae et.",
        "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
        "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
        "Size": "Aliquid quia.",
        "StateRoot": "Eos harum.",
        "Timestamp": 7483662194381612000,
        "TotalDifficulty": "Distinctio architecto perferendis quae.",
        "TransactionCount": 1234215781114073300,
        "TransactionFees": "Sunt doloremque ex quasi aut quo.",
        "Transactions": {
          "First": false,
          "Limit": 7551599146550128000,
          "MessagesIncluded": true,
          "Result": [
            {
              "BlockHash": "Voluptatem laboriosam quidem.",
              "BlockNumber": 2775752852696174000,
              "Confirmations": 6532019680679138000,
              "ContractCodes": {
                "Sint deleniti est est quibusdam et quis.": {
                  "ABI": "Eum quos.",
                  "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                  "Verified": false
                }
              },
              "ContractCreation": true,
              "Error": "Aut vel minus molestiae aut aliquam.",
              "Events": [
                {
                  "Address": "Rerum dolorum sit aut sit.",
                  "Data": "Vel in consequatur odio numquam ut.",
                  "Index": 2440912512905109500,
                  "Topics": [
                    "Voluptatem enim ducimus et."
                  ],
                  "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                }
              ],
              "From": "Tempore voluptates voluptas aut.",
              "Gas": "Qui aut provident et neque.",
              "GasPrice": "Esse labore quo non consequatur quis molestiae.",
              "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
              "Hash": "Dolorum unde est omnis velit assumenda.",
              "Index": 9096248114404918000,
              "Input": "In distinctio doloremque magni totam possimus.",
              "Messages": [
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                },
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                }
              ],
              "Network": "Qui culpa quis laudantium molestias consequatur.",
              "Nonce": "Voluptatem magnam ea.",
              "Output": "Dicta velit debitis ea temporibus nemo.",
              "Timestamp": 4092050381628505000,
              "To": "Accusantium neque debitis numquam molestiae aut.",
              "Value": "Blanditiis est ex quos distinctio eligendi totam."
            }
          ]
        },
        "UncleReward": "Tempore voluptatem neque nisi est.",
        "Uncles": [
          "Dicta aspernatur.",
          "Dicta aspernatur.",
          "Dicta aspernatur."
        ]
      }
    ],
    "TotalRecords": 7269848697550577000
  },
  "Difficulty": "Maiores aut dolorem.",
  "GasLimit": "Nulla eligendi libero modi et et iusto.",
  "GenesisHash": "Fugit harum deleniti.",
  "HashRate": "Quam ut unde et.",
  "ID": "Quas voluptas nostrum quos.",
  "Name": "Voluptatem voluptas autem earum quaerat similique sint.",
  "PendingTransactions": {
    "First": false,
    "Limit": 7551599146550128000,
    "MessagesIncluded": true,
    "Result": [
      {
        "BlockHash": "Voluptatem laboriosam quidem.",
        "BlockNumber": 2775752852696174000,
        "Confirmations": 6532019680679138000,
        "ContractCodes": {
          "Sint deleniti est est quibusdam et quis.": {
            "ABI": "Eum quos.",
            "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
            "Verified": false
          }
        },
        "ContractCreation": true,
        "Error": "Aut vel minus molestiae aut aliquam.",
        "Events": [
          {
            "Address": "Rerum dolorum sit aut sit.",
            "Data": "Vel in consequatur odio numquam ut.",
            "Index": 2440912512905109500,
            "Topics": [
              "Voluptatem enim ducimus et."
            ],
            "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
          }
        ],
        "From": "Tempore voluptates voluptas aut.",
        "Gas": "Qui aut provident et neque.",
        "GasPrice": "Esse labore quo non consequatur quis molestiae.",
        "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
        "Hash": "Dolorum unde est omnis velit assumenda.",
        "Index": 9096248114404918000,
        "Input": "In distinctio doloremque magni totam possimus.",
        "Messages": [
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          },
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          }
        ],
        "Network": "Qui culpa quis laudantium molestias consequatur.",
        "Nonce": "Voluptatem magnam ea.",
        "Output": "Dicta velit debitis ea temporibus nemo.",
        "Timestamp": 4092050381628505000,
        "To": "Accusantium neque debitis numquam molestiae aut.",
        "Value": "Blanditiis est ex quos distinctio eligendi totam."
      }
    ]
  }
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<BlockHeight>2249756891723881000</BlockHeight>
<BlockReward>Facere consequatur numquam labore.</BlockReward>
<Blocks>
  <First>true</First>
  <Limit>8813805051874942000</Limit>
  <Result>
    <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
    <CreationTime>7052733826006029000</CreationTime>
    <Difficulty>Sit aut.</Difficulty>
    <ExtraData>Molestiae quidem.</ExtraData>
    <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
    <GasUsed>Qui aut.</GasUsed>
    <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
    <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
    <MinedInSeconds>7897712511802021000</MinedInSeconds>
    <Miner>Autem veritatis repudiandae.</Miner>
    <MixHash>Officia ad aut dolores.</MixHash>
    <Network>Aut tempora enim sit corporis esse nihil.</Network>
    <Nonce>Omnis et similique.</Nonce>
    <Number>8737398717635499000</Number>
    <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
    <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
    <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
    <Size>Aliquid quia.</Size>
    <StateRoot>Eos harum.</StateRoot>
    <Timestamp>7483662194381612000</Timestamp>
    <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
    <TransactionCount>1234215781114073300</TransactionCount>
    <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
    <Transactions>
      <First>false</First>
      <Limit>7551599146550128000</Limit>
      <MessagesIncluded>true</MessagesIncluded>
      <Result>
        <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
        <BlockNumber>2775752852696174000</BlockNumber>
        <Confirmations>6532019680679138000</Confirmations>
        <ContractCodes>
          <Sint deleniti est est quibusdam et quis.>
            <ABI>Eum quos.</ABI>
            <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
            <Verified>false</Verified>
          </Sint deleniti est est quibusdam et quis.>
        </ContractCodes>
        <ContractCreation>true</ContractCreation>
        <Error>Aut vel minus molestiae aut aliquam.</Error>
        <Events>
          <Address>Rerum dolorum sit aut sit.</Address>
          <Data>Vel in consequatur odio numquam ut.</Data>
          <Index>2440912512905109500</Index>
          <Topics>Voluptatem enim ducimus et.</Topics>
          <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
        </Events>
        <From>Tempore voluptates voluptas aut.</From>
        <Gas>Qui aut provident et neque.</Gas>
        <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
        <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
        <Hash>Dolorum unde est omnis velit assumenda.</Hash>
        <Index>9096248114404918000</Index>
        <Input>In distinctio doloremque magni totam possimus.</Input>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Network>Qui culpa quis laudantium molestias consequatur.</Network>
        <Nonce>Voluptatem magnam ea.</Nonce>
        <Output>Dicta velit debitis ea temporibus nemo.</Output>
        <Timestamp>4092050381628505000</Timestamp>
        <To>Accusantium neque debitis numquam molestiae aut.</To>
        <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
      </Result>
    </Transactions>
    <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
  </Result>
  <Result>
    <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
    <CreationTime>7052733826006029000</CreationTime>
    <Difficulty>Sit aut.</Difficulty>
    <ExtraData>Molestiae quidem.</ExtraData>
    <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
    <GasUsed>Qui aut.</GasUsed>
    <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
    <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
    <MinedInSeconds>7897712511802021000</MinedInSeconds>
    <Miner>Autem veritatis repudiandae.</Miner>
    <MixHash>Officia ad aut dolores.</MixHash>
    <Network>Aut tempora enim sit corporis esse nihil.</Network>
    <Nonce>Omnis et similique.</Nonce>
    <Number>8737398717635499000</Number>
    <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
    <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
    <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
    <Size>Aliquid quia.</Size>
    <StateRoot>Eos harum.</StateRoot>
    <Timestamp>7483662194381612000</Timestamp>
    <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
    <TransactionCount>1234215781114073300</TransactionCount>
    <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
    <Transactions>
      <First>false</First>
      <Limit>7551599146550128000</Limit>
      <MessagesIncluded>true</MessagesIncluded>
      <Result>
        <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
        <BlockNumber>2775752852696174000</BlockNumber>
        <Confirmations>6532019680679138000</Confirmations>
        <ContractCodes>
          <Sint deleniti est est quibusdam et quis.>
            <ABI>Eum quos.</ABI>
            <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
            <Verified>false</Verified>
          </Sint deleniti est est quibusdam et quis.>
        </ContractCodes>
        <ContractCreation>true</ContractCreation>
        <Error>Aut vel minus molestiae aut aliquam.</Error>
        <Events>
          <Address>Rerum dolorum sit aut sit.</Address>
          <Data>Vel in consequatur odio numquam ut.</Data>
          <Index>2440912512905109500</Index>
          <Topics>Voluptatem enim ducimus et.</Topics>
          <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
        </Events>
        <From>Tempore voluptates voluptas aut.</From>
        <Gas>Qui aut provident et neque.</Gas>
        <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
        <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
        <Hash>Dolorum unde est omnis velit assumenda.</Hash>
        <Index>9096248114404918000</Index>
        <Input>In distinctio doloremque magni totam possimus.</Input>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Messages>
          <Error>Quo culpa voluptatem.</Error>
          <From>Quo optio.</From>
          <Gas>Eum in a libero esse voluptas aut.</Gas>
          <GasUsed>Sit fugit molestiae.</GasUsed>
          <Input>Et soluta.</Input>
          <Nonce>Odit sunt.</Nonce>
          <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
          <To>Dolor temporibus placeat.</To>
          <Value>Nisi a consequatur nulla saepe voluptas.</Value>
        </Messages>
        <Network>Qui culpa quis laudantium molestias consequatur.</Network>
        <Nonce>Voluptatem magnam ea.</Nonce>
        <Output>Dicta velit debitis ea temporibus nemo.</Output>
        <Timestamp>4092050381628505000</Timestamp>
        <To>Accusantium neque debitis numquam molestiae aut.</To>
        <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
      </Result>
    </Transactions>
    <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
    <Uncles>Dicta aspernatur.</Uncles>
  </Result>
  <TotalRecords>7269848697550577000</TotalRecords>
</Blocks>
<Difficulty>Maiores aut dolorem.</Difficulty>
<GasLimit>Nulla eligendi libero modi et et iusto.</GasLimit>
<GenesisHash>Fugit harum deleniti.</GenesisHash>
<HashRate>Quam ut unde et.</HashRate>
<ID>Quas voluptas nostrum quos.</ID>
<Name>Voluptatem voluptas autem earum quaerat similique sint.</Name>
<PendingTransactions>
  <First>false</First>
  <Limit>7551599146550128000</Limit>
  <MessagesIncluded>true</MessagesIncluded>
  <Result>
    <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
    <BlockNumber>2775752852696174000</BlockNumber>
    <Confirmations>6532019680679138000</Confirmations>
    <ContractCodes>
      <Sint deleniti est est quibusdam et quis.>
        <ABI>Eum quos.</ABI>
        <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
        <Verified>false</Verified>
      </Sint deleniti est est quibusdam et quis.>
    </ContractCodes>
    <ContractCreation>true</ContractCreation>
    <Error>Aut vel minus molestiae aut aliquam.</Error>
    <Events>
      <Address>Rerum dolorum sit aut sit.</Address>
      <Data>Vel in consequatur odio numquam ut.</Data>
      <Index>2440912512905109500</Index>
      <Topics>Voluptatem enim ducimus et.</Topics>
      <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
    </Events>
    <From>Tempore voluptates voluptas aut.</From>
    <Gas>Qui aut provident et neque.</Gas>
    <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
    <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
    <Hash>Dolorum unde est omnis velit assumenda.</Hash>
    <Index>9096248114404918000</Index>
    <Input>In distinctio doloremque magni totam possimus.</Input>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Messages>
      <Error>Quo culpa voluptatem.</Error>
      <From>Quo optio.</From>
      <Gas>Eum in a libero esse voluptas aut.</Gas>
      <GasUsed>Sit fugit molestiae.</GasUsed>
      <Input>Et soluta.</Input>
      <Nonce>Odit sunt.</Nonce>
      <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
      <To>Dolor temporibus placeat.</To>
      <Value>Nisi a consequatur nulla saepe voluptas.</Value>
    </Messages>
    <Network>Qui culpa quis laudantium molestias consequatur.</Network>
    <Nonce>Voluptatem magnam ea.</Nonce>
    <Output>Dicta velit debitis ea temporibus nemo.</Output>
    <Timestamp>4092050381628505000</Timestamp>
    <To>Accusantium neque debitis numquam molestiae aut.</To>
    <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
  </Result>
</PendingTransactions>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbNetwork](#schemaethdbnetwork)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

## Networks#blocks

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/networks/{ID}/blocks \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/networks/{ID}/blocks HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/networks/{ID}/blocks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/networks/{ID}/blocks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/networks/{ID}/blocks',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/networks/{ID}/blocks', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/networks/{ID}/blocks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /networks/{ID}/blocks`

*blocks Networks*

Return list of recently mined blocks on this network

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
ID|path|string|true|No description
block|query|integer|false|Optional block number to returns blocks begining at
previous|query|boolean|false|When set to true, returns transactions Previous to the specified block number and transaction index


> Example responses

```json
{
  "First": true,
  "Limit": 8813805051874942000,
  "Result": [
    {
      "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
      "CreationTime": 7052733826006029000,
      "Difficulty": "Sit aut.",
      "ExtraData": "Molestiae quidem.",
      "GasLimit": "Aut molestias magnam sunt doloremque.",
      "GasUsed": "Qui aut.",
      "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
      "LogsBloom": "Vel consequatur reprehenderit id neque.",
      "MinedInSeconds": 7897712511802021000,
      "Miner": "Autem veritatis repudiandae.",
      "MixHash": "Officia ad aut dolores.",
      "Network": "Aut tempora enim sit corporis esse nihil.",
      "Nonce": "Omnis et similique.",
      "Number": 8737398717635499000,
      "ParentHash": "Optio iure vel libero earum vitae et.",
      "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
      "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
      "Size": "Aliquid quia.",
      "StateRoot": "Eos harum.",
      "Timestamp": 7483662194381612000,
      "TotalDifficulty": "Distinctio architecto perferendis quae.",
      "TransactionCount": 1234215781114073300,
      "TransactionFees": "Sunt doloremque ex quasi aut quo.",
      "Transactions": {
        "First": false,
        "Limit": 7551599146550128000,
        "MessagesIncluded": true,
        "Result": [
          {
            "BlockHash": "Voluptatem laboriosam quidem.",
            "BlockNumber": 2775752852696174000,
            "Confirmations": 6532019680679138000,
            "ContractCodes": {
              "Sint deleniti est est quibusdam et quis.": {
                "ABI": "Eum quos.",
                "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                "Verified": false
              }
            },
            "ContractCreation": true,
            "Error": "Aut vel minus molestiae aut aliquam.",
            "Events": [
              {
                "Address": "Rerum dolorum sit aut sit.",
                "Data": "Vel in consequatur odio numquam ut.",
                "Index": 2440912512905109500,
                "Topics": [
                  "Voluptatem enim ducimus et."
                ],
                "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
              }
            ],
            "From": "Tempore voluptates voluptas aut.",
            "Gas": "Qui aut provident et neque.",
            "GasPrice": "Esse labore quo non consequatur quis molestiae.",
            "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
            "Hash": "Dolorum unde est omnis velit assumenda.",
            "Index": 9096248114404918000,
            "Input": "In distinctio doloremque magni totam possimus.",
            "Messages": [
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              },
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              }
            ],
            "Network": "Qui culpa quis laudantium molestias consequatur.",
            "Nonce": "Voluptatem magnam ea.",
            "Output": "Dicta velit debitis ea temporibus nemo.",
            "Timestamp": 4092050381628505000,
            "To": "Accusantium neque debitis numquam molestiae aut.",
            "Value": "Blanditiis est ex quos distinctio eligendi totam."
          }
        ]
      },
      "UncleReward": "Tempore voluptatem neque nisi est.",
      "Uncles": [
        "Dicta aspernatur.",
        "Dicta aspernatur.",
        "Dicta aspernatur."
      ]
    },
    {
      "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
      "CreationTime": 7052733826006029000,
      "Difficulty": "Sit aut.",
      "ExtraData": "Molestiae quidem.",
      "GasLimit": "Aut molestias magnam sunt doloremque.",
      "GasUsed": "Qui aut.",
      "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
      "LogsBloom": "Vel consequatur reprehenderit id neque.",
      "MinedInSeconds": 7897712511802021000,
      "Miner": "Autem veritatis repudiandae.",
      "MixHash": "Officia ad aut dolores.",
      "Network": "Aut tempora enim sit corporis esse nihil.",
      "Nonce": "Omnis et similique.",
      "Number": 8737398717635499000,
      "ParentHash": "Optio iure vel libero earum vitae et.",
      "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
      "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
      "Size": "Aliquid quia.",
      "StateRoot": "Eos harum.",
      "Timestamp": 7483662194381612000,
      "TotalDifficulty": "Distinctio architecto perferendis quae.",
      "TransactionCount": 1234215781114073300,
      "TransactionFees": "Sunt doloremque ex quasi aut quo.",
      "Transactions": {
        "First": false,
        "Limit": 7551599146550128000,
        "MessagesIncluded": true,
        "Result": [
          {
            "BlockHash": "Voluptatem laboriosam quidem.",
            "BlockNumber": 2775752852696174000,
            "Confirmations": 6532019680679138000,
            "ContractCodes": {
              "Sint deleniti est est quibusdam et quis.": {
                "ABI": "Eum quos.",
                "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                "Verified": false
              }
            },
            "ContractCreation": true,
            "Error": "Aut vel minus molestiae aut aliquam.",
            "Events": [
              {
                "Address": "Rerum dolorum sit aut sit.",
                "Data": "Vel in consequatur odio numquam ut.",
                "Index": 2440912512905109500,
                "Topics": [
                  "Voluptatem enim ducimus et."
                ],
                "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
              }
            ],
            "From": "Tempore voluptates voluptas aut.",
            "Gas": "Qui aut provident et neque.",
            "GasPrice": "Esse labore quo non consequatur quis molestiae.",
            "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
            "Hash": "Dolorum unde est omnis velit assumenda.",
            "Index": 9096248114404918000,
            "Input": "In distinctio doloremque magni totam possimus.",
            "Messages": [
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              },
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              }
            ],
            "Network": "Qui culpa quis laudantium molestias consequatur.",
            "Nonce": "Voluptatem magnam ea.",
            "Output": "Dicta velit debitis ea temporibus nemo.",
            "Timestamp": 4092050381628505000,
            "To": "Accusantium neque debitis numquam molestiae aut.",
            "Value": "Blanditiis est ex quos distinctio eligendi totam."
          }
        ]
      },
      "UncleReward": "Tempore voluptatem neque nisi est.",
      "Uncles": [
        "Dicta aspernatur.",
        "Dicta aspernatur.",
        "Dicta aspernatur."
      ]
    }
  ],
  "TotalRecords": 7269848697550577000
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<First>true</First>
<Limit>8813805051874942000</Limit>
<Result>
  <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
  <CreationTime>7052733826006029000</CreationTime>
  <Difficulty>Sit aut.</Difficulty>
  <ExtraData>Molestiae quidem.</ExtraData>
  <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
  <GasUsed>Qui aut.</GasUsed>
  <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
  <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
  <MinedInSeconds>7897712511802021000</MinedInSeconds>
  <Miner>Autem veritatis repudiandae.</Miner>
  <MixHash>Officia ad aut dolores.</MixHash>
  <Network>Aut tempora enim sit corporis esse nihil.</Network>
  <Nonce>Omnis et similique.</Nonce>
  <Number>8737398717635499000</Number>
  <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
  <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
  <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
  <Size>Aliquid quia.</Size>
  <StateRoot>Eos harum.</StateRoot>
  <Timestamp>7483662194381612000</Timestamp>
  <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
  <TransactionCount>1234215781114073300</TransactionCount>
  <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
  <Transactions>
    <First>false</First>
    <Limit>7551599146550128000</Limit>
    <MessagesIncluded>true</MessagesIncluded>
    <Result>
      <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
      <BlockNumber>2775752852696174000</BlockNumber>
      <Confirmations>6532019680679138000</Confirmations>
      <ContractCodes>
        <Sint deleniti est est quibusdam et quis.>
          <ABI>Eum quos.</ABI>
          <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
          <Verified>false</Verified>
        </Sint deleniti est est quibusdam et quis.>
      </ContractCodes>
      <ContractCreation>true</ContractCreation>
      <Error>Aut vel minus molestiae aut aliquam.</Error>
      <Events>
        <Address>Rerum dolorum sit aut sit.</Address>
        <Data>Vel in consequatur odio numquam ut.</Data>
        <Index>2440912512905109500</Index>
        <Topics>Voluptatem enim ducimus et.</Topics>
        <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
      </Events>
      <From>Tempore voluptates voluptas aut.</From>
      <Gas>Qui aut provident et neque.</Gas>
      <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
      <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
      <Hash>Dolorum unde est omnis velit assumenda.</Hash>
      <Index>9096248114404918000</Index>
      <Input>In distinctio doloremque magni totam possimus.</Input>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Network>Qui culpa quis laudantium molestias consequatur.</Network>
      <Nonce>Voluptatem magnam ea.</Nonce>
      <Output>Dicta velit debitis ea temporibus nemo.</Output>
      <Timestamp>4092050381628505000</Timestamp>
      <To>Accusantium neque debitis numquam molestiae aut.</To>
      <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
    </Result>
  </Transactions>
  <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
</Result>
<Result>
  <BeneficiaryReward>Vel doloremque explicabo aut aut voluptas.</BeneficiaryReward>
  <CreationTime>7052733826006029000</CreationTime>
  <Difficulty>Sit aut.</Difficulty>
  <ExtraData>Molestiae quidem.</ExtraData>
  <GasLimit>Aut molestias magnam sunt doloremque.</GasLimit>
  <GasUsed>Qui aut.</GasUsed>
  <Hash>Non perspiciatis perspiciatis officiis ducimus beatae voluptas.</Hash>
  <LogsBloom>Vel consequatur reprehenderit id neque.</LogsBloom>
  <MinedInSeconds>7897712511802021000</MinedInSeconds>
  <Miner>Autem veritatis repudiandae.</Miner>
  <MixHash>Officia ad aut dolores.</MixHash>
  <Network>Aut tempora enim sit corporis esse nihil.</Network>
  <Nonce>Omnis et similique.</Nonce>
  <Number>8737398717635499000</Number>
  <ParentHash>Optio iure vel libero earum vitae et.</ParentHash>
  <ReceiptsRoot>Illum voluptatibus autem sit sequi recusandae.</ReceiptsRoot>
  <SHA3Uncles>Ratione quaerat deserunt repellendus sit aliquid rem.</SHA3Uncles>
  <Size>Aliquid quia.</Size>
  <StateRoot>Eos harum.</StateRoot>
  <Timestamp>7483662194381612000</Timestamp>
  <TotalDifficulty>Distinctio architecto perferendis quae.</TotalDifficulty>
  <TransactionCount>1234215781114073300</TransactionCount>
  <TransactionFees>Sunt doloremque ex quasi aut quo.</TransactionFees>
  <Transactions>
    <First>false</First>
    <Limit>7551599146550128000</Limit>
    <MessagesIncluded>true</MessagesIncluded>
    <Result>
      <BlockHash>Voluptatem laboriosam quidem.</BlockHash>
      <BlockNumber>2775752852696174000</BlockNumber>
      <Confirmations>6532019680679138000</Confirmations>
      <ContractCodes>
        <Sint deleniti est est quibusdam et quis.>
          <ABI>Eum quos.</ABI>
          <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
          <Verified>false</Verified>
        </Sint deleniti est est quibusdam et quis.>
      </ContractCodes>
      <ContractCreation>true</ContractCreation>
      <Error>Aut vel minus molestiae aut aliquam.</Error>
      <Events>
        <Address>Rerum dolorum sit aut sit.</Address>
        <Data>Vel in consequatur odio numquam ut.</Data>
        <Index>2440912512905109500</Index>
        <Topics>Voluptatem enim ducimus et.</Topics>
        <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
      </Events>
      <From>Tempore voluptates voluptas aut.</From>
      <Gas>Qui aut provident et neque.</Gas>
      <GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
      <GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
      <Hash>Dolorum unde est omnis velit assumenda.</Hash>
      <Index>9096248114404918000</Index>
      <Input>In distinctio doloremque magni totam possimus.</Input>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Messages>
        <Error>Quo culpa voluptatem.</Error>
        <From>Quo optio.</From>
        <Gas>Eum in a libero esse voluptas aut.</Gas>
        <GasUsed>Sit fugit molestiae.</GasUsed>
        <Input>Et soluta.</Input>
        <Nonce>Odit sunt.</Nonce>
        <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
        <To>Dolor temporibus placeat.</To>
        <Value>Nisi a consequatur nulla saepe voluptas.</Value>
      </Messages>
      <Network>Qui culpa quis laudantium molestias consequatur.</Network>
      <Nonce>Voluptatem magnam ea.</Nonce>
      <Output>Dicta velit debitis ea temporibus nemo.</Output>
      <Timestamp>4092050381628505000</Timestamp>
      <To>Accusantium neque debitis numquam molestiae aut.</To>
      <Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
    </Result>
  </Transactions>
  <UncleReward>Tempore voluptatem neque nisi est.</UncleReward>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
  <Uncles>Dicta aspernatur.</Uncles>
</Result>
<TotalRecords>7269848697550577000</TotalRecords>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbBlocks](#schemaethdbblocks)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

# Search

## Search#search

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/search?query=string

```

```http
GET http://localhost:3001/api/v1/search?query=string HTTP/1.1
Host: localhost:3001


```

```javascript

$.ajax({
  url: 'http://localhost:3001/api/v1/search',
  method: 'get',
  data: '?query=string',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('http://localhost:3001/api/v1/search?query=string',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:3001/api/v1/search',
  params: {
  'query' => 'string'
}

p JSON.parse(result)
```

```python
import requests

r = requests.get('http://localhost:3001/api/v1/search', params={
  'query': 'string'
)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/search?query=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /search`

*search Search*

Search the Blockchain

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
network|query|string|false|Search query
query|query|string|true|Search query


### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="success">
This operation does not require authentication
</aside>

# Source

## Source#list

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/source \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/source HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/source',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/source',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/source',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/source', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/source");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /source`

*list Source*

Returns list of public source repositories

> Example responses

```json
[
  {
    "BlockchainContracts": [
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      },
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      }
    ],
    "Bytecode": {
      "Facilis quia quia fuga libero ut.": {
        "ABI": "Cumque optio aut qui.",
        "Bytecode": "Quasi quasi cupiditate ex quos quis eos.",
        "Compiler": "Sapiente voluptatem magnam quod rerum quia ab.",
        "Optimized": false
      }
    },
    "EthPM": "Molestiae necessitatibus repellendus reprehenderit.",
    "Name": "Harum natus consequatur qui.",
    "Readme": "Porro architecto.",
    "SourceFiles": [
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      },
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      }
    ],
    "Type": "Dicta ipsa id impedit omnis velit autem.",
    "URL": "Debitis pariatur nihil non.",
    "Version": "Labore ut corrupti.",
    "Versions": [
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem."
    ]
  },
  {
    "BlockchainContracts": [
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      },
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      }
    ],
    "Bytecode": {
      "Facilis quia quia fuga libero ut.": {
        "ABI": "Cumque optio aut qui.",
        "Bytecode": "Quasi quasi cupiditate ex quos quis eos.",
        "Compiler": "Sapiente voluptatem magnam quod rerum quia ab.",
        "Optimized": false
      }
    },
    "EthPM": "Molestiae necessitatibus repellendus reprehenderit.",
    "Name": "Harum natus consequatur qui.",
    "Readme": "Porro architecto.",
    "SourceFiles": [
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      },
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      }
    ],
    "Type": "Dicta ipsa id impedit omnis velit autem.",
    "URL": "Debitis pariatur nihil non.",
    "Version": "Labore ut corrupti.",
    "Versions": [
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem."
    ]
  }
]
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<BlockchainContracts>
  <Address>Numquam aut inventore.</Address>
  <Contract>Sit nostrum dolorem.</Contract>
  <Network>Necessitatibus laudantium eligendi.</Network>
</BlockchainContracts>
<BlockchainContracts>
  <Address>Numquam aut inventore.</Address>
  <Contract>Sit nostrum dolorem.</Contract>
  <Network>Necessitatibus laudantium eligendi.</Network>
</BlockchainContracts>
<Bytecode>
  <Facilis quia quia fuga libero ut.>
    <ABI>Cumque optio aut qui.</ABI>
    <Bytecode>Quasi quasi cupiditate ex quos quis eos.</Bytecode>
    <Compiler>Sapiente voluptatem magnam quod rerum quia ab.</Compiler>
    <Optimized>false</Optimized>
  </Facilis quia quia fuga libero ut.>
</Bytecode>
<EthPM>Molestiae necessitatibus repellendus reprehenderit.</EthPM>
<Name>Harum natus consequatur qui.</Name>
<Readme>Porro architecto.</Readme>
<SourceFiles>
  <CanonicalURL>Corrupti aut esse eligendi.</CanonicalURL>
  <Filename>Dolor facere officia molestias ab.</Filename>
  <Language>Aliquam iure quaerat eveniet optio exercitationem repudiandae.</Language>
  <Source>Veniam corrupti expedita est est soluta maxime.</Source>
  <Version>Quam voluptas dolorum corporis sit nihil nostrum.</Version>
</SourceFiles>
<SourceFiles>
  <CanonicalURL>Corrupti aut esse eligendi.</CanonicalURL>
  <Filename>Dolor facere officia molestias ab.</Filename>
  <Language>Aliquam iure quaerat eveniet optio exercitationem repudiandae.</Language>
  <Source>Veniam corrupti expedita est est soluta maxime.</Source>
  <Version>Quam voluptas dolorum corporis sit nihil nostrum.</Version>
</SourceFiles>
<Type>Dicta ipsa id impedit omnis velit autem.</Type>
<URL>Debitis pariatur nihil non.</URL>
<Version>Labore ut corrupti.</Version>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
<BlockchainContracts>
  <Address>Numquam aut inventore.</Address>
  <Contract>Sit nostrum dolorem.</Contract>
  <Network>Necessitatibus laudantium eligendi.</Network>
</BlockchainContracts>
<BlockchainContracts>
  <Address>Numquam aut inventore.</Address>
  <Contract>Sit nostrum dolorem.</Contract>
  <Network>Necessitatibus laudantium eligendi.</Network>
</BlockchainContracts>
<Bytecode>
  <Facilis quia quia fuga libero ut.>
    <ABI>Cumque optio aut qui.</ABI>
    <Bytecode>Quasi quasi cupiditate ex quos quis eos.</Bytecode>
    <Compiler>Sapiente voluptatem magnam quod rerum quia ab.</Compiler>
    <Optimized>false</Optimized>
  </Facilis quia quia fuga libero ut.>
</Bytecode>
<EthPM>Molestiae necessitatibus repellendus reprehenderit.</EthPM>
<Name>Harum natus consequatur qui.</Name>
<Readme>Porro architecto.</Readme>
<SourceFiles>
  <CanonicalURL>Corrupti aut esse eligendi.</CanonicalURL>
  <Filename>Dolor facere officia molestias ab.</Filename>
  <Language>Aliquam iure quaerat eveniet optio exercitationem repudiandae.</Language>
  <Source>Veniam corrupti expedita est est soluta maxime.</Source>
  <Version>Quam voluptas dolorum corporis sit nihil nostrum.</Version>
</SourceFiles>
<SourceFiles>
  <CanonicalURL>Corrupti aut esse eligendi.</CanonicalURL>
  <Filename>Dolor facere officia molestias ab.</Filename>
  <Language>Aliquam iure quaerat eveniet optio exercitationem repudiandae.</Language>
  <Source>Veniam corrupti expedita est est soluta maxime.</Source>
  <Version>Quam voluptas dolorum corporis sit nihil nostrum.</Version>
</SourceFiles>
<Type>Dicta ipsa id impedit omnis velit autem.</Type>
<URL>Debitis pariatur nihil non.</URL>
<Version>Labore ut corrupti.</Version>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbSourceCollection](#schemaethdbsourcecollection)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

## Source#show

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/source/{Type}/{Name} \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/source/{Type}/{Name} HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/source/{Type}/{Name}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/source/{Type}/{Name}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/source/{Type}/{Name}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/source/{Type}/{Name}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/source/{Type}/{Name}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /source/{Type}/{Name}`

*show Source*

Returns information on source package

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Name|path|string|true|No description
Type|path|string|true|No description
network|query|string|false|No description


> Example responses

```json
{
  "BlockchainContracts": [
    {
      "Address": "Numquam aut inventore.",
      "Contract": "Sit nostrum dolorem.",
      "Network": "Necessitatibus laudantium eligendi."
    },
    {
      "Address": "Numquam aut inventore.",
      "Contract": "Sit nostrum dolorem.",
      "Network": "Necessitatibus laudantium eligendi."
    }
  ],
  "Bytecode": {
    "Facilis quia quia fuga libero ut.": {
      "ABI": "Cumque optio aut qui.",
      "Bytecode": "Quasi quasi cupiditate ex quos quis eos.",
      "Compiler": "Sapiente voluptatem magnam quod rerum quia ab.",
      "Optimized": false
    }
  },
  "EthPM": "Molestiae necessitatibus repellendus reprehenderit.",
  "Name": "Harum natus consequatur qui.",
  "Readme": "Porro architecto.",
  "SourceFiles": [
    {
      "CanonicalURL": "Corrupti aut esse eligendi.",
      "Filename": "Dolor facere officia molestias ab.",
      "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
      "Source": "Veniam corrupti expedita est est soluta maxime.",
      "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
    },
    {
      "CanonicalURL": "Corrupti aut esse eligendi.",
      "Filename": "Dolor facere officia molestias ab.",
      "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
      "Source": "Veniam corrupti expedita est est soluta maxime.",
      "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
    }
  ],
  "Type": "Dicta ipsa id impedit omnis velit autem.",
  "URL": "Debitis pariatur nihil non.",
  "Version": "Labore ut corrupti.",
  "Versions": [
    "Iste possimus ipsa eos earum saepe quidem.",
    "Iste possimus ipsa eos earum saepe quidem.",
    "Iste possimus ipsa eos earum saepe quidem."
  ]
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<BlockchainContracts>
  <Address>Numquam aut inventore.</Address>
  <Contract>Sit nostrum dolorem.</Contract>
  <Network>Necessitatibus laudantium eligendi.</Network>
</BlockchainContracts>
<BlockchainContracts>
  <Address>Numquam aut inventore.</Address>
  <Contract>Sit nostrum dolorem.</Contract>
  <Network>Necessitatibus laudantium eligendi.</Network>
</BlockchainContracts>
<Bytecode>
  <Facilis quia quia fuga libero ut.>
    <ABI>Cumque optio aut qui.</ABI>
    <Bytecode>Quasi quasi cupiditate ex quos quis eos.</Bytecode>
    <Compiler>Sapiente voluptatem magnam quod rerum quia ab.</Compiler>
    <Optimized>false</Optimized>
  </Facilis quia quia fuga libero ut.>
</Bytecode>
<EthPM>Molestiae necessitatibus repellendus reprehenderit.</EthPM>
<Name>Harum natus consequatur qui.</Name>
<Readme>Porro architecto.</Readme>
<SourceFiles>
  <CanonicalURL>Corrupti aut esse eligendi.</CanonicalURL>
  <Filename>Dolor facere officia molestias ab.</Filename>
  <Language>Aliquam iure quaerat eveniet optio exercitationem repudiandae.</Language>
  <Source>Veniam corrupti expedita est est soluta maxime.</Source>
  <Version>Quam voluptas dolorum corporis sit nihil nostrum.</Version>
</SourceFiles>
<SourceFiles>
  <CanonicalURL>Corrupti aut esse eligendi.</CanonicalURL>
  <Filename>Dolor facere officia molestias ab.</Filename>
  <Language>Aliquam iure quaerat eveniet optio exercitationem repudiandae.</Language>
  <Source>Veniam corrupti expedita est est soluta maxime.</Source>
  <Version>Quam voluptas dolorum corporis sit nihil nostrum.</Version>
</SourceFiles>
<Type>Dicta ipsa id impedit omnis velit autem.</Type>
<URL>Debitis pariatur nihil non.</URL>
<Version>Labore ut corrupti.</Version>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
<Versions>Iste possimus ipsa eos earum saepe quidem.</Versions>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbSource](#schemaethdbsource)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

# Transaction

## Transaction#show

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/tx/{Hash} \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/tx/{Hash} HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/tx/{Hash}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/tx/{Hash}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/tx/{Hash}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/tx/{Hash}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/tx/{Hash}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /tx/{Hash}`

*show Transaction*

Ethereum Transactions

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Hash|path|string|true|Transaction hash


> Example responses

```json
{
  "BlockHash": "Voluptatem laboriosam quidem.",
  "BlockNumber": 2775752852696174000,
  "Confirmations": 6532019680679138000,
  "ContractCodes": {
    "Sint deleniti est est quibusdam et quis.": {
      "ABI": "Eum quos.",
      "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
      "Verified": false
    }
  },
  "ContractCreation": true,
  "Error": "Aut vel minus molestiae aut aliquam.",
  "Events": [
    {
      "Address": "Rerum dolorum sit aut sit.",
      "Data": "Vel in consequatur odio numquam ut.",
      "Index": 2440912512905109500,
      "Topics": [
        "Voluptatem enim ducimus et."
      ],
      "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
    }
  ],
  "From": "Tempore voluptates voluptas aut.",
  "Gas": "Qui aut provident et neque.",
  "GasPrice": "Esse labore quo non consequatur quis molestiae.",
  "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
  "Hash": "Dolorum unde est omnis velit assumenda.",
  "Index": 9096248114404918000,
  "Input": "In distinctio doloremque magni totam possimus.",
  "Messages": [
    {
      "Error": "Quo culpa voluptatem.",
      "From": "Quo optio.",
      "Gas": "Eum in a libero esse voluptas aut.",
      "GasUsed": "Sit fugit molestiae.",
      "Input": "Et soluta.",
      "Nonce": "Odit sunt.",
      "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
      "To": "Dolor temporibus placeat.",
      "Value": "Nisi a consequatur nulla saepe voluptas."
    },
    {
      "Error": "Quo culpa voluptatem.",
      "From": "Quo optio.",
      "Gas": "Eum in a libero esse voluptas aut.",
      "GasUsed": "Sit fugit molestiae.",
      "Input": "Et soluta.",
      "Nonce": "Odit sunt.",
      "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
      "To": "Dolor temporibus placeat.",
      "Value": "Nisi a consequatur nulla saepe voluptas."
    }
  ],
  "Network": "Qui culpa quis laudantium molestias consequatur.",
  "Nonce": "Voluptatem magnam ea.",
  "Output": "Dicta velit debitis ea temporibus nemo.",
  "Timestamp": 4092050381628505000,
  "To": "Accusantium neque debitis numquam molestiae aut.",
  "Value": "Blanditiis est ex quos distinctio eligendi totam."
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<BlockHash>Voluptatem laboriosam quidem.</BlockHash>
<BlockNumber>2775752852696174000</BlockNumber>
<Confirmations>6532019680679138000</Confirmations>
<ContractCodes>
  <Sint deleniti est est quibusdam et quis.>
    <ABI>Eum quos.</ABI>
    <Bytecode>Dolor omnis blanditiis soluta eveniet laborum nulla.</Bytecode>
    <Verified>false</Verified>
  </Sint deleniti est est quibusdam et quis.>
</ContractCodes>
<ContractCreation>true</ContractCreation>
<Error>Aut vel minus molestiae aut aliquam.</Error>
<Events>
  <Address>Rerum dolorum sit aut sit.</Address>
  <Data>Vel in consequatur odio numquam ut.</Data>
  <Index>2440912512905109500</Index>
  <Topics>Voluptatem enim ducimus et.</Topics>
  <TransactionHash>Autem et dicta voluptatibus quod vero sequi.</TransactionHash>
</Events>
<From>Tempore voluptates voluptas aut.</From>
<Gas>Qui aut provident et neque.</Gas>
<GasPrice>Esse labore quo non consequatur quis molestiae.</GasPrice>
<GasUsed>Exercitationem totam officiis aut debitis vero eum.</GasUsed>
<Hash>Dolorum unde est omnis velit assumenda.</Hash>
<Index>9096248114404918000</Index>
<Input>In distinctio doloremque magni totam possimus.</Input>
<Messages>
  <Error>Quo culpa voluptatem.</Error>
  <From>Quo optio.</From>
  <Gas>Eum in a libero esse voluptas aut.</Gas>
  <GasUsed>Sit fugit molestiae.</GasUsed>
  <Input>Et soluta.</Input>
  <Nonce>Odit sunt.</Nonce>
  <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
  <To>Dolor temporibus placeat.</To>
  <Value>Nisi a consequatur nulla saepe voluptas.</Value>
</Messages>
<Messages>
  <Error>Quo culpa voluptatem.</Error>
  <From>Quo optio.</From>
  <Gas>Eum in a libero esse voluptas aut.</Gas>
  <GasUsed>Sit fugit molestiae.</GasUsed>
  <Input>Et soluta.</Input>
  <Nonce>Odit sunt.</Nonce>
  <Position>Sunt officia sit ut voluptatem quasi perferendis.</Position>
  <To>Dolor temporibus placeat.</To>
  <Value>Nisi a consequatur nulla saepe voluptas.</Value>
</Messages>
<Network>Qui culpa quis laudantium molestias consequatur.</Network>
<Nonce>Voluptatem magnam ea.</Nonce>
<Output>Dicta velit debitis ea temporibus nemo.</Output>
<Timestamp>4092050381628505000</Timestamp>
<To>Accusantium neque debitis numquam molestiae aut.</To>
<Value>Blanditiis est ex quos distinctio eligendi totam.</Value>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbTransaction](#schemaethdbtransaction)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

# Uncle

## Uncle#show

> Code samples

```shell
# You can also use wget
curl -X get http://localhost:3001/api/v1/uncle/{Hash} \
  -H 'Accept: application/vnd.goa.error'

```

```http
GET http://localhost:3001/api/v1/uncle/{Hash} HTTP/1.1
Host: localhost:3001

Accept: application/vnd.goa.error

```

```javascript
var headers = {
  'Accept':'application/vnd.goa.error'

};

$.ajax({
  url: 'http://localhost:3001/api/v1/uncle/{Hash}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/vnd.goa.error'

};

fetch('http://localhost:3001/api/v1/uncle/{Hash}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/vnd.goa.error'
}

result = RestClient.get 'http://localhost:3001/api/v1/uncle/{Hash}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/vnd.goa.error'
}

r = requests.get('http://localhost:3001/api/v1/uncle/{Hash}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3001/api/v1/uncle/{Hash}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /uncle/{Hash}`

*show Uncle*

Uncle Block

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
Hash|path|string|true|Transaction hash


> Example responses

```json
{
  "BeneficiaryReward": "Mollitia omnis necessitatibus et.",
  "BlockNumber": 6948539910358115000,
  "CreationTime": 2533265886652186000,
  "Difficulty": "Eaque saepe.",
  "ExtraData": "Voluptate expedita saepe voluptates.",
  "GasLimit": "Eius est ea odit repellat est.",
  "Hash": "Asperiores et facere nostrum omnis consequuntur.",
  "Index": 4134083501788099000,
  "LogsBloom": "Ut nihil ipsam alias debitis qui.",
  "Miner": "Ea quasi assumenda.",
  "MixHash": "Ducimus maiores beatae.",
  "Nonce": "Molestiae suscipit quam dolore sit eum.",
  "Number": 7066559540085266000,
  "ParentHash": "Consectetur excepturi molestias quibusdam autem incidunt fugiat.",
  "ReceiptsRoot": "Itaque accusantium sunt.",
  "SHA3Uncles": "Architecto modi.",
  "Size": "Laudantium totam consectetur nihil repudiandae.",
  "StateRoot": "Provident facere consequatur explicabo est voluptatem.",
  "TotalDifficulty": "Voluptatibus dolorem."
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<BeneficiaryReward>Mollitia omnis necessitatibus et.</BeneficiaryReward>
<BlockNumber>6948539910358115000</BlockNumber>
<CreationTime>2533265886652186000</CreationTime>
<Difficulty>Eaque saepe.</Difficulty>
<ExtraData>Voluptate expedita saepe voluptates.</ExtraData>
<GasLimit>Eius est ea odit repellat est.</GasLimit>
<Hash>Asperiores et facere nostrum omnis consequuntur.</Hash>
<Index>4134083501788099000</Index>
<LogsBloom>Ut nihil ipsam alias debitis qui.</LogsBloom>
<Miner>Ea quasi assumenda.</Miner>
<MixHash>Ducimus maiores beatae.</MixHash>
<Nonce>Molestiae suscipit quam dolore sit eum.</Nonce>
<Number>7066559540085266000</Number>
<ParentHash>Consectetur excepturi molestias quibusdam autem incidunt fugiat.</ParentHash>
<ReceiptsRoot>Itaque accusantium sunt.</ReceiptsRoot>
<SHA3Uncles>Architecto modi.</SHA3Uncles>
<Size>Laudantium totam consectetur nihil repudiandae.</Size>
<StateRoot>Provident facere consequatur explicabo est voluptatem.</StateRoot>
<TotalDifficulty>Voluptatibus dolorem.</TotalDifficulty>
```
```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<code>invalid_value</code>
<detail>Value of ID must be an integer</detail>
<id>3F1FKVRR</id>
<meta>
  <timestamp>1458609066</timestamp>
</meta>
<status>400</status>
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[EthdbUncle](#schemaethdbuncle)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[error](#schemaerror)

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

## EthdbAccount

<a name="schemaethdbaccount"></a>

```json
{
  "Address": "Eligendi nisi.",
  "Balance": "Quaerat voluptatem non alias a in omnis.",
  "Contract": {
    "Code": {
      "ABI": "Eum quos.",
      "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
      "Verified": false
    },
    "CreatedBy": "Ut rerum omnis corporis adipisci facilis.",
    "CreationBlockHash": "Sed et officiis quo est numquam.",
    "CreationBlockHeight": 7885687097374916000,
    "CreationTimestamp": 7072314242291326000,
    "CreationTransaction": "Voluptas hic ullam inventore.",
    "SourcePackage": {
      "Name": "Alias distinctio sed.",
      "Type": "Quia voluptatem eum dolores officia.",
      "URL": "Voluptas amet."
    }
  },
  "MessageCount": 2362536009182212000,
  "MinedBlockCount": 3769039475084015600,
  "MinedUncleCount": 4349567159630496000,
  "Network": "Voluptas accusantium fugiat eos aut adipisci.",
  "Nickname": "Est porro sint dignissimos doloribus pariatur maiores.",
  "Nonce": "Similique accusantium.",
  "TransactionCount": 159856759856627170
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
Address|string|true|Unique Account identifier
Balance|string|true|Account balance in Wei
Contract|[EthdbAccountcontract](#schemaethdbaccountcontract)|false|Additional information about contract account (default view)
» Code|[EthdbContractcode](#schemaethdbcontractcode)|true|Contract bytecode (default view)
»» ABI|string|false|Contract ABI
»» Bytecode|string|true|Bytecode of contract
»» Verified|boolean|true|If the source code for this contract has been recompiled and matches the bytecode deployed on the Blockchain
» CreatedBy|string|true|Account that created this contract
» CreationBlockHash|string|true|Block hash which includes creation transaction
» CreationBlockHeight|integer(int64)|true|Block number which includes creation transaction
» CreationTimestamp|integer(int64)|true|Timestamp of block which includes creation transaction
» CreationTransaction|string|true|Transaction which created this contract
» SourcePackage|[EthdbSourceTiny](#schemaethdbsourcetiny)|false|Source code package (tiny view)
»» Name|string|true|Name
»» Type|string|true|Type of package.  Can be 'github'
»» URL|string|true|URL to canonical source repo
MessageCount|integer(int64)|true|Total number of internal transaction messages
MinedBlockCount|integer(int64)|true|Number of blocks mined by this Acccount
MinedUncleCount|integer(int64)|true|Number of uncle blocks mined by this Acccount
Network|string|true|Network ID of account
Nickname|string|false|Optional nickname for this account (not from blockchain
Nonce|string|true|Represents number of transactions created from this Account
TransactionCount|integer(int64)|true|Total number of transactions



## EthdbAccountcontract

<a name="schemaethdbaccountcontract"></a>

```json
{
  "Code": {
    "ABI": "Eum quos.",
    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
    "Verified": false
  },
  "CreatedBy": "Ut rerum omnis corporis adipisci facilis.",
  "CreationBlockHash": "Sed et officiis quo est numquam.",
  "CreationBlockHeight": 7885687097374916000,
  "CreationTimestamp": 7072314242291326000,
  "CreationTransaction": "Voluptas hic ullam inventore.",
  "SourcePackage": {
    "Name": "Alias distinctio sed.",
    "Type": "Quia voluptatem eum dolores officia.",
    "URL": "Voluptas amet."
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
Code|[EthdbContractcode](#schemaethdbcontractcode)|true|Contract bytecode (default view)
» ABI|string|false|Contract ABI
» Bytecode|string|true|Bytecode of contract
» Verified|boolean|true|If the source code for this contract has been recompiled and matches the bytecode deployed on the Blockchain
CreatedBy|string|true|Account that created this contract
CreationBlockHash|string|true|Block hash which includes creation transaction
CreationBlockHeight|integer(int64)|true|Block number which includes creation transaction
CreationTimestamp|integer(int64)|true|Timestamp of block which includes creation transaction
CreationTransaction|string|true|Transaction which created this contract
SourcePackage|[EthdbSourceTiny](#schemaethdbsourcetiny)|false|Source code package (tiny view)
» Name|string|true|Name
» Type|string|true|Type of package.  Can be 'github'
» URL|string|true|URL to canonical source repo



## EthdbBlock

<a name="schemaethdbblock"></a>

```json
{
  "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
  "CreationTime": 7052733826006029000,
  "Difficulty": "Sit aut.",
  "ExtraData": "Molestiae quidem.",
  "GasLimit": "Aut molestias magnam sunt doloremque.",
  "GasUsed": "Qui aut.",
  "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
  "LogsBloom": "Vel consequatur reprehenderit id neque.",
  "MinedInSeconds": 7897712511802021000,
  "Miner": "Autem veritatis repudiandae.",
  "MixHash": "Officia ad aut dolores.",
  "Network": "Aut tempora enim sit corporis esse nihil.",
  "Nonce": "Omnis et similique.",
  "Number": 8737398717635499000,
  "ParentHash": "Optio iure vel libero earum vitae et.",
  "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
  "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
  "Size": "Aliquid quia.",
  "StateRoot": "Eos harum.",
  "Timestamp": 7483662194381612000,
  "TotalDifficulty": "Distinctio architecto perferendis quae.",
  "TransactionCount": 1234215781114073300,
  "TransactionFees": "Sunt doloremque ex quasi aut quo.",
  "Transactions": {
    "First": false,
    "Limit": 7551599146550128000,
    "MessagesIncluded": true,
    "Result": [
      {
        "BlockHash": "Voluptatem laboriosam quidem.",
        "BlockNumber": 2775752852696174000,
        "Confirmations": 6532019680679138000,
        "ContractCodes": {
          "Sint deleniti est est quibusdam et quis.": {
            "ABI": "Eum quos.",
            "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
            "Verified": false
          }
        },
        "ContractCreation": true,
        "Error": "Aut vel minus molestiae aut aliquam.",
        "Events": [
          {
            "Address": "Rerum dolorum sit aut sit.",
            "Data": "Vel in consequatur odio numquam ut.",
            "Index": 2440912512905109500,
            "Topics": [
              "Voluptatem enim ducimus et."
            ],
            "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
          }
        ],
        "From": "Tempore voluptates voluptas aut.",
        "Gas": "Qui aut provident et neque.",
        "GasPrice": "Esse labore quo non consequatur quis molestiae.",
        "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
        "Hash": "Dolorum unde est omnis velit assumenda.",
        "Index": 9096248114404918000,
        "Input": "In distinctio doloremque magni totam possimus.",
        "Messages": [
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          },
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          }
        ],
        "Network": "Qui culpa quis laudantium molestias consequatur.",
        "Nonce": "Voluptatem magnam ea.",
        "Output": "Dicta velit debitis ea temporibus nemo.",
        "Timestamp": 4092050381628505000,
        "To": "Accusantium neque debitis numquam molestiae aut.",
        "Value": "Blanditiis est ex quos distinctio eligendi totam."
      }
    ]
  },
  "UncleReward": "Tempore voluptatem neque nisi est.",
  "Uncles": [
    "Dicta aspernatur.",
    "Dicta aspernatur.",
    "Dicta aspernatur."
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
BeneficiaryReward|string|true|Reward for mining a block.  Includes the base reward, reward for including Uncle blocks and the fees of Transactions included in the Block
CreationTime|integer(int64)|true|Timestamp of Block creation in Unix timestamp format
Difficulty|string|true|Difficulty level of this block
ExtraData|string|true|Data included in the Block by the Miner
GasLimit|string|true|Gas limit for this Block
GasUsed|string|true|Sum of gas used by transactions included in this Block
Hash|string|true|Keccak-256 hash of the Block header
LogsBloom|string|false|Bloom filter of indexable information included in the Block receipt Events
MinedInSeconds|integer(int64)|true|Number of seconds to mine this block
Miner|string|true|Address of miner that created the block
MixHash|string|false|Hash which proves Proof of Work for this Block has been completed
Network|string|true|Network ID
Nonce|string|false|Hash to be used in Proof of Work calculation
Number|integer(int64)|true|Block number
ParentHash|string|true|Hash of Parent Block
ReceiptsRoot|string|false|Hash of receipts
SHA3Uncles|string|true|Hash of Uncles included in Block
Size|string|false|Size of the Block header in bytes
StateRoot|string|false|No description
Timestamp|integer(int64)|true|When this block was mined, in UNIX format
TotalDifficulty|string|true|Total network difficulty when this block was mined
TransactionCount|integer(int64)|true|No description
TransactionFees|string|true|Sum of gas used of all transactions included in this block
Transactions|[EthdbTransactions](#schemaethdbtransactions)|true|A list of Ethereum transactions (default view)
» First|boolean|false|Set to true if results returned are at the beginning
» Limit|integer(int64)|true|Limit of number of results returned
» MessagesIncluded|boolean|true|Set to true if results include transaction messages
» Result|[[EthdbTransaction](#schemaethdbtransaction)]|false|Ethereum Transaction (default view)
»» BlockHash|string|true|Hash of Block this Transaction is included in
»» BlockNumber|integer(int64)|true|Height of Block this Transaction is included in
»» Confirmations|integer(int64)|true|Number of confirmations for this transaction
»» ContractCodes|object|false|If the transactions or messages are sent to a contract, information about the contract is returned if available
»» ContractCreation|boolean|false|This flag is set if the transaction creates a new contract
»» Error|string|true|Error message from the execution of this transaction, if any
»» From|string|true|Transaction creator address
»» Gas|string|true|Total gas supplied by this Transaction
»» GasPrice|string|true|Price in Wei of Gas supplied by this Transaction
»» GasUsed|string|true|Gas Used in this Transactions
»» Hash|string|true|Hash
»» Index|integer(int64)|true|Position of Transaction in the Block
»» Input|string|true|Transaction function call information
»» Network|string|true|Network ID of transaction
»» Nonce|string|true|Transaction nonce
»» Output|string|true|Transaction output - the result of calling a contract function
»» Timestamp|integer(int64)|true|Timestamp of when this Transaction was included a Block. In Unix timestamp format.
»» To|string|true|Transaction destination address
»» Value|string|true|Ethereum value transfered by this transation
»» Events|[[EthdbEvent](#schemaethdbevent)]|false|Event Log event (default view)
»»» Address|string|true|Address of Account
»»» Data|string|true|Event data
»»» Index|integer(int64)|true|Index of Event generated by Transaction
»»» TransactionHash|string|true|Hash of Transaction which generated this Event
»»» Topics|[string]|false|No description
»» Messages|[[EthdbMessage](#schemaethdbmessage)]|false|Transaction Internal message (default view)
»»» Error|string|true|Error message (if any) from executing of this message
»»» From|string|true|Transaction creator address
»»» Gas|string|true|Total gas supplied by this Transaction
»»» GasUsed|string|true|Gas Used in this Transactions
»»» Input|string|true|Transaction function call information
»»» Nonce|string|true|Transaction nonce
»»» Position|string|true|Position of this message in the EVM call stack
»»» To|string|true|Transaction destination address
»»» Value|string|true|Ethereum value transfered by this transation
UncleReward|string|true|Amount rewarded to miner for including Uncles in this block
Uncles|[string]|false|No description



## EthdbBlockchaincontract

<a name="schemaethdbblockchaincontract"></a>

```json
{
  "Address": "Numquam aut inventore.",
  "Contract": "Sit nostrum dolorem.",
  "Network": "Necessitatibus laudantium eligendi."
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
Address|string|true|Contract address
Contract|string|true|Compiled contract name
Network|string|true|Blockchain name



## EthdbBlockchaincontractCollection

<a name="schemaethdbblockchaincontractcollection"></a>

```json
[
  {
    "Address": "Numquam aut inventore.",
    "Contract": "Sit nostrum dolorem.",
    "Network": "Necessitatibus laudantium eligendi."
  }
] 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
anonymous|[[EthdbBlockchaincontract](#schemaethdbblockchaincontract)]|false|Listing of contract deployed on the blockchain (default view)
» Address|string|true|Contract address
» Contract|string|true|Compiled contract name
» Network|string|true|Blockchain name



## EthdbBlocks

<a name="schemaethdbblocks"></a>

```json
{
  "First": true,
  "Limit": 8813805051874942000,
  "Result": [
    {
      "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
      "CreationTime": 7052733826006029000,
      "Difficulty": "Sit aut.",
      "ExtraData": "Molestiae quidem.",
      "GasLimit": "Aut molestias magnam sunt doloremque.",
      "GasUsed": "Qui aut.",
      "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
      "LogsBloom": "Vel consequatur reprehenderit id neque.",
      "MinedInSeconds": 7897712511802021000,
      "Miner": "Autem veritatis repudiandae.",
      "MixHash": "Officia ad aut dolores.",
      "Network": "Aut tempora enim sit corporis esse nihil.",
      "Nonce": "Omnis et similique.",
      "Number": 8737398717635499000,
      "ParentHash": "Optio iure vel libero earum vitae et.",
      "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
      "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
      "Size": "Aliquid quia.",
      "StateRoot": "Eos harum.",
      "Timestamp": 7483662194381612000,
      "TotalDifficulty": "Distinctio architecto perferendis quae.",
      "TransactionCount": 1234215781114073300,
      "TransactionFees": "Sunt doloremque ex quasi aut quo.",
      "Transactions": {
        "First": false,
        "Limit": 7551599146550128000,
        "MessagesIncluded": true,
        "Result": [
          {
            "BlockHash": "Voluptatem laboriosam quidem.",
            "BlockNumber": 2775752852696174000,
            "Confirmations": 6532019680679138000,
            "ContractCodes": {
              "Sint deleniti est est quibusdam et quis.": {
                "ABI": "Eum quos.",
                "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                "Verified": false
              }
            },
            "ContractCreation": true,
            "Error": "Aut vel minus molestiae aut aliquam.",
            "Events": [
              {
                "Address": "Rerum dolorum sit aut sit.",
                "Data": "Vel in consequatur odio numquam ut.",
                "Index": 2440912512905109500,
                "Topics": [
                  "Voluptatem enim ducimus et."
                ],
                "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
              }
            ],
            "From": "Tempore voluptates voluptas aut.",
            "Gas": "Qui aut provident et neque.",
            "GasPrice": "Esse labore quo non consequatur quis molestiae.",
            "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
            "Hash": "Dolorum unde est omnis velit assumenda.",
            "Index": 9096248114404918000,
            "Input": "In distinctio doloremque magni totam possimus.",
            "Messages": [
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              },
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              }
            ],
            "Network": "Qui culpa quis laudantium molestias consequatur.",
            "Nonce": "Voluptatem magnam ea.",
            "Output": "Dicta velit debitis ea temporibus nemo.",
            "Timestamp": 4092050381628505000,
            "To": "Accusantium neque debitis numquam molestiae aut.",
            "Value": "Blanditiis est ex quos distinctio eligendi totam."
          }
        ]
      },
      "UncleReward": "Tempore voluptatem neque nisi est.",
      "Uncles": [
        "Dicta aspernatur.",
        "Dicta aspernatur.",
        "Dicta aspernatur."
      ]
    },
    {
      "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
      "CreationTime": 7052733826006029000,
      "Difficulty": "Sit aut.",
      "ExtraData": "Molestiae quidem.",
      "GasLimit": "Aut molestias magnam sunt doloremque.",
      "GasUsed": "Qui aut.",
      "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
      "LogsBloom": "Vel consequatur reprehenderit id neque.",
      "MinedInSeconds": 7897712511802021000,
      "Miner": "Autem veritatis repudiandae.",
      "MixHash": "Officia ad aut dolores.",
      "Network": "Aut tempora enim sit corporis esse nihil.",
      "Nonce": "Omnis et similique.",
      "Number": 8737398717635499000,
      "ParentHash": "Optio iure vel libero earum vitae et.",
      "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
      "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
      "Size": "Aliquid quia.",
      "StateRoot": "Eos harum.",
      "Timestamp": 7483662194381612000,
      "TotalDifficulty": "Distinctio architecto perferendis quae.",
      "TransactionCount": 1234215781114073300,
      "TransactionFees": "Sunt doloremque ex quasi aut quo.",
      "Transactions": {
        "First": false,
        "Limit": 7551599146550128000,
        "MessagesIncluded": true,
        "Result": [
          {
            "BlockHash": "Voluptatem laboriosam quidem.",
            "BlockNumber": 2775752852696174000,
            "Confirmations": 6532019680679138000,
            "ContractCodes": {
              "Sint deleniti est est quibusdam et quis.": {
                "ABI": "Eum quos.",
                "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                "Verified": false
              }
            },
            "ContractCreation": true,
            "Error": "Aut vel minus molestiae aut aliquam.",
            "Events": [
              {
                "Address": "Rerum dolorum sit aut sit.",
                "Data": "Vel in consequatur odio numquam ut.",
                "Index": 2440912512905109500,
                "Topics": [
                  "Voluptatem enim ducimus et."
                ],
                "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
              }
            ],
            "From": "Tempore voluptates voluptas aut.",
            "Gas": "Qui aut provident et neque.",
            "GasPrice": "Esse labore quo non consequatur quis molestiae.",
            "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
            "Hash": "Dolorum unde est omnis velit assumenda.",
            "Index": 9096248114404918000,
            "Input": "In distinctio doloremque magni totam possimus.",
            "Messages": [
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              },
              {
                "Error": "Quo culpa voluptatem.",
                "From": "Quo optio.",
                "Gas": "Eum in a libero esse voluptas aut.",
                "GasUsed": "Sit fugit molestiae.",
                "Input": "Et soluta.",
                "Nonce": "Odit sunt.",
                "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                "To": "Dolor temporibus placeat.",
                "Value": "Nisi a consequatur nulla saepe voluptas."
              }
            ],
            "Network": "Qui culpa quis laudantium molestias consequatur.",
            "Nonce": "Voluptatem magnam ea.",
            "Output": "Dicta velit debitis ea temporibus nemo.",
            "Timestamp": 4092050381628505000,
            "To": "Accusantium neque debitis numquam molestiae aut.",
            "Value": "Blanditiis est ex quos distinctio eligendi totam."
          }
        ]
      },
      "UncleReward": "Tempore voluptatem neque nisi est.",
      "Uncles": [
        "Dicta aspernatur.",
        "Dicta aspernatur.",
        "Dicta aspernatur."
      ]
    }
  ],
  "TotalRecords": 7269848697550577000
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
First|boolean|false|Set to true if results returned are at the begining
Limit|integer(int64)|true|Limit of number of results returned
TotalRecords|integer(int64)|true|Total number of blocks
Result|[[EthdbBlock](#schemaethdbblock)]|false|Ethereum Block (default view)
» BeneficiaryReward|string|true|Reward for mining a block.  Includes the base reward, reward for including Uncle blocks and the fees of Transactions included in the Block
» CreationTime|integer(int64)|true|Timestamp of Block creation in Unix timestamp format
» Difficulty|string|true|Difficulty level of this block
» ExtraData|string|true|Data included in the Block by the Miner
» GasLimit|string|true|Gas limit for this Block
» GasUsed|string|true|Sum of gas used by transactions included in this Block
» Hash|string|true|Keccak-256 hash of the Block header
» LogsBloom|string|false|Bloom filter of indexable information included in the Block receipt Events
» MinedInSeconds|integer(int64)|true|Number of seconds to mine this block
» Miner|string|true|Address of miner that created the block
» MixHash|string|false|Hash which proves Proof of Work for this Block has been completed
» Network|string|true|Network ID
» Nonce|string|false|Hash to be used in Proof of Work calculation
» Number|integer(int64)|true|Block number
» ParentHash|string|true|Hash of Parent Block
» ReceiptsRoot|string|false|Hash of receipts
» SHA3Uncles|string|true|Hash of Uncles included in Block
» Size|string|false|Size of the Block header in bytes
» StateRoot|string|false|No description
» Timestamp|integer(int64)|true|When this block was mined, in UNIX format
» TotalDifficulty|string|true|Total network difficulty when this block was mined
» TransactionCount|integer(int64)|true|No description
» TransactionFees|string|true|Sum of gas used of all transactions included in this block
» Transactions|[EthdbTransactions](#schemaethdbtransactions)|true|A list of Ethereum transactions (default view)
»» First|boolean|false|Set to true if results returned are at the beginning
»» Limit|integer(int64)|true|Limit of number of results returned
»» MessagesIncluded|boolean|true|Set to true if results include transaction messages
»» Result|[[EthdbTransaction](#schemaethdbtransaction)]|false|Ethereum Transaction (default view)
»»» BlockHash|string|true|Hash of Block this Transaction is included in
»»» BlockNumber|integer(int64)|true|Height of Block this Transaction is included in
»»» Confirmations|integer(int64)|true|Number of confirmations for this transaction
»»» ContractCodes|object|false|If the transactions or messages are sent to a contract, information about the contract is returned if available
»»» ContractCreation|boolean|false|This flag is set if the transaction creates a new contract
»»» Error|string|true|Error message from the execution of this transaction, if any
»»» From|string|true|Transaction creator address
»»» Gas|string|true|Total gas supplied by this Transaction
»»» GasPrice|string|true|Price in Wei of Gas supplied by this Transaction
»»» GasUsed|string|true|Gas Used in this Transactions
»»» Hash|string|true|Hash
»»» Index|integer(int64)|true|Position of Transaction in the Block
»»» Input|string|true|Transaction function call information
»»» Network|string|true|Network ID of transaction
»»» Nonce|string|true|Transaction nonce
»»» Output|string|true|Transaction output - the result of calling a contract function
»»» Timestamp|integer(int64)|true|Timestamp of when this Transaction was included a Block. In Unix timestamp format.
»»» To|string|true|Transaction destination address
»»» Value|string|true|Ethereum value transfered by this transation
»»» Events|[[EthdbEvent](#schemaethdbevent)]|false|Event Log event (default view)
»»»» Address|string|true|Address of Account
»»»» Data|string|true|Event data
»»»» Index|integer(int64)|true|Index of Event generated by Transaction
»»»» TransactionHash|string|true|Hash of Transaction which generated this Event
»»»» Topics|[string]|false|No description
»»» Messages|[[EthdbMessage](#schemaethdbmessage)]|false|Transaction Internal message (default view)
»»»» Error|string|true|Error message (if any) from executing of this message
»»»» From|string|true|Transaction creator address
»»»» Gas|string|true|Total gas supplied by this Transaction
»»»» GasUsed|string|true|Gas Used in this Transactions
»»»» Input|string|true|Transaction function call information
»»»» Nonce|string|true|Transaction nonce
»»»» Position|string|true|Position of this message in the EVM call stack
»»»» To|string|true|Transaction destination address
»»»» Value|string|true|Ethereum value transfered by this transation
» UncleReward|string|true|Amount rewarded to miner for including Uncles in this block
» Uncles|[string]|false|No description



## EthdbContractcode

<a name="schemaethdbcontractcode"></a>

```json
{
  "ABI": "Eum quos.",
  "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
  "Verified": false
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
ABI|string|false|Contract ABI
Bytecode|string|true|Bytecode of contract
Verified|boolean|true|If the source code for this contract has been recompiled and matches the bytecode deployed on the Blockchain



## EthdbEvent

<a name="schemaethdbevent"></a>

```json
{
  "Address": "Rerum dolorum sit aut sit.",
  "Data": "Vel in consequatur odio numquam ut.",
  "Index": 2440912512905109500,
  "Topics": [
    "Voluptatem enim ducimus et."
  ],
  "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
Address|string|true|Address of Account
Data|string|true|Event data
Index|integer(int64)|true|Index of Event generated by Transaction
TransactionHash|string|true|Hash of Transaction which generated this Event
Topics|[string]|false|No description



## EthdbMessage

<a name="schemaethdbmessage"></a>

```json
{
  "Error": "Quo culpa voluptatem.",
  "From": "Quo optio.",
  "Gas": "Eum in a libero esse voluptas aut.",
  "GasUsed": "Sit fugit molestiae.",
  "Input": "Et soluta.",
  "Nonce": "Odit sunt.",
  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
  "To": "Dolor temporibus placeat.",
  "Value": "Nisi a consequatur nulla saepe voluptas."
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
Error|string|true|Error message (if any) from executing of this message
From|string|true|Transaction creator address
Gas|string|true|Total gas supplied by this Transaction
GasUsed|string|true|Gas Used in this Transactions
Input|string|true|Transaction function call information
Nonce|string|true|Transaction nonce
Position|string|true|Position of this message in the EVM call stack
To|string|true|Transaction destination address
Value|string|true|Ethereum value transfered by this transation



## EthdbNetwork

<a name="schemaethdbnetwork"></a>

```json
{
  "BlockHeight": 2249756891723881000,
  "BlockReward": "Facere consequatur numquam labore.",
  "Blocks": {
    "First": true,
    "Limit": 8813805051874942000,
    "Result": [
      {
        "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
        "CreationTime": 7052733826006029000,
        "Difficulty": "Sit aut.",
        "ExtraData": "Molestiae quidem.",
        "GasLimit": "Aut molestias magnam sunt doloremque.",
        "GasUsed": "Qui aut.",
        "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
        "LogsBloom": "Vel consequatur reprehenderit id neque.",
        "MinedInSeconds": 7897712511802021000,
        "Miner": "Autem veritatis repudiandae.",
        "MixHash": "Officia ad aut dolores.",
        "Network": "Aut tempora enim sit corporis esse nihil.",
        "Nonce": "Omnis et similique.",
        "Number": 8737398717635499000,
        "ParentHash": "Optio iure vel libero earum vitae et.",
        "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
        "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
        "Size": "Aliquid quia.",
        "StateRoot": "Eos harum.",
        "Timestamp": 7483662194381612000,
        "TotalDifficulty": "Distinctio architecto perferendis quae.",
        "TransactionCount": 1234215781114073300,
        "TransactionFees": "Sunt doloremque ex quasi aut quo.",
        "Transactions": {
          "First": false,
          "Limit": 7551599146550128000,
          "MessagesIncluded": true,
          "Result": [
            {
              "BlockHash": "Voluptatem laboriosam quidem.",
              "BlockNumber": 2775752852696174000,
              "Confirmations": 6532019680679138000,
              "ContractCodes": {
                "Sint deleniti est est quibusdam et quis.": {
                  "ABI": "Eum quos.",
                  "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                  "Verified": false
                }
              },
              "ContractCreation": true,
              "Error": "Aut vel minus molestiae aut aliquam.",
              "Events": [
                {
                  "Address": "Rerum dolorum sit aut sit.",
                  "Data": "Vel in consequatur odio numquam ut.",
                  "Index": 2440912512905109500,
                  "Topics": [
                    "Voluptatem enim ducimus et."
                  ],
                  "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                }
              ],
              "From": "Tempore voluptates voluptas aut.",
              "Gas": "Qui aut provident et neque.",
              "GasPrice": "Esse labore quo non consequatur quis molestiae.",
              "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
              "Hash": "Dolorum unde est omnis velit assumenda.",
              "Index": 9096248114404918000,
              "Input": "In distinctio doloremque magni totam possimus.",
              "Messages": [
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                },
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                }
              ],
              "Network": "Qui culpa quis laudantium molestias consequatur.",
              "Nonce": "Voluptatem magnam ea.",
              "Output": "Dicta velit debitis ea temporibus nemo.",
              "Timestamp": 4092050381628505000,
              "To": "Accusantium neque debitis numquam molestiae aut.",
              "Value": "Blanditiis est ex quos distinctio eligendi totam."
            }
          ]
        },
        "UncleReward": "Tempore voluptatem neque nisi est.",
        "Uncles": [
          "Dicta aspernatur.",
          "Dicta aspernatur.",
          "Dicta aspernatur."
        ]
      },
      {
        "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
        "CreationTime": 7052733826006029000,
        "Difficulty": "Sit aut.",
        "ExtraData": "Molestiae quidem.",
        "GasLimit": "Aut molestias magnam sunt doloremque.",
        "GasUsed": "Qui aut.",
        "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
        "LogsBloom": "Vel consequatur reprehenderit id neque.",
        "MinedInSeconds": 7897712511802021000,
        "Miner": "Autem veritatis repudiandae.",
        "MixHash": "Officia ad aut dolores.",
        "Network": "Aut tempora enim sit corporis esse nihil.",
        "Nonce": "Omnis et similique.",
        "Number": 8737398717635499000,
        "ParentHash": "Optio iure vel libero earum vitae et.",
        "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
        "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
        "Size": "Aliquid quia.",
        "StateRoot": "Eos harum.",
        "Timestamp": 7483662194381612000,
        "TotalDifficulty": "Distinctio architecto perferendis quae.",
        "TransactionCount": 1234215781114073300,
        "TransactionFees": "Sunt doloremque ex quasi aut quo.",
        "Transactions": {
          "First": false,
          "Limit": 7551599146550128000,
          "MessagesIncluded": true,
          "Result": [
            {
              "BlockHash": "Voluptatem laboriosam quidem.",
              "BlockNumber": 2775752852696174000,
              "Confirmations": 6532019680679138000,
              "ContractCodes": {
                "Sint deleniti est est quibusdam et quis.": {
                  "ABI": "Eum quos.",
                  "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                  "Verified": false
                }
              },
              "ContractCreation": true,
              "Error": "Aut vel minus molestiae aut aliquam.",
              "Events": [
                {
                  "Address": "Rerum dolorum sit aut sit.",
                  "Data": "Vel in consequatur odio numquam ut.",
                  "Index": 2440912512905109500,
                  "Topics": [
                    "Voluptatem enim ducimus et."
                  ],
                  "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                }
              ],
              "From": "Tempore voluptates voluptas aut.",
              "Gas": "Qui aut provident et neque.",
              "GasPrice": "Esse labore quo non consequatur quis molestiae.",
              "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
              "Hash": "Dolorum unde est omnis velit assumenda.",
              "Index": 9096248114404918000,
              "Input": "In distinctio doloremque magni totam possimus.",
              "Messages": [
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                },
                {
                  "Error": "Quo culpa voluptatem.",
                  "From": "Quo optio.",
                  "Gas": "Eum in a libero esse voluptas aut.",
                  "GasUsed": "Sit fugit molestiae.",
                  "Input": "Et soluta.",
                  "Nonce": "Odit sunt.",
                  "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                  "To": "Dolor temporibus placeat.",
                  "Value": "Nisi a consequatur nulla saepe voluptas."
                }
              ],
              "Network": "Qui culpa quis laudantium molestias consequatur.",
              "Nonce": "Voluptatem magnam ea.",
              "Output": "Dicta velit debitis ea temporibus nemo.",
              "Timestamp": 4092050381628505000,
              "To": "Accusantium neque debitis numquam molestiae aut.",
              "Value": "Blanditiis est ex quos distinctio eligendi totam."
            }
          ]
        },
        "UncleReward": "Tempore voluptatem neque nisi est.",
        "Uncles": [
          "Dicta aspernatur.",
          "Dicta aspernatur.",
          "Dicta aspernatur."
        ]
      }
    ],
    "TotalRecords": 7269848697550577000
  },
  "Difficulty": "Maiores aut dolorem.",
  "GasLimit": "Nulla eligendi libero modi et et iusto.",
  "GenesisHash": "Fugit harum deleniti.",
  "HashRate": "Quam ut unde et.",
  "ID": "Quas voluptas nostrum quos.",
  "Name": "Voluptatem voluptas autem earum quaerat similique sint.",
  "PendingTransactions": {
    "First": false,
    "Limit": 7551599146550128000,
    "MessagesIncluded": true,
    "Result": [
      {
        "BlockHash": "Voluptatem laboriosam quidem.",
        "BlockNumber": 2775752852696174000,
        "Confirmations": 6532019680679138000,
        "ContractCodes": {
          "Sint deleniti est est quibusdam et quis.": {
            "ABI": "Eum quos.",
            "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
            "Verified": false
          }
        },
        "ContractCreation": true,
        "Error": "Aut vel minus molestiae aut aliquam.",
        "Events": [
          {
            "Address": "Rerum dolorum sit aut sit.",
            "Data": "Vel in consequatur odio numquam ut.",
            "Index": 2440912512905109500,
            "Topics": [
              "Voluptatem enim ducimus et."
            ],
            "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
          }
        ],
        "From": "Tempore voluptates voluptas aut.",
        "Gas": "Qui aut provident et neque.",
        "GasPrice": "Esse labore quo non consequatur quis molestiae.",
        "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
        "Hash": "Dolorum unde est omnis velit assumenda.",
        "Index": 9096248114404918000,
        "Input": "In distinctio doloremque magni totam possimus.",
        "Messages": [
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          },
          {
            "Error": "Quo culpa voluptatem.",
            "From": "Quo optio.",
            "Gas": "Eum in a libero esse voluptas aut.",
            "GasUsed": "Sit fugit molestiae.",
            "Input": "Et soluta.",
            "Nonce": "Odit sunt.",
            "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
            "To": "Dolor temporibus placeat.",
            "Value": "Nisi a consequatur nulla saepe voluptas."
          }
        ],
        "Network": "Qui culpa quis laudantium molestias consequatur.",
        "Nonce": "Voluptatem magnam ea.",
        "Output": "Dicta velit debitis ea temporibus nemo.",
        "Timestamp": 4092050381628505000,
        "To": "Accusantium neque debitis numquam molestiae aut.",
        "Value": "Blanditiis est ex quos distinctio eligendi totam."
      }
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
BlockHeight|integer(int64)|true|Height of last known block for this network
BlockReward|string|false|Miner block reward amount, in Wei, hex format
Blocks|[EthdbBlocks](#schemaethdbblocks)|false|A list of Ethereum blocks (default view)
» First|boolean|false|Set to true if results returned are at the begining
» Limit|integer(int64)|true|Limit of number of results returned
» TotalRecords|integer(int64)|true|Total number of blocks
» Result|[[EthdbBlock](#schemaethdbblock)]|false|Ethereum Block (default view)
»» BeneficiaryReward|string|true|Reward for mining a block.  Includes the base reward, reward for including Uncle blocks and the fees of Transactions included in the Block
»» CreationTime|integer(int64)|true|Timestamp of Block creation in Unix timestamp format
»» Difficulty|string|true|Difficulty level of this block
»» ExtraData|string|true|Data included in the Block by the Miner
»» GasLimit|string|true|Gas limit for this Block
»» GasUsed|string|true|Sum of gas used by transactions included in this Block
»» Hash|string|true|Keccak-256 hash of the Block header
»» LogsBloom|string|false|Bloom filter of indexable information included in the Block receipt Events
»» MinedInSeconds|integer(int64)|true|Number of seconds to mine this block
»» Miner|string|true|Address of miner that created the block
»» MixHash|string|false|Hash which proves Proof of Work for this Block has been completed
»» Network|string|true|Network ID
»» Nonce|string|false|Hash to be used in Proof of Work calculation
»» Number|integer(int64)|true|Block number
»» ParentHash|string|true|Hash of Parent Block
»» ReceiptsRoot|string|false|Hash of receipts
»» SHA3Uncles|string|true|Hash of Uncles included in Block
»» Size|string|false|Size of the Block header in bytes
»» StateRoot|string|false|No description
»» Timestamp|integer(int64)|true|When this block was mined, in UNIX format
»» TotalDifficulty|string|true|Total network difficulty when this block was mined
»» TransactionCount|integer(int64)|true|No description
»» TransactionFees|string|true|Sum of gas used of all transactions included in this block
»» Transactions|[EthdbTransactions](#schemaethdbtransactions)|true|A list of Ethereum transactions (default view)
»»» First|boolean|false|Set to true if results returned are at the beginning
»»» Limit|integer(int64)|true|Limit of number of results returned
»»» MessagesIncluded|boolean|true|Set to true if results include transaction messages
»»» Result|[[EthdbTransaction](#schemaethdbtransaction)]|false|Ethereum Transaction (default view)
»»»» BlockHash|string|true|Hash of Block this Transaction is included in
»»»» BlockNumber|integer(int64)|true|Height of Block this Transaction is included in
»»»» Confirmations|integer(int64)|true|Number of confirmations for this transaction
»»»» ContractCodes|object|false|If the transactions or messages are sent to a contract, information about the contract is returned if available
»»»» ContractCreation|boolean|false|This flag is set if the transaction creates a new contract
»»»» Error|string|true|Error message from the execution of this transaction, if any
»»»» From|string|true|Transaction creator address
»»»» Gas|string|true|Total gas supplied by this Transaction
»»»» GasPrice|string|true|Price in Wei of Gas supplied by this Transaction
»»»» GasUsed|string|true|Gas Used in this Transactions
»»»» Hash|string|true|Hash
»»»» Index|integer(int64)|true|Position of Transaction in the Block
»»»» Input|string|true|Transaction function call information
»»»» Network|string|true|Network ID of transaction
»»»» Nonce|string|true|Transaction nonce
»»»» Output|string|true|Transaction output - the result of calling a contract function
»»»» Timestamp|integer(int64)|true|Timestamp of when this Transaction was included a Block. In Unix timestamp format.
»»»» To|string|true|Transaction destination address
»»»» Value|string|true|Ethereum value transfered by this transation
»»»» Events|[[EthdbEvent](#schemaethdbevent)]|false|Event Log event (default view)
»»»»» Address|string|true|Address of Account
»»»»» Data|string|true|Event data
»»»»» Index|integer(int64)|true|Index of Event generated by Transaction
»»»»» TransactionHash|string|true|Hash of Transaction which generated this Event
»»»»» Topics|[string]|false|No description
»»»» Messages|[[EthdbMessage](#schemaethdbmessage)]|false|Transaction Internal message (default view)
»»»»» Error|string|true|Error message (if any) from executing of this message
»»»»» From|string|true|Transaction creator address
»»»»» Gas|string|true|Total gas supplied by this Transaction
»»»»» GasUsed|string|true|Gas Used in this Transactions
»»»»» Input|string|true|Transaction function call information
»»»»» Nonce|string|true|Transaction nonce
»»»»» Position|string|true|Position of this message in the EVM call stack
»»»»» To|string|true|Transaction destination address
»»»»» Value|string|true|Ethereum value transfered by this transation
»» UncleReward|string|true|Amount rewarded to miner for including Uncles in this block
»» Uncles|[string]|false|No description
Difficulty|string|false|Total network difficulty
GasLimit|string|false|Network gas limit per block
GenesisHash|string|true|Hash of Genesis block
HashRate|string|false|Total network hash rate
ID|string|true|Network ID
Name|string|true|Network name



## EthdbNetworkCollection

<a name="schemaethdbnetworkcollection"></a>

```json
[
  {
    "BlockHeight": 2249756891723881000,
    "BlockReward": "Facere consequatur numquam labore.",
    "Blocks": {
      "First": true,
      "Limit": 8813805051874942000,
      "Result": [
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        },
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        }
      ],
      "TotalRecords": 7269848697550577000
    },
    "Difficulty": "Maiores aut dolorem.",
    "GasLimit": "Nulla eligendi libero modi et et iusto.",
    "GenesisHash": "Fugit harum deleniti.",
    "HashRate": "Quam ut unde et.",
    "ID": "Quas voluptas nostrum quos.",
    "Name": "Voluptatem voluptas autem earum quaerat similique sint.",
    "PendingTransactions": {
      "First": false,
      "Limit": 7551599146550128000,
      "MessagesIncluded": true,
      "Result": [
        {
          "BlockHash": "Voluptatem laboriosam quidem.",
          "BlockNumber": 2775752852696174000,
          "Confirmations": 6532019680679138000,
          "ContractCodes": {
            "Sint deleniti est est quibusdam et quis.": {
              "ABI": "Eum quos.",
              "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
              "Verified": false
            }
          },
          "ContractCreation": true,
          "Error": "Aut vel minus molestiae aut aliquam.",
          "Events": [
            {
              "Address": "Rerum dolorum sit aut sit.",
              "Data": "Vel in consequatur odio numquam ut.",
              "Index": 2440912512905109500,
              "Topics": [
                "Voluptatem enim ducimus et."
              ],
              "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
            }
          ],
          "From": "Tempore voluptates voluptas aut.",
          "Gas": "Qui aut provident et neque.",
          "GasPrice": "Esse labore quo non consequatur quis molestiae.",
          "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
          "Hash": "Dolorum unde est omnis velit assumenda.",
          "Index": 9096248114404918000,
          "Input": "In distinctio doloremque magni totam possimus.",
          "Messages": [
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            },
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            }
          ],
          "Network": "Qui culpa quis laudantium molestias consequatur.",
          "Nonce": "Voluptatem magnam ea.",
          "Output": "Dicta velit debitis ea temporibus nemo.",
          "Timestamp": 4092050381628505000,
          "To": "Accusantium neque debitis numquam molestiae aut.",
          "Value": "Blanditiis est ex quos distinctio eligendi totam."
        }
      ]
    }
  },
  {
    "BlockHeight": 2249756891723881000,
    "BlockReward": "Facere consequatur numquam labore.",
    "Blocks": {
      "First": true,
      "Limit": 8813805051874942000,
      "Result": [
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        },
        {
          "BeneficiaryReward": "Vel doloremque explicabo aut aut voluptas.",
          "CreationTime": 7052733826006029000,
          "Difficulty": "Sit aut.",
          "ExtraData": "Molestiae quidem.",
          "GasLimit": "Aut molestias magnam sunt doloremque.",
          "GasUsed": "Qui aut.",
          "Hash": "Non perspiciatis perspiciatis officiis ducimus beatae voluptas.",
          "LogsBloom": "Vel consequatur reprehenderit id neque.",
          "MinedInSeconds": 7897712511802021000,
          "Miner": "Autem veritatis repudiandae.",
          "MixHash": "Officia ad aut dolores.",
          "Network": "Aut tempora enim sit corporis esse nihil.",
          "Nonce": "Omnis et similique.",
          "Number": 8737398717635499000,
          "ParentHash": "Optio iure vel libero earum vitae et.",
          "ReceiptsRoot": "Illum voluptatibus autem sit sequi recusandae.",
          "SHA3Uncles": "Ratione quaerat deserunt repellendus sit aliquid rem.",
          "Size": "Aliquid quia.",
          "StateRoot": "Eos harum.",
          "Timestamp": 7483662194381612000,
          "TotalDifficulty": "Distinctio architecto perferendis quae.",
          "TransactionCount": 1234215781114073300,
          "TransactionFees": "Sunt doloremque ex quasi aut quo.",
          "Transactions": {
            "First": false,
            "Limit": 7551599146550128000,
            "MessagesIncluded": true,
            "Result": [
              {
                "BlockHash": "Voluptatem laboriosam quidem.",
                "BlockNumber": 2775752852696174000,
                "Confirmations": 6532019680679138000,
                "ContractCodes": {
                  "Sint deleniti est est quibusdam et quis.": {
                    "ABI": "Eum quos.",
                    "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
                    "Verified": false
                  }
                },
                "ContractCreation": true,
                "Error": "Aut vel minus molestiae aut aliquam.",
                "Events": [
                  {
                    "Address": "Rerum dolorum sit aut sit.",
                    "Data": "Vel in consequatur odio numquam ut.",
                    "Index": 2440912512905109500,
                    "Topics": [
                      "Voluptatem enim ducimus et."
                    ],
                    "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
                  }
                ],
                "From": "Tempore voluptates voluptas aut.",
                "Gas": "Qui aut provident et neque.",
                "GasPrice": "Esse labore quo non consequatur quis molestiae.",
                "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
                "Hash": "Dolorum unde est omnis velit assumenda.",
                "Index": 9096248114404918000,
                "Input": "In distinctio doloremque magni totam possimus.",
                "Messages": [
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  },
                  {
                    "Error": "Quo culpa voluptatem.",
                    "From": "Quo optio.",
                    "Gas": "Eum in a libero esse voluptas aut.",
                    "GasUsed": "Sit fugit molestiae.",
                    "Input": "Et soluta.",
                    "Nonce": "Odit sunt.",
                    "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
                    "To": "Dolor temporibus placeat.",
                    "Value": "Nisi a consequatur nulla saepe voluptas."
                  }
                ],
                "Network": "Qui culpa quis laudantium molestias consequatur.",
                "Nonce": "Voluptatem magnam ea.",
                "Output": "Dicta velit debitis ea temporibus nemo.",
                "Timestamp": 4092050381628505000,
                "To": "Accusantium neque debitis numquam molestiae aut.",
                "Value": "Blanditiis est ex quos distinctio eligendi totam."
              }
            ]
          },
          "UncleReward": "Tempore voluptatem neque nisi est.",
          "Uncles": [
            "Dicta aspernatur.",
            "Dicta aspernatur.",
            "Dicta aspernatur."
          ]
        }
      ],
      "TotalRecords": 7269848697550577000
    },
    "Difficulty": "Maiores aut dolorem.",
    "GasLimit": "Nulla eligendi libero modi et et iusto.",
    "GenesisHash": "Fugit harum deleniti.",
    "HashRate": "Quam ut unde et.",
    "ID": "Quas voluptas nostrum quos.",
    "Name": "Voluptatem voluptas autem earum quaerat similique sint.",
    "PendingTransactions": {
      "First": false,
      "Limit": 7551599146550128000,
      "MessagesIncluded": true,
      "Result": [
        {
          "BlockHash": "Voluptatem laboriosam quidem.",
          "BlockNumber": 2775752852696174000,
          "Confirmations": 6532019680679138000,
          "ContractCodes": {
            "Sint deleniti est est quibusdam et quis.": {
              "ABI": "Eum quos.",
              "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
              "Verified": false
            }
          },
          "ContractCreation": true,
          "Error": "Aut vel minus molestiae aut aliquam.",
          "Events": [
            {
              "Address": "Rerum dolorum sit aut sit.",
              "Data": "Vel in consequatur odio numquam ut.",
              "Index": 2440912512905109500,
              "Topics": [
                "Voluptatem enim ducimus et."
              ],
              "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
            }
          ],
          "From": "Tempore voluptates voluptas aut.",
          "Gas": "Qui aut provident et neque.",
          "GasPrice": "Esse labore quo non consequatur quis molestiae.",
          "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
          "Hash": "Dolorum unde est omnis velit assumenda.",
          "Index": 9096248114404918000,
          "Input": "In distinctio doloremque magni totam possimus.",
          "Messages": [
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            },
            {
              "Error": "Quo culpa voluptatem.",
              "From": "Quo optio.",
              "Gas": "Eum in a libero esse voluptas aut.",
              "GasUsed": "Sit fugit molestiae.",
              "Input": "Et soluta.",
              "Nonce": "Odit sunt.",
              "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
              "To": "Dolor temporibus placeat.",
              "Value": "Nisi a consequatur nulla saepe voluptas."
            }
          ],
          "Network": "Qui culpa quis laudantium molestias consequatur.",
          "Nonce": "Voluptatem magnam ea.",
          "Output": "Dicta velit debitis ea temporibus nemo.",
          "Timestamp": 4092050381628505000,
          "To": "Accusantium neque debitis numquam molestiae aut.",
          "Value": "Blanditiis est ex quos distinctio eligendi totam."
        }
      ]
    }
  }
] 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
anonymous|[[EthdbNetwork](#schemaethdbnetwork)]|false|Ethereum Blockchain network (default view)
» BlockHeight|integer(int64)|true|Height of last known block for this network
» BlockReward|string|false|Miner block reward amount, in Wei, hex format
» Blocks|[EthdbBlocks](#schemaethdbblocks)|false|A list of Ethereum blocks (default view)
»» First|boolean|false|Set to true if results returned are at the begining
»» Limit|integer(int64)|true|Limit of number of results returned
»» TotalRecords|integer(int64)|true|Total number of blocks
»» Result|[[EthdbBlock](#schemaethdbblock)]|false|Ethereum Block (default view)
»»» BeneficiaryReward|string|true|Reward for mining a block.  Includes the base reward, reward for including Uncle blocks and the fees of Transactions included in the Block
»»» CreationTime|integer(int64)|true|Timestamp of Block creation in Unix timestamp format
»»» Difficulty|string|true|Difficulty level of this block
»»» ExtraData|string|true|Data included in the Block by the Miner
»»» GasLimit|string|true|Gas limit for this Block
»»» GasUsed|string|true|Sum of gas used by transactions included in this Block
»»» Hash|string|true|Keccak-256 hash of the Block header
»»» LogsBloom|string|false|Bloom filter of indexable information included in the Block receipt Events
»»» MinedInSeconds|integer(int64)|true|Number of seconds to mine this block
»»» Miner|string|true|Address of miner that created the block
»»» MixHash|string|false|Hash which proves Proof of Work for this Block has been completed
»»» Network|string|true|Network ID
»»» Nonce|string|false|Hash to be used in Proof of Work calculation
»»» Number|integer(int64)|true|Block number
»»» ParentHash|string|true|Hash of Parent Block
»»» ReceiptsRoot|string|false|Hash of receipts
»»» SHA3Uncles|string|true|Hash of Uncles included in Block
»»» Size|string|false|Size of the Block header in bytes
»»» StateRoot|string|false|No description
»»» Timestamp|integer(int64)|true|When this block was mined, in UNIX format
»»» TotalDifficulty|string|true|Total network difficulty when this block was mined
»»» TransactionCount|integer(int64)|true|No description
»»» TransactionFees|string|true|Sum of gas used of all transactions included in this block
»»» Transactions|[EthdbTransactions](#schemaethdbtransactions)|true|A list of Ethereum transactions (default view)
»»»» First|boolean|false|Set to true if results returned are at the beginning
»»»» Limit|integer(int64)|true|Limit of number of results returned
»»»» MessagesIncluded|boolean|true|Set to true if results include transaction messages
»»»» Result|[[EthdbTransaction](#schemaethdbtransaction)]|false|Ethereum Transaction (default view)
»»»»» BlockHash|string|true|Hash of Block this Transaction is included in
»»»»» BlockNumber|integer(int64)|true|Height of Block this Transaction is included in
»»»»» Confirmations|integer(int64)|true|Number of confirmations for this transaction
»»»»» ContractCodes|object|false|If the transactions or messages are sent to a contract, information about the contract is returned if available
»»»»» ContractCreation|boolean|false|This flag is set if the transaction creates a new contract
»»»»» Error|string|true|Error message from the execution of this transaction, if any
»»»»» From|string|true|Transaction creator address
»»»»» Gas|string|true|Total gas supplied by this Transaction
»»»»» GasPrice|string|true|Price in Wei of Gas supplied by this Transaction
»»»»» GasUsed|string|true|Gas Used in this Transactions
»»»»» Hash|string|true|Hash
»»»»» Index|integer(int64)|true|Position of Transaction in the Block
»»»»» Input|string|true|Transaction function call information
»»»»» Network|string|true|Network ID of transaction
»»»»» Nonce|string|true|Transaction nonce
»»»»» Output|string|true|Transaction output - the result of calling a contract function
»»»»» Timestamp|integer(int64)|true|Timestamp of when this Transaction was included a Block. In Unix timestamp format.
»»»»» To|string|true|Transaction destination address
»»»»» Value|string|true|Ethereum value transfered by this transation
»»»»» Events|[[EthdbEvent](#schemaethdbevent)]|false|Event Log event (default view)
»»»»»» Address|string|true|Address of Account
»»»»»» Data|string|true|Event data
»»»»»» Index|integer(int64)|true|Index of Event generated by Transaction
»»»»»» TransactionHash|string|true|Hash of Transaction which generated this Event
»»»»»» Topics|[string]|false|No description
»»»»» Messages|[[EthdbMessage](#schemaethdbmessage)]|false|Transaction Internal message (default view)
»»»»»» Error|string|true|Error message (if any) from executing of this message
»»»»»» From|string|true|Transaction creator address
»»»»»» Gas|string|true|Total gas supplied by this Transaction
»»»»»» GasUsed|string|true|Gas Used in this Transactions
»»»»»» Input|string|true|Transaction function call information
»»»»»» Nonce|string|true|Transaction nonce
»»»»»» Position|string|true|Position of this message in the EVM call stack
»»»»»» To|string|true|Transaction destination address
»»»»»» Value|string|true|Ethereum value transfered by this transation
»»» UncleReward|string|true|Amount rewarded to miner for including Uncles in this block
»»» Uncles|[string]|false|No description
» Difficulty|string|false|Total network difficulty
» GasLimit|string|false|Network gas limit per block
» GenesisHash|string|true|Hash of Genesis block
» HashRate|string|false|Total network hash rate
» ID|string|true|Network ID
» Name|string|true|Network name



## EthdbSource

<a name="schemaethdbsource"></a>

```json
{
  "BlockchainContracts": [
    {
      "Address": "Numquam aut inventore.",
      "Contract": "Sit nostrum dolorem.",
      "Network": "Necessitatibus laudantium eligendi."
    },
    {
      "Address": "Numquam aut inventore.",
      "Contract": "Sit nostrum dolorem.",
      "Network": "Necessitatibus laudantium eligendi."
    }
  ],
  "Bytecode": {
    "Facilis quia quia fuga libero ut.": {
      "ABI": "Cumque optio aut qui.",
      "Bytecode": "Quasi quasi cupiditate ex quos quis eos.",
      "Compiler": "Sapiente voluptatem magnam quod rerum quia ab.",
      "Optimized": false
    }
  },
  "EthPM": "Molestiae necessitatibus repellendus reprehenderit.",
  "Name": "Harum natus consequatur qui.",
  "Readme": "Porro architecto.",
  "SourceFiles": [
    {
      "CanonicalURL": "Corrupti aut esse eligendi.",
      "Filename": "Dolor facere officia molestias ab.",
      "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
      "Source": "Veniam corrupti expedita est est soluta maxime.",
      "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
    },
    {
      "CanonicalURL": "Corrupti aut esse eligendi.",
      "Filename": "Dolor facere officia molestias ab.",
      "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
      "Source": "Veniam corrupti expedita est est soluta maxime.",
      "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
    }
  ],
  "Type": "Dicta ipsa id impedit omnis velit autem.",
  "URL": "Debitis pariatur nihil non.",
  "Version": "Labore ut corrupti.",
  "Versions": [
    "Iste possimus ipsa eos earum saepe quidem.",
    "Iste possimus ipsa eos earum saepe quidem.",
    "Iste possimus ipsa eos earum saepe quidem."
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
Bytecode|object|true|Source package compiled into EVM bytecode
EthPM|string|true|Ethereum package manager JSON file
Name|string|true|Name
Readme|string|true|Description of source package
Type|string|true|Type of package.  Can be 'github'
URL|string|true|URL to canonical source repo
Version|string|true|Version of this source package
BlockchainContracts|[[EthdbBlockchaincontract](#schemaethdbblockchaincontract)]|false|Listing of contract deployed on the blockchain (default view)
» Address|string|true|Contract address
» Contract|string|true|Compiled contract name
» Network|string|true|Blockchain name
SourceFiles|[[EthdbSourcefile](#schemaethdbsourcefile)]|false|Source code package (default view)
» CanonicalURL|string|true|Link to orignal version of this file
» Filename|string|true|File name
» Language|string|true|Source code programming language
» Source|string|true|Source code
» Version|string|true|Source code version
Versions|[string]|false|No description



## EthdbSourceCollection

<a name="schemaethdbsourcecollection"></a>

```json
[
  {
    "BlockchainContracts": [
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      },
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      }
    ],
    "Bytecode": {
      "Facilis quia quia fuga libero ut.": {
        "ABI": "Cumque optio aut qui.",
        "Bytecode": "Quasi quasi cupiditate ex quos quis eos.",
        "Compiler": "Sapiente voluptatem magnam quod rerum quia ab.",
        "Optimized": false
      }
    },
    "EthPM": "Molestiae necessitatibus repellendus reprehenderit.",
    "Name": "Harum natus consequatur qui.",
    "Readme": "Porro architecto.",
    "SourceFiles": [
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      },
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      }
    ],
    "Type": "Dicta ipsa id impedit omnis velit autem.",
    "URL": "Debitis pariatur nihil non.",
    "Version": "Labore ut corrupti.",
    "Versions": [
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem."
    ]
  },
  {
    "BlockchainContracts": [
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      },
      {
        "Address": "Numquam aut inventore.",
        "Contract": "Sit nostrum dolorem.",
        "Network": "Necessitatibus laudantium eligendi."
      }
    ],
    "Bytecode": {
      "Facilis quia quia fuga libero ut.": {
        "ABI": "Cumque optio aut qui.",
        "Bytecode": "Quasi quasi cupiditate ex quos quis eos.",
        "Compiler": "Sapiente voluptatem magnam quod rerum quia ab.",
        "Optimized": false
      }
    },
    "EthPM": "Molestiae necessitatibus repellendus reprehenderit.",
    "Name": "Harum natus consequatur qui.",
    "Readme": "Porro architecto.",
    "SourceFiles": [
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      },
      {
        "CanonicalURL": "Corrupti aut esse eligendi.",
        "Filename": "Dolor facere officia molestias ab.",
        "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
        "Source": "Veniam corrupti expedita est est soluta maxime.",
        "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
      }
    ],
    "Type": "Dicta ipsa id impedit omnis velit autem.",
    "URL": "Debitis pariatur nihil non.",
    "Version": "Labore ut corrupti.",
    "Versions": [
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem.",
      "Iste possimus ipsa eos earum saepe quidem."
    ]
  }
] 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
anonymous|[[EthdbSource](#schemaethdbsource)]|false|Source code package (default view)
» Bytecode|object|true|Source package compiled into EVM bytecode
» EthPM|string|true|Ethereum package manager JSON file
» Name|string|true|Name
» Readme|string|true|Description of source package
» Type|string|true|Type of package.  Can be 'github'
» URL|string|true|URL to canonical source repo
» Version|string|true|Version of this source package
» BlockchainContracts|[[EthdbBlockchaincontract](#schemaethdbblockchaincontract)]|false|Listing of contract deployed on the blockchain (default view)
»» Address|string|true|Contract address
»» Contract|string|true|Compiled contract name
»» Network|string|true|Blockchain name
» SourceFiles|[[EthdbSourcefile](#schemaethdbsourcefile)]|false|Source code package (default view)
»» CanonicalURL|string|true|Link to orignal version of this file
»» Filename|string|true|File name
»» Language|string|true|Source code programming language
»» Source|string|true|Source code
»» Version|string|true|Source code version
» Versions|[string]|false|No description



## EthdbSourceTiny

<a name="schemaethdbsourcetiny"></a>

```json
{
  "Name": "Alias distinctio sed.",
  "Type": "Quia voluptatem eum dolores officia.",
  "URL": "Voluptas amet."
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
Name|string|true|Name
Type|string|true|Type of package.  Can be 'github'
URL|string|true|URL to canonical source repo



## EthdbSourcefile

<a name="schemaethdbsourcefile"></a>

```json
{
  "CanonicalURL": "Corrupti aut esse eligendi.",
  "Filename": "Dolor facere officia molestias ab.",
  "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
  "Source": "Veniam corrupti expedita est est soluta maxime.",
  "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
CanonicalURL|string|true|Link to orignal version of this file
Filename|string|true|File name
Language|string|true|Source code programming language
Source|string|true|Source code
Version|string|true|Source code version



## EthdbSourcefileCollection

<a name="schemaethdbsourcefilecollection"></a>

```json
[
  {
    "CanonicalURL": "Corrupti aut esse eligendi.",
    "Filename": "Dolor facere officia molestias ab.",
    "Language": "Aliquam iure quaerat eveniet optio exercitationem repudiandae.",
    "Source": "Veniam corrupti expedita est est soluta maxime.",
    "Version": "Quam voluptas dolorum corporis sit nihil nostrum."
  }
] 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
anonymous|[[EthdbSourcefile](#schemaethdbsourcefile)]|false|Source code package (default view)
» CanonicalURL|string|true|Link to orignal version of this file
» Filename|string|true|File name
» Language|string|true|Source code programming language
» Source|string|true|Source code
» Version|string|true|Source code version



## EthdbTransaction

<a name="schemaethdbtransaction"></a>

```json
{
  "BlockHash": "Voluptatem laboriosam quidem.",
  "BlockNumber": 2775752852696174000,
  "Confirmations": 6532019680679138000,
  "ContractCodes": {
    "Sint deleniti est est quibusdam et quis.": {
      "ABI": "Eum quos.",
      "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
      "Verified": false
    }
  },
  "ContractCreation": true,
  "Error": "Aut vel minus molestiae aut aliquam.",
  "Events": [
    {
      "Address": "Rerum dolorum sit aut sit.",
      "Data": "Vel in consequatur odio numquam ut.",
      "Index": 2440912512905109500,
      "Topics": [
        "Voluptatem enim ducimus et."
      ],
      "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
    }
  ],
  "From": "Tempore voluptates voluptas aut.",
  "Gas": "Qui aut provident et neque.",
  "GasPrice": "Esse labore quo non consequatur quis molestiae.",
  "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
  "Hash": "Dolorum unde est omnis velit assumenda.",
  "Index": 9096248114404918000,
  "Input": "In distinctio doloremque magni totam possimus.",
  "Messages": [
    {
      "Error": "Quo culpa voluptatem.",
      "From": "Quo optio.",
      "Gas": "Eum in a libero esse voluptas aut.",
      "GasUsed": "Sit fugit molestiae.",
      "Input": "Et soluta.",
      "Nonce": "Odit sunt.",
      "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
      "To": "Dolor temporibus placeat.",
      "Value": "Nisi a consequatur nulla saepe voluptas."
    },
    {
      "Error": "Quo culpa voluptatem.",
      "From": "Quo optio.",
      "Gas": "Eum in a libero esse voluptas aut.",
      "GasUsed": "Sit fugit molestiae.",
      "Input": "Et soluta.",
      "Nonce": "Odit sunt.",
      "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
      "To": "Dolor temporibus placeat.",
      "Value": "Nisi a consequatur nulla saepe voluptas."
    }
  ],
  "Network": "Qui culpa quis laudantium molestias consequatur.",
  "Nonce": "Voluptatem magnam ea.",
  "Output": "Dicta velit debitis ea temporibus nemo.",
  "Timestamp": 4092050381628505000,
  "To": "Accusantium neque debitis numquam molestiae aut.",
  "Value": "Blanditiis est ex quos distinctio eligendi totam."
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
BlockHash|string|true|Hash of Block this Transaction is included in
BlockNumber|integer(int64)|true|Height of Block this Transaction is included in
Confirmations|integer(int64)|true|Number of confirmations for this transaction
ContractCodes|object|false|If the transactions or messages are sent to a contract, information about the contract is returned if available
ContractCreation|boolean|false|This flag is set if the transaction creates a new contract
Error|string|true|Error message from the execution of this transaction, if any
From|string|true|Transaction creator address
Gas|string|true|Total gas supplied by this Transaction
GasPrice|string|true|Price in Wei of Gas supplied by this Transaction
GasUsed|string|true|Gas Used in this Transactions
Hash|string|true|Hash
Index|integer(int64)|true|Position of Transaction in the Block
Input|string|true|Transaction function call information
Network|string|true|Network ID of transaction
Nonce|string|true|Transaction nonce
Output|string|true|Transaction output - the result of calling a contract function
Timestamp|integer(int64)|true|Timestamp of when this Transaction was included a Block. In Unix timestamp format.
To|string|true|Transaction destination address
Value|string|true|Ethereum value transfered by this transation
Events|[[EthdbEvent](#schemaethdbevent)]|false|Event Log event (default view)
» Address|string|true|Address of Account
» Data|string|true|Event data
» Index|integer(int64)|true|Index of Event generated by Transaction
» TransactionHash|string|true|Hash of Transaction which generated this Event
» Topics|[string]|false|No description
Messages|[[EthdbMessage](#schemaethdbmessage)]|false|Transaction Internal message (default view)
» Error|string|true|Error message (if any) from executing of this message
» From|string|true|Transaction creator address
» Gas|string|true|Total gas supplied by this Transaction
» GasUsed|string|true|Gas Used in this Transactions
» Input|string|true|Transaction function call information
» Nonce|string|true|Transaction nonce
» Position|string|true|Position of this message in the EVM call stack
» To|string|true|Transaction destination address
» Value|string|true|Ethereum value transfered by this transation



## EthdbTransactions

<a name="schemaethdbtransactions"></a>

```json
{
  "First": false,
  "Limit": 7551599146550128000,
  "MessagesIncluded": true,
  "Result": [
    {
      "BlockHash": "Voluptatem laboriosam quidem.",
      "BlockNumber": 2775752852696174000,
      "Confirmations": 6532019680679138000,
      "ContractCodes": {
        "Sint deleniti est est quibusdam et quis.": {
          "ABI": "Eum quos.",
          "Bytecode": "Dolor omnis blanditiis soluta eveniet laborum nulla.",
          "Verified": false
        }
      },
      "ContractCreation": true,
      "Error": "Aut vel minus molestiae aut aliquam.",
      "Events": [
        {
          "Address": "Rerum dolorum sit aut sit.",
          "Data": "Vel in consequatur odio numquam ut.",
          "Index": 2440912512905109500,
          "Topics": [
            "Voluptatem enim ducimus et."
          ],
          "TransactionHash": "Autem et dicta voluptatibus quod vero sequi."
        }
      ],
      "From": "Tempore voluptates voluptas aut.",
      "Gas": "Qui aut provident et neque.",
      "GasPrice": "Esse labore quo non consequatur quis molestiae.",
      "GasUsed": "Exercitationem totam officiis aut debitis vero eum.",
      "Hash": "Dolorum unde est omnis velit assumenda.",
      "Index": 9096248114404918000,
      "Input": "In distinctio doloremque magni totam possimus.",
      "Messages": [
        {
          "Error": "Quo culpa voluptatem.",
          "From": "Quo optio.",
          "Gas": "Eum in a libero esse voluptas aut.",
          "GasUsed": "Sit fugit molestiae.",
          "Input": "Et soluta.",
          "Nonce": "Odit sunt.",
          "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
          "To": "Dolor temporibus placeat.",
          "Value": "Nisi a consequatur nulla saepe voluptas."
        },
        {
          "Error": "Quo culpa voluptatem.",
          "From": "Quo optio.",
          "Gas": "Eum in a libero esse voluptas aut.",
          "GasUsed": "Sit fugit molestiae.",
          "Input": "Et soluta.",
          "Nonce": "Odit sunt.",
          "Position": "Sunt officia sit ut voluptatem quasi perferendis.",
          "To": "Dolor temporibus placeat.",
          "Value": "Nisi a consequatur nulla saepe voluptas."
        }
      ],
      "Network": "Qui culpa quis laudantium molestias consequatur.",
      "Nonce": "Voluptatem magnam ea.",
      "Output": "Dicta velit debitis ea temporibus nemo.",
      "Timestamp": 4092050381628505000,
      "To": "Accusantium neque debitis numquam molestiae aut.",
      "Value": "Blanditiis est ex quos distinctio eligendi totam."
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
First|boolean|false|Set to true if results returned are at the beginning
Limit|integer(int64)|true|Limit of number of results returned
MessagesIncluded|boolean|true|Set to true if results include transaction messages
Result|[[EthdbTransaction](#schemaethdbtransaction)]|false|Ethereum Transaction (default view)
» BlockHash|string|true|Hash of Block this Transaction is included in
» BlockNumber|integer(int64)|true|Height of Block this Transaction is included in
» Confirmations|integer(int64)|true|Number of confirmations for this transaction
» ContractCodes|object|false|If the transactions or messages are sent to a contract, information about the contract is returned if available
» ContractCreation|boolean|false|This flag is set if the transaction creates a new contract
» Error|string|true|Error message from the execution of this transaction, if any
» From|string|true|Transaction creator address
» Gas|string|true|Total gas supplied by this Transaction
» GasPrice|string|true|Price in Wei of Gas supplied by this Transaction
» GasUsed|string|true|Gas Used in this Transactions
» Hash|string|true|Hash
» Index|integer(int64)|true|Position of Transaction in the Block
» Input|string|true|Transaction function call information
» Network|string|true|Network ID of transaction
» Nonce|string|true|Transaction nonce
» Output|string|true|Transaction output - the result of calling a contract function
» Timestamp|integer(int64)|true|Timestamp of when this Transaction was included a Block. In Unix timestamp format.
» To|string|true|Transaction destination address
» Value|string|true|Ethereum value transfered by this transation
» Events|[[EthdbEvent](#schemaethdbevent)]|false|Event Log event (default view)
»» Address|string|true|Address of Account
»» Data|string|true|Event data
»» Index|integer(int64)|true|Index of Event generated by Transaction
»» TransactionHash|string|true|Hash of Transaction which generated this Event
»» Topics|[string]|false|No description
» Messages|[[EthdbMessage](#schemaethdbmessage)]|false|Transaction Internal message (default view)
»» Error|string|true|Error message (if any) from executing of this message
»» From|string|true|Transaction creator address
»» Gas|string|true|Total gas supplied by this Transaction
»» GasUsed|string|true|Gas Used in this Transactions
»» Input|string|true|Transaction function call information
»» Nonce|string|true|Transaction nonce
»» Position|string|true|Position of this message in the EVM call stack
»» To|string|true|Transaction destination address
»» Value|string|true|Ethereum value transfered by this transation



## EthdbUncle

<a name="schemaethdbuncle"></a>

```json
{
  "BeneficiaryReward": "Mollitia omnis necessitatibus et.",
  "BlockNumber": 6948539910358115000,
  "CreationTime": 2533265886652186000,
  "Difficulty": "Eaque saepe.",
  "ExtraData": "Voluptate expedita saepe voluptates.",
  "GasLimit": "Eius est ea odit repellat est.",
  "Hash": "Asperiores et facere nostrum omnis consequuntur.",
  "Index": 4134083501788099000,
  "LogsBloom": "Ut nihil ipsam alias debitis qui.",
  "Miner": "Ea quasi assumenda.",
  "MixHash": "Ducimus maiores beatae.",
  "Nonce": "Molestiae suscipit quam dolore sit eum.",
  "Number": 7066559540085266000,
  "ParentHash": "Consectetur excepturi molestias quibusdam autem incidunt fugiat.",
  "ReceiptsRoot": "Itaque accusantium sunt.",
  "SHA3Uncles": "Architecto modi.",
  "Size": "Laudantium totam consectetur nihil repudiandae.",
  "StateRoot": "Provident facere consequatur explicabo est voluptatem.",
  "TotalDifficulty": "Voluptatibus dolorem."
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
BeneficiaryReward|string|true|Reward for mining a block.  Includes the base reward, reward for including Uncle blocks and the fees of Transactions included in the Block
BlockNumber|integer(int64)|true|Mined in Ethereum Block
CreationTime|integer(int64)|true|Timestamp of Block creation in Unix timestamp format
Difficulty|string|true|Difficulty level of this block
ExtraData|string|true|Data included in the Block by the Miner
GasLimit|string|true|Gas limit for this Block
Hash|string|true|Keccak-256 hash of the Block header
Index|integer(int64)|true|Position of the Uncle in mined Ethereum block
LogsBloom|string|true|Bloom filter of indexable information included in the Block receipt Events
Miner|string|true|Address that created this Uncle
MixHash|string|true|Hash which proves Proof of Work for this Block has been completed
Nonce|string|true|Hash to be used in Proof of Work calculation
Number|integer(int64)|true|Uncle number
ParentHash|string|true|Hash of Parent Block
ReceiptsRoot|string|true|Hash of reeipts state
SHA3Uncles|string|true|Hash of uncles
Size|string|true|Size of the Block header in bytes
StateRoot|string|true|Hash of the state of this block
TotalDifficulty|string|true|Total difficulty of the chain



## EthdbUncles

<a name="schemaethdbuncles"></a>

```json
{
  "First": true,
  "Limit": 6916214044123517000,
  "Result": [
    {
      "BeneficiaryReward": "Mollitia omnis necessitatibus et.",
      "BlockNumber": 6948539910358115000,
      "CreationTime": 2533265886652186000,
      "Difficulty": "Eaque saepe.",
      "ExtraData": "Voluptate expedita saepe voluptates.",
      "GasLimit": "Eius est ea odit repellat est.",
      "Hash": "Asperiores et facere nostrum omnis consequuntur.",
      "Index": 4134083501788099000,
      "LogsBloom": "Ut nihil ipsam alias debitis qui.",
      "Miner": "Ea quasi assumenda.",
      "MixHash": "Ducimus maiores beatae.",
      "Nonce": "Molestiae suscipit quam dolore sit eum.",
      "Number": 7066559540085266000,
      "ParentHash": "Consectetur excepturi molestias quibusdam autem incidunt fugiat.",
      "ReceiptsRoot": "Itaque accusantium sunt.",
      "SHA3Uncles": "Architecto modi.",
      "Size": "Laudantium totam consectetur nihil repudiandae.",
      "StateRoot": "Provident facere consequatur explicabo est voluptatem.",
      "TotalDifficulty": "Voluptatibus dolorem."
    }
  ],
  "TotalRecords": 2078329725000681500
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
First|boolean|false|Set to true if results returned are at the begining
Limit|integer(int64)|true|Limit of results returned
TotalRecords|integer(int64)|true|Total number of blocks
Result|[[EthdbUncle](#schemaethdbuncle)]|false|Ethereum Uncle (default view)
» BeneficiaryReward|string|true|Reward for mining a block.  Includes the base reward, reward for including Uncle blocks and the fees of Transactions included in the Block
» BlockNumber|integer(int64)|true|Mined in Ethereum Block
» CreationTime|integer(int64)|true|Timestamp of Block creation in Unix timestamp format
» Difficulty|string|true|Difficulty level of this block
» ExtraData|string|true|Data included in the Block by the Miner
» GasLimit|string|true|Gas limit for this Block
» Hash|string|true|Keccak-256 hash of the Block header
» Index|integer(int64)|true|Position of the Uncle in mined Ethereum block
» LogsBloom|string|true|Bloom filter of indexable information included in the Block receipt Events
» Miner|string|true|Address that created this Uncle
» MixHash|string|true|Hash which proves Proof of Work for this Block has been completed
» Nonce|string|true|Hash to be used in Proof of Work calculation
» Number|integer(int64)|true|Uncle number
» ParentHash|string|true|Hash of Parent Block
» ReceiptsRoot|string|true|Hash of reeipts state
» SHA3Uncles|string|true|Hash of uncles
» Size|string|true|Size of the Block header in bytes
» StateRoot|string|true|Hash of the state of this block
» TotalDifficulty|string|true|Total difficulty of the chain



## error

<a name="schemaerror"></a>

```json
{
  "code": "invalid_value",
  "detail": "Value of ID must be an integer",
  "id": "3F1FKVRR",
  "meta": {
    "timestamp": 1458609066
  },
  "status": "400"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|---|
code|string|false|an application-specific error code, expressed as a string value.
detail|string|false|a human-readable explanation specific to this occurrence of the problem.
id|string|false|a unique identifier for this particular occurrence of the problem.
meta|object|false|a meta object containing non-standard meta-information about the error.
status|string|false|the HTTP status code applicable to this problem, expressed as a string value.





