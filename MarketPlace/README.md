![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)  

| Product                     | Type                       | Description                                               |
| :--------                   | :-------                   | :-------------------------                                |
| Centaurify NFT Marketplace  | Marketplace Smart Contract | Used by the CentArt NFT Marketplace to mint ERC721 tokens |

---

# README - Centaurify NFT Marketplace

This is the README for the CentArt [marketplace](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/Marketplace/CentBaseMarketPlaceBETA.sol) smart contract, developed for [Centaurify](https://www.centaurify.com), by the [Viken Blockchain Solutions](https://www.vikenblockchain.com) team.  

## Table of Contents

- [README - Centaurify NFT Marketplace](#readme---centaurify-nft-marketplace)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
    - [Read The Docs - Centaurify Marketplace](#read-the-docs---centaurify-marketplace)
  - [Deployments](#deployments)
  - [Install](#install)
    - [Usage](#usage)
  - [Audits](#audits)
  - [Contributing](#contributing)
  - [License](#license)

## Introduction

> Centaurify offers a music niched NFT marketplace and a full scale ticketing solution for live events.
> By tokenizing tickets with NFT and Smart contract technology using a multi chain solution Centaurify will prevent scalping, fraud, and give the control of the secondary market back to the organisers and artists.
> Built by artists for artists.  
> Empowering Music!  

### Read The Docs - Centaurify Marketplace  

See the [documentation](ReadTheDocs_marketplace.md#introduction), the [contracts](./contracts/NFT/Marketplace), and the full [documentation](https://) for more information on Centaurify and the CentArt platform.

## Deployments

[CentBaseMarketplaceBETA.sol](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/Marketplace/CentBaseMarketPlaceBETA.sol) deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Mumbai           | []() |


[CentBase721BETA.sol](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/Marketplace/CentBASE721BETA.SOL) deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Mumbai testnet   | [0xedC9Bb1F129E0B2682170535b3cA349C3Dff39A3](https://mumbai.polygonscan.com/address/0xedC9Bb1F129E0B2682170535b3cA349C3Dff39A3#code) |


CentBaseWhitelistBETA.sol deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Goerli           | []() |

CentBaseRoyaltySplitterBETA.sol deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Goerli           | []() |


## Install

To install dependencies and compile contracts:

```bash
git clone https://github.com/CentaurifyOrg/smart_contracts.git && cd CentArt
yarn
yarn compile
```

### Usage

**To run hardhat tests written in javascript:**

```bash
yarn test_local
yarn coverage
```

> Note: artifacts and cache folders may occasionally need to be removed between standard and coverage test runs.


**To deploy CentArt contracts to localhost you need two terminals open:**

Terminal one:

```bash
yarn ganache
```

Terminal two:  

```bash
yarn deploy_local_nft
```

## Audits

input an aduit text here.

## Contributing

Contributions to CentArt are welcome by anyone interested in writing more tests, improving readability, optimizing for gas efficiency, or extending the protocol via new zone contracts or other features.

When making a pull request, ensure that:

- All tests pass.
- Code coverage remains at 90% (coverage tests must currently be written in hardhat).
- All new code adheres to the style guide:
  - All lint checks pass.
  - Code is thoroughly commented with natspec where relevant.
- If making a change to the contracts:
  - Gas snapshots are provided and demonstrate an improvement (or an acceptable deficit given other improvements).
  - Reference contracts are modified correspondingly if relevant.
  - New tests (ideally via foundry) are included for all new features or code paths.
- If making a modification to third-party dependencies, `yarn audit` passes.
- A descriptive summary of the PR has been provided.

## License

[MIT](LICENSE) © 2022 Centaurify / Viken Blockchain Solutions.
