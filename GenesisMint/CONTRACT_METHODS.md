## Contract Methods

### Admin Functions

> _These methods below can only be called by the **OWNER** account._

---

#### setBaseTokenURI  

* _Will set the `_baseTokenURI` for this contract. The `_baseTokenURI` is used as the base url for the unique PFPs used for this GenesisMint._  
* _The `_baseTokenURI` has to be set before `setPublicMintValues` and the Public mint phase starts, for any unique PFP image can be revealed._  

```javascript
function setBaseTokenURI(string memory __baseTokenURI) public onlyOwner {
  _baseTokenURI = __baseTokenURI;
}  
```  

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__baseTokenURI` | `string`  | _The base Url for the NFTs of this Genesis Mint contract._ |  

---

#### setGoldenTicketURI  

* _Will set the `_goldenTicketURI` for this contract. The `_goldenTicketURI` is used as the pre-reveal asset for the NFTs in this GenesisMint._  
* _The `_goldenTicketURI` has to be set before `setPhase1MintValues`, and the pre-mint phase 1 starts._  

```javascript
function setGoldenTicketURI(string memory __goldenTicketURI) public onlyOwner {
  _goldenTicketURI = __goldenTicketURI;
}
``` 

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__goldenTicketURI` | `string`  | _The URI for the GoldenTicket.mp4 asset used for this Genesis Mint._|

---

#### setContractURI  

* _Will set the `_contractURI` for this contract. The `_contractURI` is used by the function `contractURI()`, as required by OpenSeato honor royalty payout._  
* _Supports OpenSea's - Royalty Standard. { https://docs.opensea.io/docs/contract-level-metadata }_  

```javascript
function setContractURI(string memory __contractURI) public onlyOwner {
    _contractURI = __contractURI;
}
``` 

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__contractURI` | `string`  | _The url of the .JSON file used for this Genesis Mint._|


## Workflows

### ADMIN FLOW

_This flow will describe the Admin flow for completing all phases of this Genesis Mint and the methods available to this contracts Owner account._

## Usage/Examples

```javascript
import Component from 'my-project'

function App() {
  return <Component />
}
```

