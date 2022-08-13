![Centaurify](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product                     | Type                       | Description                                               |
| :--------                   | :-------                   | :-------------------------                                |
| Centaurify NFT Marketplace  | Marketplace Smart Contract | Used by the CentArt NFT Marketplace to mint ERC721 tokens |

---

# CentArt Marketplace - Read The Docs

This is the official documentation for the [Marketplace](https://github.com/CentaurifyOrg/smart_contracts/tree/main/contracts/NFT/Marketplace/) smart contract developed by [Viken Blockchain Solutions](https://www.vikenblockchain.com) for [Centaurify](https://www.centaurify.com).

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

- [CentArt Marketplace - Read The Docs](#centart-marketplace---read-the-docs)
  - [Introduction](#introduction)
  - [How To Use The Marketplace](#how-to-use-the-marketplace)
    - [Market Item](#market-item)
    - [Market Order](#market-order)
    - [Market Auction](#market-auction)
  - [Smart Contract](#smart-contract)
    - [Contract Modifiers](#contract-modifiers)
    - [Contract Methods](#contract-methods)

---  

<-- Back to [ReadTheDocs](README.md#readme---centaurify-nft-marketplace "Back to ReadTheDocs")

## Introduction

Be part of the next generation music scene, with the most exclusive web3 music community and social club in the solar system.  

## How To Use The Marketplace

_This marketplace smart contract will allow pre-approved artists to create a market item to list at our marketplace, the artist can then sell the listed item for a **fixed price** or for the highest price in a **timed auction**._

This documentation will go through the different steps listed below.  

### Market Item

> Creating a market item is the process of preparing an NFT to be sold for a fixed price or as a timed auction.

- [Read more about market items.](MarketItems.md#market-items "Link to description of market items.")

### Market Order

> Creating a market order is to sell a market item for a pre-set fixed price.

- [Read about market orders.](MarketOrder.md#create-an-market-order "Link to description of market orders.")

### Market Auction

> Creating a market auction is to sell a market item at a timed auction.

- [Read about market auctions.](MarketAuction.md#create-an-market-auction "Link to description of market auctions.")

---  

## Smart Contract  

### Contract Modifiers

_Modifiers used to validate method parameters in the marketplace smart contract._

- [Modifiers](Modifiers.md#contract-modifiers)

### Contract Methods

_Restricted admin methods and normal user methods in the marketplace smart contract._

- [MarketItem methods](MarketItems.md#market-item-methods)  

- [Admin methods](Admin_methods.md#admin-methods)  
