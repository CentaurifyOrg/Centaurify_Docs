![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product      | Type               | Description                |
| :--------    | :-------           | :------------------------- |
| Genesis Mint | NFT Smart Contract | GoldenTicket  - PFP        |

<-- Back to [ReadTheDocs](ReadTheDocs_Genesis_Mint.md#table-of-contents "Back to ReadTheDocs")

---

# Admin Flow

_This admin flow describes the different admin steps and tasks for this Genesis Mint smart contract._

_The different tasks of the admin role are listed below._

- [Deploy Smart Contract](#deploy-smart-contract).
- [Initiate Pre-Mint Phases](#initiate-pre-mint-phases)
- [Initiate Public Mint Phase](#initiate-public-mint-phase)
- [Initiate Early Reveal Phase](#initiate-early-reveal-phase)
- [Initiate Final Reveal Phase](#initiate-reveal-phase)
- [Withdraw Revenue](#withdraw-revenue)

- [Update State Variables](#update-state-variables)
- [Other Admin Metods](#other-admin-methods)

---

## Deploy Smart Contract  

_You can read more about the contract constructor in the description below._

### Contract Constructor  

| Parameter    | Type   | Description |
|:---------    | :----  | :---------- |
|`_contractUri`| string | The contractUri is read by OpenSea for collection description and royalty information|

**The constructor will:**  

- Set the deployer address as the `owner` account.
- Set the `contractURI` to the `_contractURI` parameter.
- Set the `owner` account as the `recipient` account.
- Set the default `royalty` percentage to 7.5 %.
- Set the `owner` account as the `royalty` receiver.
- Mint `500` Golden Tickets to the `owner` account.

---  

## Initiate Pre-Mint Phases  

_The Admin is responsible for initiating the different premint mint phases._  

Initiate the premint phases by calling the methods below.

- [`setPhaseOneMintValues`](./Methods_admin.md#setphaseonemintvalues)
- [`setPhaseTwoMintValues`](./Methods_admin.md#setphasetwomintvalues)
- [`setPhaseThreeMintValues`](./Methods_admin.md#setphasethreemintvalues)

## Initiate Public Mint Phase  

Initiate the public mint phase by calling the method below.  

- [`setPublicMintValues`](./Methods_admin.md#setpublicmintvalues)  

## Initiate Early Reveal Phase  

Initiate the early reveal phase by calling the method below.  

- [`setEarlyReveal`](./Methods_admin.md#setearlyrevealvalues)  

## Initiate Reveal Phase  

Initiate the final reveal phase by calling the method below.  

- [`setRevealValues`](./Methods_admin.md#setrevealvalues)  

## Withdraw Revenue  

_Only the `owner`/ admin account can execute the `withdraw` method, and withdraw the revenue from the **Cent Collection AAA** smart contract._

- [`withdraw`](./Methods_admin.md#withdraw)  

## Update State Variables  

_This smart contract has some dedicated admin methods to update the state variables listed below._  

- [Set URI methods](./Methods_admin.md#set-uri-methods)  
- [`setMerkleRoot`]()
- [`setRecipient`](./Methods_admin.md#setrecipient)
- [`setMintPrice`]()
- [`setMaxItemsPerTx`](./Methods_admin.md#setmaxitemspertx)

## Other Admin Methods  

- [`RemoveStuckTokens`]()
- [`ownerMint`]()  

