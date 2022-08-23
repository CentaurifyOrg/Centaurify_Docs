![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product      | Type               | Description                |
| :--------    | :-------           | :------------------------- |
| Genesis Mint | NFT Smart Contract | GoldenTicket  - PFP        |

---

# Contract Modifiers

## Table of contents

- [Contract Modifiers](#contract-modifiers)
  - [Table of contents](#table-of-contents)
    - [Modifiers](#modifiers)
      - [Phase modifiers](#phase-modifiers)
        - [`phaseOneIsOpen`](#phaseoneisopen)
        - [`phaseTwoIsOpen`](#phasetwoisopen)
        - [`phaseThreeIsOpen`](#phasethreeisopen)
        - [`publicMintIsOpen`](#publicmintisopen)
        - [`earlyRevealIsOpen`](#earlyrevealisopen)
      - [Other modifiers](#other-modifiers)
        - [`costs`](#costs)

<-- Back to [Read-The-Docs](ReadTheDocs_Genesis_Mint.md#table-of-contents "Back to Read-The-Docs")

### Modifiers

_The modifiers in this smart contract are described below._

---

#### Phase modifiers

> _The different modifiers is set to validate specific phase variables to pass._
>
> - Validates the correct status of the contract.
> - Validates that the phase specific `startTimestamp` is set.
> - Validates if the current `block.timestamp` is within the phase specific `startTimestamp`.  

##### `phaseOneIsOpen`  

- _Modifier `phaseOneIsOpen` validates if the pre-mint phase1 has started._
- _Used by the method [`whitelistPhase1Mint`](Methods_user.md#whitelistphase1mint "Link to whitelistPhase1Mint")._
- _Used by the admin method [`setPhaseTwoMintValues`](Methods.md#setphasetwomintvalues "Link to setPhaseTwoMintValues")._


```javascript
modifier phaseOneIsOpen() {
  uint currentTime = block.timestamp;
  if (status != Status.Phase1) revert Code_1(status, Status.Phase1);
  if (currentTime <= startTimestamp) revert Code_2(startTimestamp);

  if (phase1StartTimestamp == 0) revert Code_2(phase1StartTimestamp);
  _;
}
```  

---

##### `phaseTwoIsOpen`  

- _Modifier `phaseTwoIsOpen` validates if the pre-mint phase2 has started._
- _Used by the method [`whitelistPhase2Mint`](Methods_user.md#whitelistphase2mint "Link to whitelistPhase2Mint")._
- _Used by the admin method [`setPhaseThreeMintValues`](./Methods.md#setphasethreemintvalues "Link to setPhaseThreeMintValues")._


```javascript
modifier phaseTwoIsOpen() {
  uint currentTime = block.timestamp;
  if (status != Status.Phase2) revert Code_1(status, Status.Phase2);
  if (currentTime <= startTimestamp) revert Code_2(startTimestamp);

  if (startTimestamp == 0) revert Code_2(startTimestamp);
  _;
}
```  

##### `phaseThreeIsOpen`  

- _Modifier `phaseThreeIsOpen` validates if the pre-mint phase3 has started._
- _Used by the method [`whitelistPhase3Mint`](Methods_user.md#whitelistphase3mint "Link to whitelistPhase3Mint")._
- _Used by the admin method [`setPublicMintValues`](./Methods.md#setpublicmintvalues "Link to setPublicMintValues")._


```javascript
modifier phaseThreeIsOpen() {
  uint currentTime = block.timestamp;
  if (status != Status.Phase3) revert Code_1(status, Status.Phase3);
  if (currentTime <= startTimestamp) revert Code_2(startTimestamp);

  if (startTimestamp == 0) revert Code_2(startTimestamp);
  _;
}
```  

---

##### `publicMintIsOpen`  

- _Modifier `publicMintIsOpen` validates if the public mint phase has started._
- _Used by the method [`publicMint`](Methods_user.md#publicmint "Link to publicMint")._
- _Used by the admin method [`setEarlyRevealValues`](./Methods.md#setearlyrevealvalues "Link to setEarlyRevealValues")._


```javascript
modifier publicMintIsOpen() {
  uint currentTime = block.timestamp;
  if (status != Status.Public) revert Code_1(status, Status.Public);
  if (currentTime <= startTimestamp) revert Code_2(startTimestamp);

  if (startTimestamp == 0) revert Code_2(startTimestamp);
  _;
}
```  

---

##### `earlyRevealIsOpen`  

- _Modifier `earlyRevealIsOpen` validates if the early reveal phase has started._
- _Used by the method [`earlyReveal`]()._
- _Used by the admin method [`setRevealValues`](./Methods.md#setrevealvalues "Link to setRevealValues")._


```javascript
modifier earlyRevealIsOpen() {
  uint currentTime = block.timestamp;
  if (status != Status.EarlyReveal) 
    revert Code_1(status, Status.EarlyReveal);
  
  if (currentTime <= startTimestamp) revert Code_2(startTimestamp);
  if (startTimestamp == 0) revert Code_2(startTimestamp);
  _;
}
```  

---

#### Other modifiers

##### `costs`

- _Modifier `costs` validates if `msg.value` is enough to pay for the minting._
- _Used by the methods [`whitelistPhase1Mint`]( "Link to whitelistPhase1Mint"), [`whitelistPhase2Mint`]( "Link to whitelistPhase2Mint"), [`whitelistPhase3Mint`]( "Link to whitelistPhase3Mint")._

```javascript
    modifier costs(uint amount) {
        uint value = (mintPrice * amount);
        if (msg.value < value) revert LowAmount(msg.value);
        _;
    }
```  

| Parameter | Type     | Description                    |
| :-------- | :------- | :-------------------------     |
| `amount`  | `uint`   | _The amount of tokens to mint, is passed by the base metod._|

---
