
![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product                     | Type                       | Description                                               |
| :--------                   | :-------                   | :-------------------------                                |
| Centaurify NFT product | Marketplace Smart Contract | Used by the CentArt NFT Marketplace to mint ERC721 tokens |

---

# Market Items

> _A Market Item is the representation of an NFT listed for sale at the **Centaurify NFT Marketplace**._  

## Table Of Content  

- [Market Items](#market-items)
  - [Table Of Content](#table-of-content)
  - [What Is A Market Item?](#what-is-a-market-item)
    - [Contract Code](#contract-code)
      - [`struct MarketItem`](#struct-marketitem)
    - [Global Variables](#global-variables)
    - [Market Item Methods](#market-item-methods)
      - [`createMarketItem`](#createmarketitem)
      - [`removeMarketItem`](#removemarketitem)
      - [`getMarketItem`](#getmarketitem)
  
---

<-- Back to [README](README.md#table-of-contents "Back to README")

## What Is A Market Item?

- _All NTFs listed for sale on the Centaurify NFT Marketplace is an **MarketItem**, with an uniqe **itemid**._

- _**Why do we create market items?**_
  - We create marketItems to have ownership and better controll of the NFT.

- _**Who can create a new Market Items to list on the Centaurify Marketplace?**_
  - Only the **OPERATOR ROLE** can create a new market item.  

---

### Contract Code

These are the methods related to Market Items :  

- [`createMarketItem` - Creates a new market item.](#createmarketitem)

- [`removeMarketItem` - Removes a market item.](#removemarketitem)

- [`getMarketItem` - Get information of a market item.]()  

- [`fetchMarketItems` - Fetches the id of all market Items.]()

- 

#### `struct MarketItem`

- _A `MarketItem` is a Solidity type **Struct** as shown below._

```javascript
    /// @notice A MarketItem is a listed token.
    struct MarketItem {
        bytes32 itemId;
        uint index;
        address payable tokenOwner;
        address operator;   
        Escrow escrow; 
        address nftContract;
        uint tokenId;
        Status status;
        bool active;
    }
```

| Parameter | Type     | Description                    |
| :-------- | :------- | :-------------------------     |
| `itemId`  | `bytes32`| _The uniqe id of this marketItem._|
| `index`  | `uint`| _The of this itemId in the `itemIndex` array._|
| `tokenOwner`| `address`| _The owner of this market Item._|
| `operator`| `address`| _The operator is the marketplace contract._|
| `escrow`| `Escrow`| _The escrow contract address._|
| `nftContract`| `address`| _The contract address of this marketItem._|
| `tokenId`| `uint`| _The tokenId of this marketItem._|
| `status`| `Status`| _The current status of this marketItem._|
| `active`| `bool`| _The activity conditon of this marketItem._|

---

### Global Variables  

---  

### Market Item Methods

#### `createMarketItem`

- _Creates an new `MarketItem` on the marketplace._  
- _Restricted to only `OPERATOR_ROLE`._  
- _Returns the `itemId` of the new market item._  

```javascript
    function createMarketItem(address nftContract, uint tokenId, address payable seller) 
        external 
        onlyRole(OPERATOR_ROLE) 
        returns (bytes32 itemId)
    {}
```  

| Parameter    | Type     | Description                    |
| :--------    | :------- | :-------------------------     |
| `nftContract`| `address`| _The contract address of the token to add to the marketplace._|
| `tokenId`    | `uint`   | _The id of the token to add to the marketplace._|
| `seller`     | `address`| _The address of the seller of this nft._|  

| Returns  | Type     | Description                    |
| :--------| :------- | :-------------------------     |
| `_itemId`| `bytes32`| _Returns the bytes32 market itemId._|


#### `removeMarketItem`

- _Method used to remove a market item from our marketplace._  
- _Restricted with modifier `isAuthorized` to validate the caller._
- _Emits the event `MarketItemRemoved()`._  

```javascript
    function removeItem(bytes32 itemId) external isAuthorized(itemId) {
        bytes32 _itemId = itemsMapping[itemId].itemId;
        if (_msgSender() != itemsMapping[_itemId].tokenOwner) revert NotAuth();

        _itemRemove(itemId);
        emit MarketItemRemoved(itemId, _msgSender());
    }
```  

| Parameter | Type     | Description                    |
| :-------- | :------- | :-------------------------     |
| `itemId`  | `bytes32`| _The itemId to remove from the marketplace._|


#### `getMarketItem`

- _Method used to get information of a specific market item._  

```javascript
    function getMarketItem(bytes32 itemId) external view returns (MarketItem memory) {
        return itemsMapping[itemId];
    }
```  

| Parameter | Type     | Description                    |
| :-------- | :------- | :-------------------------     |
| `itemId`  | `bytes32`| _The itemId to remove from the marketplace._|

| Returns     | Type      | Description                    |
| :--------   |  :------- | :-------------------------     |
| `MarketItem`| `struct`  | _Returns the information of the market item._|

---
