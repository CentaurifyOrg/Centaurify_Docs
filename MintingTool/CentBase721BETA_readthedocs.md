# ![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)  

| Product         | Type               | Description                                              |
| :--------       | :-------           | :-------------------------                               |
| CentERC721BETA  | NFT Smart Contract | Used by the CentArt NFT Marketplace to mint ERC721 tokens|

---

## CentBase721 Minting Contract - Read The Docs

This is the official documentation for the [CentBase721BETA](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/Minting/CentBase721BETA.sol) smart contract developed for [Centaurify](https://www.centaurify.com) by the [Viken Blockchain Solutions](https://www.vikenblockchain.com) team.

This base ERC721 smart contract is used by the CentArt NFT Marketplace `NFT Minting tool` developed by [Mlabs](https://mlabs.city/), for [Centaurify](https://www.centaurify.com).

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

### Supported Features

- _Support ERC2981 - Royalty Standard with the { [royaltyInfo](https://eips.ethereum.org/EIPS/eip-2981) } method._
- _Support OpenSea's { [contractURI](https://docs.opensea.io/docs/contract-level-metadata) } method for query contract metadata._
- _Support Royalty payout to multiple accounts, with OpenZeppelin { [PaymentSplitter](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/finance/PaymentSplitter.sol) }._

---

## Table of contents

- [Related Contracts](#related-contracts)
- [Contract Methods](#contract-methods)
  - [`mint`](#mint-a-new-token)
  - [`batchMint`](#mint-a-batch-of-nft's)
  - [`deployPaymentSplitter`](#split-royalty-between-multiple-addresses)

---

## Related Contracts

These smart contracts are part of the Centaurify Marketplace platform.

- [CentBase721BETA.sol](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/Minting/CentBase721BETA.sol)
- [CentBaseMarketPlaceBETA.sol](https://github.dev/CentaurifyOrg/smart_contracts/blob/main/unit_tests/contracts/NFT/Marketplace/%20CentBaseMarketPlaceBETA.sol#L1)
- [CentBaseWhitelistBETA.sol](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/Whitelist/CentBaseWhitelistBETA.sol)

## CentBase721BETA.sol deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Mumbai testsnet  | [0xedC9Bb1F129E0B2682170535b3cA349C3Dff39A3](https://mumbai.polygonscan.com/address/0xedC9Bb1F129E0B2682170535b3cA349C3Dff39A3#code) |

---

## Contract Methods

_These methods below can only be called by a **whitelisted** account ( ie. minting tool ) during the BETA release._

### **Mint a new token**  

_Mint a batch of new tokens and set the token royalty._

```javascript
  function mint(address to, string memory _tokenURI, address payable royaltyAddress, uint96 royaltyFee) 
    public 
    onlyWhitelistedUsers 
    feeAmount(royaltyFee)

```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `to`             | `address` | _The address to receive the NFT to be minted._ |
| `_tokenURI`      | `string`  | _The uri pointing to the metadata of this NFT._ |
| `royaltyAddress` | `address` | _The address to receive the royalty amount from secondary market sales._ |
| `royaltyFee`     | `uint96`  | _The royalty fee as percentage points. ( Example, 1000 = 10% )_ |  

#### Modifier Restrictions

| Modifier                | Parameter     | Description                |
| :--------               | :-------      |:------------------------- |
| `onlyWhitelistedUsers`  |               | _Reverts if the caller is not a `Whitelisted` address._ |
| `feeAmount(royaltyFee)` | `royaltyFee`  | _Reverts if the `royaltyFee` is above `MAX_ROYALTY_FEE`._ |

#### Mint Events

| Event     | Parameters                                            | Description                           |
| :-------- | :-------                                              |:-------------------------             |
| `Minted`  | `TokenId, TokenURI, To, RoyaltyReceiver, RoyaltyFee`  | _Emitted when a new NFT is minted._   |

---

### **Mint a batch of NFT's**

_Mint a batch of new tokens and set the token royalty._

```javascript
  function batchMint(address to, string memory _tokenURI, uint amount, address payable royaltyAddress, uint96 royaltyFee) 
    external 
    onlyWhitelistedUsers 
    feeAmount(royaltyFee)
```

| Parameter        | Type      | Description                |
| :--------        | :-------  | :------------------------- |
| `to`             | `address` | _The address to receive the NFT to be minted._ |
| `_tokenURI`      | `string`  | _The uri pointing to the metadata of this NFT._ |
| `amount`         | `uint`    | _The amount of tokens to batch mint._ |
| `royaltyAddress` | `address` | _The address to receive the royalty amount from secondary market sales._ |
| `royaltyFee`     | `uint96`  | _The royalty fee as percentage points. ( Example, 1000 = 10% )_ |  

#### Modifier restrictions

| Modifier                | Parameter     | Description                |
| :--------               | :-------      |:------------------------- |
| `onlyWhitelistedUsers`  |               | _Reverts if the caller is not a `Whitelisted` address._ |
| `feeAmount(royaltyFee)` | `royaltyFee`  | _Reverts if the `royaltyFee` is above `MAX_ROYALTY_FEE`._ |

#### Batch Mint Events  

| Event         | Parameters                                           | Description                                    |
| :--------     | :-------                                             |:-------------------------                      |
| `Minted`      | `TokenId, TokenURI, To, RoyaltyReceiver, RoyaltyFee` | _Emitted for every new NFT that is minted._            |
| `BatchMinted` | `To, MintedAmount, TokenURI, RoyaltyReceiver`        | _Emitted when the batch of new NFTs are minted._ |

---  

### **Split Royalty between multiple addresses**

_Deploys a OpenZeppelin PaymentSplitter.sol to allow split royalty between multiple accounts._

```javascript
function deployPaymentSplitter(
    address[] memory recipients, 
    uint[] memory shares, 
    uint salt
)   
    external 
    onlyWhitelistedUsers 
    returns (address)
```

| Parameter    | Type        | Description                                     |
| :--------    | :-------    | :-------------------------                      |
| `recipients` | `address[]` | _Array of accounts to split the royalty amount between._  |
| `shares`     | `uint[]`    | _Array of shares, correlating to the recipient array. Individual shares should amount to total 100 shares._ |
| `salt`       | `uint`      | _Random number used as salt._|

#### Modifier

| Modifier                | Parameter     | Description                                               |
| :--------               | :-------      |:-------------------------                                 |
| `onlyWhitelistedUsers`  |               | _Reverts if the caller is not a `Whitelisted` address._   |

#### PaymentSplitter Events  

| Event                | Parameters                      | Description                                      |
| :--------            | :-------                        |:-------------------------                        |
| `NewRoyaltySplitter` | `RoyaltySplitter, RoyaltyIndex` | _Emitted when a new RoyaltySplitter is deployed._|

## Authors

- [@dadogg80](https://github.com/Dadogg80) - [Viken Blockchain Solutions](https://vikenblockchain.com/) 
