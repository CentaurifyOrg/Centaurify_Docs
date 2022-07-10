![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product       | Type | Description                |
| :--------        | :-------       | :------------------------- |
| Genesis Mint | NFT Smart Contract | GoldenTicket  - PFP |

---

# Contract Methods

## Table of contents

- [Genesis Mint - Contract Methods](#genesis-mint---contract-methods)
  - [Table of contents](#table-of-contents)
    - [Admin Methods](#admin-methods)
      - [Set URI Methods](#set-uri-methods)
        - [`setBaseTokenURI`](#setbasetokenuri)
        - [`setGoldenTicketURI`](#setgoldenticketuri)
        - [`setContractURI`](#setcontracturi)
      - [Set Phase Methods](#set-phase-methods)
        - [`setPhaseOneMintValues`](#setphaseonemintvalues)
        - [`setPhaseTwoMintValues`](#setphasetwomintvalues)
        - [`setPhaseThreeMintValues`](#setphasethreemintvalues)
        - [`setPublicMintValues`](#setpublicmintvalues)

<-- Back to [readthedocs](ReadTheDocs_Genesis_Mint.md#table-of-contents "Back to ReadTheDocs")

### Admin Methods

> _The methods below can only be called by the **OWNER** account._

---

#### Set URI Methods

##### `setBaseTokenURI`  

- _Will set the `_baseTokenURI` for this contract._
- _The `_baseTokenURI` is used as the base url for the unique PFPs used for this GenesisMint._  
- _The `_baseTokenURI` has to be set before `setPhaseOneMintValues` or any mint phase starts, for any unique PFP image to be revealed._  


```javascript
function setBaseTokenURI(string memory __baseTokenURI) public onlyOwner {
  _baseTokenURI = __baseTokenURI;
}  
```  

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__baseTokenURI` | `string`  | _The base Url for the NFTs of this Genesis Mint contract._ |  

---

##### `setGoldenTicketURI`

- _Will set the `_goldenTicketURI` for this contract._
- _The `_goldenTicketURI` is used as the pre-reveal asset for the NFTs in this GenesisMint._  
- _The `_goldenTicketURI` has to be set before `setPhaseOneMintValues`, and the pre-mint phase 1 starts._
- _Example of `_goldenTicketURI`: ["https://xm9lk7erz9ku.usemoralis.com/goldenticket_teaser.mp4"](https://xm9lk7erz9ku.usemoralis.com/goldenticket_teaser.mp4)_

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
- _The `_contractURI` is used by the function `contractURI()`, as required by OpenSeato honor royalty payout._  
- _Supports OpenSea's - Royalty Standard. { <https://docs.opensea.io/docs/contract-level-metadata> }_
- _Example of `_contractURI`: ["https://xm9lk7erz9ku.usemoralis.com/contract.json"](https://xm9lk7erz9ku.usemoralis.com/contract.json)_


```javascript
function setContractURI(string memory __contractURI) public onlyOwner {
    _contractURI = __contractURI;
}
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__contractURI` | `string`  | _The url of the .JSON file used for this Genesis Mint._|

---

#### Set Phase Methods

##### `setPhaseOneMintValues`  

- _Will initiate the pre-mint phase 1._
- _Make sure the `_baseTokenURI` is set before `setPhaseOneMintValues`, and the pre-mint phase 1 starts._
- _Make sure the `_goldenTicketURI` is set before `setPhaseOneMintValues`, and the pre-mint phase 1 starts._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._


```javascript
function setPhaseOneMintValues(uint _phase1StartTimestamp, bytes32 _merkleRoot) external onlyOwner
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `_phase1StartTimestamp` | `uint`  | _The timestamp to start the premint Phase 1._|
| `_merkleRoot` | `bytes32`  | _The merkleroot of the Phase1 whitelist to mint from._|

---

##### `setPhaseTwoMintValues`  

- _Will initiate the pre-mint phase 2._  
- _Make sure the `_baseTokenURI` is set before `setPhaseTwoMintValues`, and the pre-mint phase 2 starts._
- _Make sure the `_goldenTicketURI` is set before `setPhaseTwoMintValues`, and the pre-mint phase 2 starts._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._



```javascript
function setPhaseTwoMintValues(uint _phase2StartTimestamp, bytes32 _merkleRoot) external onlyOwner phaseOneIsOpen
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `_phase2StartTimestamp` | `uint`  | _The timestamp to start the premint Phase 2._|
| `_merkleRoot` | `bytes32`  | _The merkleroot of the Phase2 whitelist to mint from._|

---

##### `setPhaseThreeMintValues`  

- _Will initiate the pre-mint phase 3._
- _Make sure the `_baseTokenURI` is set before `setPhaseThreeMintValues`, and the pre-mint phase 3 starts._
- _Make sure the `_goldenTicketURI` is set before `setPhaseThreeMintValues`, and the pre-mint phase 3 starts._
- _Use [generate_merkle_root.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/generate_merkle_root.js "Script to generate the merkle root") to generate the `bytes32 merkleRoot` for each phase._



```javascript
function setPhaseThreeMintValues(uint _phase3StartTimestamp, bytes32 _merkleRoot) external onlyOwner phaseTwoIsOpen
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `_phase3StartTimestamp` | `uint`  | _The timestamp to start the premint Phase 3._|
| `_merkleRoot` | `bytes32`  | _The merkleroot of the Phase3 whitelist to mint from._|

---

##### `setPublicMintValues`  

- _Will initiate the public mint phase._
- _Make sure the `_baseTokenURI` is set before `setPublicMintValues`, and the public mint phase starts._
- _Make sure the `_goldenTicketURI` is set before `setPublicMintValues`, and the public mint phase starts._


```javascript
function setPublicMintValues(uint _publicStartTimestamp, uint _earlyRevealTimestamp) external onlyOwner phaseThreeIsOpen
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `_publicStartTimestamp` | `uint`  | _The timestamp to start the public mint phase._|
| `_earlyRevealTimestamp` | `uint`  | _The timestamp when earlyReveal is allowed._|

---
