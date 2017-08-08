--- 

title: ETHdb API 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

Ethereum Blockchain explorer 

**Version:**  

[API Documentation](http://ethdb.io/docs/api) 

# /ACCOUNT/{ADDRESS}
## ***GET*** 

**Summary:** show Account

**Description:** Returns Account information

### HTTP Request 
`***GET*** /account/{Address}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Address | path | Account address | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /ACCOUNT/{ADDRESS}/CODE
## ***GET*** 

**Summary:** code Account

**Description:** Returns code for contract.  Returns not found if Account is not a contract

### HTTP Request 
`***GET*** /account/{Address}/code` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Address | path | Account address | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /ACCOUNT/{ADDRESS}/MINED_BLOCKS
## ***GET*** 

**Summary:** mined_blocks Account

**Description:** Returns list of blocks mined by this Account

### HTTP Request 
`***GET*** /account/{Address}/mined_blocks` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Address | path | Account address | Yes | string |
| block | query | Return mined blocks begining from Block number | No | integer |
| previous | query | When set to true, returns transactions Previous to the specified block number and transaction index | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /ACCOUNT/{ADDRESS}/MINED_UNCLES
## ***GET*** 

**Summary:** mined_uncles Account

**Description:** Returns list of blocks mined by this Account

### HTTP Request 
`***GET*** /account/{Address}/mined_uncles` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Address | path | Account address | Yes | string |
| block | query | Return mined uncles begining from Block number | No | integer |
| previous | query | When set to true, returns transactions Previous to the specified block number and transaction index | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /ACCOUNT/{ADDRESS}/TRANSACTIONS
## ***GET*** 

**Summary:** transactions Account

**Description:** Returns list of transactions with the From or To fields matching Address

### HTTP Request 
`***GET*** /account/{Address}/transactions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Address | path | Account address | Yes | string |
| block | query | Return transactions begining from Block number. Defaults to latest block if not specified | No | integer |
| internals | query | Include transaction messages (internal transactions) in results | No | boolean |
| previous | query | When set to true, returns transactions Previous to the specified block number and transaction index | No | boolean |
| txindex | query | Return transactions after transaction index in Block | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /BLOCK/{HASHORHEIGHT}
## ***GET*** 

**Summary:** show Block

**Description:** Retuns Block information

### HTTP Request 
`***GET*** /block/{HashOrHeight}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| HashOrHeight | path | Block hash or height | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /NETWORKS
## ***GET*** 

**Summary:** list Networks

**Description:** Retuns a list of supported Ethereum networks

### HTTP Request 
`***GET*** /networks` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /NETWORKS/{ID}
## ***GET*** 

**Summary:** show Networks

**Description:** Network details

### HTTP Request 
`***GET*** /networks/{ID}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| ID | path |  | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /NETWORKS/{ID}/BLOCKS
## ***GET*** 

**Summary:** blocks Networks

**Description:** Return list of recently mined blocks on this network

### HTTP Request 
`***GET*** /networks/{ID}/blocks` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| ID | path |  | Yes | string |
| block | query | Optional block number to returns blocks begining at | No | integer |
| previous | query | When set to true, returns transactions Previous to the specified block number and transaction index | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /SEARCH
## ***GET*** 

**Summary:** search Search

**Description:** Search the Blockchain

### HTTP Request 
`***GET*** /search` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| network | query | Search query | No | string |
| query | query | Search query | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |

# /SOURCE
## ***GET*** 

**Summary:** list Source

**Description:** Returns list of public source repositories

### HTTP Request 
`***GET*** /source` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /SOURCE/{TYPE}/{NAME}
## ***GET*** 

**Summary:** show Source

**Description:** Returns information on source package

### HTTP Request 
`***GET*** /source/{Type}/{Name}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Name | path |  | Yes | string |
| Type | path |  | Yes | string |
| network | query |  | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /TX/{HASH}
## ***GET*** 

**Summary:** show Transaction

**Description:** Ethereum Transactions

### HTTP Request 
`***GET*** /tx/{Hash}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Hash | path | Transaction hash | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

# /UNCLE/{HASH}
## ***GET*** 

**Summary:** show Uncle

**Description:** Uncle Block

### HTTP Request 
`***GET*** /uncle/{Hash}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Hash | path | Transaction hash | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |
| 500 | Internal Server Error |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
