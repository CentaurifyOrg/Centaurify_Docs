![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product      | Type               | Description                |
| :--------    | :-------           | :------------------------- |
| Genesis Mint | NFT Smart Contract | GoldenTicket  - PFP        |

---

# Contract Methods

## Table of contents

- [Contract Methods](#contract-methods)
  - [Table of contents](#table-of-contents)
    - [User Methods](#user-methods)
      - [Mint Methods](#mint-methods)
        - [`whitelistPhase1Mint`](#whitelistphase1mint)
        - [`whitelistPhase2Mint`](#whitelistphase2mint)

<-- Back to [readthedocs](ReadTheDocs_Genesis_Mint.md#table-of-contents "Back to ReadTheDocs")

### User Methods

> _The methods below can are not restricted to Owner and can be called by **ANY** account._

---

#### Mint Methods

##### `whitelistPhase1Mint`  

- _If user account is whitelisted, it will allow to mint the accounts total allocation._

```javascript
function whitelistPhase1Mint(
    uint amount,
    bytes32 leaf,
    bytes32[] memory proof
) external payable phaseOneIsOpen costs(amount) {}
```  

| Parameter  | Type        | Description                      |
| :--------  | :-------    | :-------------------------       |
| `amount`   | `uint`      | _The amount of nft's to mint._   |  
| `leaf`     | `bytes32`   | _The leaf node of the three._    |  
| `proof`    | `bytes32[]` | _The proof from the merkletree._ |  

---

##### `whitelistPhase2Mint`  

- _If user account is whitelisted, it will allow to mint the accounts total allocation._

```javascript
function whitelistPhase2Mint(
    uint amount,
    bytes32 leaf,
    bytes32[] memory proof
) external payable phaseTwoIsOpen costs(amount) {}
```  

| Parameter  | Type        | Description                      |
| :--------  | :-------    | :-------------------------       |
| `amount`   | `uint`      | _The amount of nft's to mint._   |  
| `leaf`     | `bytes32`   | _The leaf node of the three._    |  
| `proof`    | `bytes32[]` | _The proof from the merkletree._ |  

---
<!-- 
##### `setGoldenTicketURI`

- _Will set the `_goldenTicketURI` for this contract._
- _The `_goldenTicketURI` is used as the pre-reveal asset for the NFTs in this GenesisMint._  
- _The `_goldenTicketURI` has to be set before `setPhaseOneMintValues`, and the pre-mint phase 1 starts._
- _Example of `_goldenTicketURI`: ["https://gateway.moralisipfs.com/ipfs/QmYVdmyWpFwfKfjXbYNheykFQPMY3roH2TWYLAnLaSCRnG"](QmYVdmyWpFwfKfjXbYNheykFQPMY3roH2TWYLAnLaSCRnG)_

```javascript
function setGoldenTicketURI(string memory __goldenTicketURI) public onlyOwner {
  _goldenTicketURI = __goldenTicketURI;
}
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__goldenTicketURI` | `string`  | _The URI for the GoldenTicket.mp4 asset used for this Genesis Mint._|

---

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

#### Set Phase Methods

##### `setPhaseOneMintValues`  

- _Will initiate the pre-mint phase 1._
- _Make sure the `_baseTokenURI` is set before `setPhaseOneMintValues`, and the pre-mint phase 1 starts._
- _Make sure the `_goldenTicketURI` is set before `setPhaseOneMintValues`, and the pre-mint phase 1 starts._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._


```javascript
function setPhaseOneMintValues(uint _phase1StartTimestamp, bytes32 _merkleRoot) external onlyOwner {}
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `_phase1StartTimestamp` | `uint`  | _The timestamp to start the premint Phase 1._|
| `_merkleRoot` | `bytes32`  | _The merkleroot of the Phase1 whitelist to mint from._|

---

##### `setPhaseTwoMintValues`  

- _Will initiate the pre-mint phase 2._  
- _Restricted by modifier `phaseOneIsOpen`._
- _Make sure the `_goldenTicketURI` is set before `setPhaseTwoMintValues`, and the pre-mint phase 2 starts._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._



```javascript
function setPhaseTwoMintValues(uint _phase2StartTimestamp, bytes32 _merkleRoot) external onlyOwner phaseOneIsOpen {}
```

| Parameter               | Type      | Description                |
| :--------               | :-------  | :------------------------- |
| `_phase2StartTimestamp` | `uint`    | _The timestamp to start the premint Phase 2._|
| `_merkleRoot`           | `bytes32` | _The merkleroot of the Phase2 whitelist to mint from._|

---

##### `setPhaseThreeMintValues`  

- _Will initiate the pre-mint phase 3._
- _Restricted by modifier `phaseTwoIsOpen`._
- _Make sure the `_goldenTicketURI` is set before `setPhaseThreeMintValues`, and the pre-mint phase 3 starts._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._



```javascript
function setPhaseThreeMintValues(uint _phase3StartTimestamp, bytes32 _merkleRoot) external onlyOwner phaseTwoIsOpen {}
```

| Parameter               | Type      | Description                |
| :--------               | :-------  | :------------------------- |
| `_phase3StartTimestamp` | `uint`    | _The timestamp to start the premint Phase 3._|
| `_merkleRoot`           | `bytes32` | _The merkleroot of the Phase3 whitelist to mint from._|

---

##### `setPublicMintValues`

- _Will initiate the public mint phase._  
- _Restricted by modifier `phaseThreeIsOpen`._
- _Make sure the `_baseTokenURI` is set before `setPublicMintValues`, and the public mint phase starts._
- _Make sure the `_goldenTicketURI` is set before `setPublicMintValues`, and the public mint phase starts._


```javascript
function setPublicMintValues(uint _publicStartTimestamp) external onlyOwner phaseThreeIsOpen {}
```

| Parameter               | Type      | Description                                    |
| :--------               | :-------  | :-------------------------                     |
| `_publicStartTimestamp` | `uint`    | _The timestamp to start the public mint phase._|

---

##### `setEarlyRevealValues`  

- _Will initiate the EarlyReveal phase._ 
- _Restricted by modifier `publicMintIsOpen`._
- _Will allow GoldenTicket holders to initiate early reveal of their PFP._

```javascript
function setEarlyRevealValues(uint _earlyRevealTimestamp) external onlyOwner publicMintIsOpen {}
```

| Parameter               | Type      | Description                                     |
| :--------               | :-------  | :-------------------------                      |
| `_earlyRevealTimestamp` | `uint`    | _The timestamp to start the early reveal phase._|

---

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
 -->