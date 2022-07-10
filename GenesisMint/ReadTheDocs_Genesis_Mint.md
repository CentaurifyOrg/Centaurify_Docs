![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)  

# Read The Docs - Genesis Mint

This is the official documentation for the [GenesisMint](GenesisMint.sol) smart contract developed by [Viken Blockchain Solutions](https://www.vikenblockchain.com) for [Centaurify](https://www.centaurify.com).

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

## Introduction

Be part of the next generation music scene, with the most exclusive web3 music community and social club in the solar system.

## Table Of Contents

- [Read The Docs - Genesis Mint](#read-the-docs---genesis-mint)
  - [Introduction](#introduction)
  - [Table Of Contents](#table-of-contents)
  - [Supported Features](#supported-features)
  - [Contract Methods](#contract-methods)
    - [Admin Functions](#admin-functions)
      - [`setBaseTokenURI`](#setbasetokenuri)
      - [`setGoldenTicketURI`s](#setgoldenticketuris)
      - [`setContractURI`](#setcontracturi)
  - [Workflows](#workflows)
    - [ADMIN FLOW](#admin-flow)
      - [Usage/Examples](#usageexamples)

## Supported Features

- _Build on the ERC721A smart contract from [ChiruLabs](https://www.erc721a.org/) for cheaper batch minting and better fee optimization_
- _Support ERC2981 - Royalty Standard with the { [royaltyInfo](https://eips.ethereum.org/EIPS/eip-2981) } method._
- _Support OpenSea's { [contractURI](https://docs.opensea.io/docs/contract-level-metadata) } method for query contract metadata._
- _Supports whitelisted accounts by using MerkleTree validation._
- _Supports REVEAL feature._
- _Supports Early reveal feature._  

## Contract Methods


### Admin Functions

> _The methods below can only be called by the **OWNER** account._

---


#### `setBaseTokenURI`  

- _Will set the `_baseTokenURI` for this contract._
- _The `_baseTokenURI` is used as the base url for the unique PFPs used for this GenesisMint._  
- _The `_baseTokenURI` has to be set before `setPublicMintValues` and the Public mint phase starts, for any unique PFP image can be revealed._  


```javascript
function setBaseTokenURI(string memory __baseTokenURI) public onlyOwner {
  _baseTokenURI = __baseTokenURI;
}  
```  

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `__baseTokenURI` | `string`  | _The base Url for the NFTs of this Genesis Mint contract._ |  


---

#### `setGoldenTicketURI`s  

- _Will set the `_goldenTicketURI` for this contract._
- _The `_goldenTicketURI` is used as the pre-reveal asset for the NFTs in this GenesisMint._  
- _The `_goldenTicketURI` has to be set before `setPhase1MintValues`, and the pre-mint phase 1 starts._
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

#### `setContractURI`  

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


## Workflows

### ADMIN FLOW

_This flow will describe the Admin flow for completing all phases of this Genesis Mint and the methods available to this contracts Owner account._

#### Usage/Examples
