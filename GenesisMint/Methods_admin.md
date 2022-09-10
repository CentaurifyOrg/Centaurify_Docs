![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product      | Type               | Description                |
| :--------    | :-------           | :------------------------- |
| Genesis Mint | NFT Smart Contract | Collection AAA        |

---

# Contract Methods

## Table of contents

- [Contract Methods](#contract-methods)
  - [Table of contents](#table-of-contents)
    - [Admin Methods](#admin-methods)
      - [Set URI Methods](#set-uri-methods)
        - [`setBaseTokenURI`](#setbasetokenuri)
        - [`setContractURI`](#setcontracturi)
      - [Set Phase Methods](#set-phase-methods)
        - [`setPhaseOneMintValues`](#setphaseonemintvalues)
        - [`setPhaseTwoMintValues`](#setphasetwomintvalues)
        - [`setPhaseThreeMintValues`](#setphasethreemintvalues)
        - [`setPublicMintValues`](#setpublicmintvalues)
        - [`setEarlyRevealValues`](#setearlyrevealvalues)
        - [`setRevealValues`](#setrevealvalues)
      - [Other Methods](#other-methods)
        - [`setRecipient`](#setrecipient)
        - [`setMaxItemsPerTx`](#setmaxitemspertx)

<-- Back to [readthedocs](ReadTheDocs_Genesis_Mint.md#table-of-contents "Back to ReadTheDocs")

---  

### Admin Methods

> _The methods below can only be called by the **ADMIN_ROLE** account._



#### **Set URI Methods**

##### `setBaseTokenURI`  

- _Will set the `_baseTokenURI` for this contract._
- _The `_baseTokenURI` is used as the base url for the unique PFPs used for this GenesisMint._  
- _The `_baseTokenURI` is a required parameter for the constructor._  


```javascript
function setBaseTokenURI(string memory __baseTokenURI) public onlyOwner {
  _baseTokenURI = __baseTokenURI;
}  
```  

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__baseTokenURI` | `string`  | _The base Url for the NFTs of this Genesis Mint contract._ |  


##### `setContractURI`  

- _Will set the `_contractURI` for this contract._
- _The `_contractURI` is used by the function `contractURI()`, as required by OpenSea to honor royalty payout._  
- _Supports OpenSea's - Royalty Standard. { <https://docs.opensea.io/docs/contract-level-metadata> }_
- _Example of `_contractURI`: ["https://gateway.moralisipfs.com/ipfs/QmQk8b3mAEwEfeu6gyZ6CRcWcjkafnQt7x59U9KPP2ewwK"]("https://gateway.moralisipfs.com/ipfs/QmQk8b3mAEwEfeu6gyZ6CRcWcjkafnQt7x59U9KPP2ewwK")_
- _The `_contractURI` is a required parameter for the constructor._  

```javascript
function setContractURI(string memory __contractURI) public onlyOwner {
    _contractURI = __contractURI;
}
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__contractURI` | `string`  | _The url of the ContractURI used for this Genesis Mint._|

---

#### **Set Phase Methods**

_There are six different stages/phases in this Genesis Mint, the phases are listed below._

| Pre-Mint Phase One | Pre-Mint Phase Two | Pre-Mint Phase Three | Public Mint | Early Reveal | Reveal |
|:------------------ | :----------------- | :------------------- | :---------- | :----------- | :----- |
| 16 hours| 16 hours | 16 hours | 2 weeks | Not Set| Not Set | | | | 


##### `setPhaseOneMintValues`  

- _Will initiate the pre-mint phase 1._
- _Make sure the `_baseTokenURI` is set before `setPhaseOneMintValues`, and the pre-mint phase 1 starts._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._


```javascript
function setPhaseOneMintValues(uint _phase1StartTimestamp, bytes32 _merkleRoot) external onlyOwner {}
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `_phase1StartTimestamp` | `uint`  | _The timestamp to start the premint Phase 1._|
| `_merkleRoot` | `bytes32`  | _The merkleroot of the Phase1 whitelist to mint from._|



##### `setPhaseTwoMintValues`  

- _Will initiate the pre-mint phase 2._  
- _Restricted by modifier `phaseOneIsOpen`._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._


```javascript
function setPhaseTwoMintValues(uint _phase2StartTimestamp, bytes32 _merkleRoot) external onlyOwner phaseOneIsOpen {}
```

| Parameter               | Type      | Description                |
| :--------               | :-------  | :------------------------- |
| `_phase2StartTimestamp` | `uint`    | _The timestamp to start the premint Phase 2._|
| `_merkleRoot`           | `bytes32` | _The merkleroot of the Phase2 whitelist to mint from._|



##### `setPhaseThreeMintValues`  

- _Will initiate the pre-mint phase 3._
- _Restricted by modifier `phaseTwoIsOpen`._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._



```javascript
function setPhaseThreeMintValues(uint _phase3StartTimestamp, bytes32 _merkleRoot) external onlyOwner phaseTwoIsOpen {}
```

| Parameter               | Type      | Description                |
| :--------               | :-------  | :------------------------- |
| `_phase3StartTimestamp` | `uint`    | _The timestamp to start the premint Phase 3._|
| `_merkleRoot`           | `bytes32` | _The merkleroot of the Phase3 whitelist to mint from._|



##### `setPublicMintValues`

- _Will initiate the public mint phase._  
- _Restricted by modifier `phaseThreeIsOpen`._
- _Make sure the `_baseTokenURI` is set before `setPublicMintValues`, and the public mint phase starts._


```javascript
function setPublicMintValues(uint _publicStartTimestamp) external onlyOwner phaseThreeIsOpen {}
```

| Parameter               | Type      | Description                                    |
| :--------               | :-------  | :-------------------------                     |
| `_publicStartTimestamp` | `uint`    | _The timestamp to start the public mint phase._|


##### `setEarlyRevealValues`  

- _Will initiate the EarlyReveal phase._ 
- _Restricted by modifier `publicMintIsOpen`._
- _Will allow GoldenTicket holders to initiate an early reveal of their PFP._

```javascript
function setEarlyRevealValues(uint _earlyRevealTimestamp) external onlyOwner publicMintIsOpen {}
```

| Parameter               | Type      | Description                                     |
| :--------               | :-------  | :-------------------------                      |
| `_earlyRevealTimestamp` | `uint`    | _The timestamp to start the early reveal phase._|


##### `setRevealValues`  

- _Will initiate the Revealed phase._ 
- _Restricted by modifier `earlyRevealIsOpen`._
- _Will allow GoldenTicket holders to initiate early reveal of their PFP._

```javascript
 function setRevealValues() public onlyOwner earlyRevealIsOpen {
      status = Status.Revealed;
 }
 ```

---

#### **Other Methods**  

##### `setRecipient`  

- _Update the recipient address._
- _Restricted to `owner` account._
- _Will update the `recipient` account to receive the withdrawn funds._

```javascript
  function setRecipient(address payable _recipient) external onlyOwner {
      recipient = _recipient;
  }
 ```  

##### `setMaxItemsPerTx`  

- _Update the maxItemsPerTx._  
- _Restricted to `owner` account._
- _Will update the `maxItemsPerTx` value._

```javascript
   function setMaxItemsPerTx(uint _maxItemsPerTx) external onlyOwner {
        maxItemsPerTx = _maxItemsPerTx;
    }
 ```

---
