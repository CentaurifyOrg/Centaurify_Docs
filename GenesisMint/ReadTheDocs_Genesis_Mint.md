![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product       | Type               | Description                |
| :--------     | :-------           | :------------------------- |
| Genesis Mint  | NFT Smart Contract | Collection AAA      |

---

# Genesis Mint - Read The Docs

This is the official documentation for the [GenesisMint](Ghttps://github.com/Centaurifly/ethereum_repository/blob/merge_genesis_mint/smart_contracts/contracts/nft/genesis_mint/GenesisMint.sol) smart contract developed by [Viken Blockchain Solutions](https://www.vikenblockchain.com) for [Centaurify](https://www.centaurify.com).

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

## Introduction

Be part of the next generation music scene, with the most exclusive web3 music community and social club in the solar system.

## Table Of Contents

- [Genesis Mint - Read The Docs](#genesis-mint---read-the-docs)
  - [Introduction](#introduction)
  - [Table Of Contents](#table-of-contents)
  - [Supported Features](#supported-features)
  - [Contract Modifiers](#contract-modifiers)
  - [Contract Methods](#contract-methods)
    - [Admin Methods](#admin-methods)
    - [User Methods](#user-methods)
  - [Workflows](#workflows)
    - [Admin Flow](#admin-flow)

## [Supported Features](Supported_features.md#supported-features)

> _Features supported by the Genesis Mint smart contract._

- _Build on the ERC721A smart contract from [ChiruLabs](https://www.erc721a.org/) for cheaper batch minting and better fee optimization_
- _Support ERC2981 - Royalty Standard with the { [royaltyInfo](https://eips.ethereum.org/EIPS/eip-2981) } method._
- _Support OpenSea's { [contractURI](https://docs.opensea.io/docs/contract-level-metadata) } method for query contract metadata._
- _Whitelisted accounts by using MerkleTree validation._
- _Three Pre-Mint Phases._
- _One Public Mint Phase._
- _Early reveal feature._  
- _REVEAL feature._

---


## [Custom Errors](Custom_errors.md#custom-errors)

## [Contract Modifiers](Modifiers.md#contract-modifiers)

> _Modifiers used to validate method parameters in the Genesis Mint smart contract._

- [Phase modifiers](Modifiers.md#phase-modifiers)
- [Other modifiers](Modifiers.md#other-modifiers)

## [Contract Methods](#contract-methods)

> _Restricted admin methods and normal user methods in the Genesis Mint smart contract._

### [Admin Methods](Methods_admin.md#admin-methods)

> _Admin methods available to the contract OWNER account._

- [Set URI methods](Methods_admin.md#set-uri-methods)
- [Set Phase methods](Methods_admin.md#set-phase-methods)

### [User Methods](Methods_user.md#user-methods)

> _User methods available to users of the Genesis mint smart contract._

- [Minting methods](Methods_user.md#mint-methods)
- [Reveal methods](Methods_user.md#reveal-methods)

## [Workflows](WorkFlows.md#workflows)

> _This page will give a description of the two main workflows for the Genesis Mint smart contract._

### [Admin Flow](Flow_admin.md#admin-flow)
