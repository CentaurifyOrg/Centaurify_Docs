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
        - [`whitelistPhase3Mint`](#whitelistphase3mint)
        - [`publicMint`](#publicmint)

<-- Back to [readthedocs](ReadTheDocs_Genesis_Mint.md#table-of-contents "Back to ReadTheDocs")

### User Methods

> _The methods below can are not restricted to Owner and can be called by **ANY** account._

---

#### Mint Methods

##### `whitelistPhase1Mint`  

- _Only whitelisted accounts of pre-mint phase1 is allowed to mint their allocated amount._
- _Max 5 NFT's per account._
- _Restricted by modifiers `phaseOneIsOpen`, `costs(amount)`._
- _Use [frontend.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/frontend.js "Script to generate the leaf and proof") to generate and validate the `bytes32 leaf` and `bytes32[] proof` for the user account._

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

- _Only whitelisted accounts of pre-mint phase2 accounts is allowed to mint their allocated amount._
- _Max 4 NFT's per account._
- _Restricted by modifiers `phaseTwoIsOpen`, `costs(amount)`._
- _Use [frontend.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/frontend.js "Script to generate the leaf and proof") to generate and validate the `bytes32 leaf` and `bytes32[] proof` for the user account._

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

##### `whitelistPhase3Mint`  

- _Only whitelisted accounts of pre-mint phase3 is allowed to mint their allocated amount._
- _Max 3 NFT's allocated per account._
- _Restricted by modifiers `phaseThreeIsOpen`, `costs(amount)`._
- _Use [frontend.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/frontend.js "Script to generate the leaf and proof") to generate and validate the `bytes32 leaf` and `bytes32[] proof` for the user account._

```javascript
function whitelistPhase3Mint(
    uint amount,
    bytes32 leaf,
    bytes32[] memory proof
) external payable phaseThreeIsOpen costs(amount) {}
```  

| Parameter  | Type        | Description                      |
| :--------  | :-------    | :-------------------------       |
| `amount`   | `uint`      | _The amount of nft's to mint._   |  
| `leaf`     | `bytes32`   | _The leaf node of the three._    |  
| `proof`    | `bytes32[]` | _The proof from the merkletree._ |  

---

##### `publicMint`  

- _PublicMint has no restrictions on who can mint._
- _Max 3 NFT's allocated per account._
- _Restricted by modifiers `publicMintIsOpen`, `costs(amount)`._
- _Use [frontend.js](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/scripts/frontend.js "Script to generate the leaf and proof") to generate and validate the `bytes32 leaf` and `bytes32[] proof` for the user account._

```javascript
function PublicMint(uint amount) external payable publicMintIsOpen costs(amount) {}
```  

| Parameter  | Type        | Description                      |
| :--------  | :-------    | :-------------------------       |
| `amount`   | `uint`      | _The amount of nft's to mint._   | 

---
