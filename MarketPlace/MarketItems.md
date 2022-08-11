
# ![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product                     | Type                       | Description                                               |
| :--------                   | :-------                   | :-------------------------                                |
| Centaurify NFT product | Marketplace Smart Contract | Used by the CentArt NFT Marketplace to mint ERC721 tokens |

---

# Market Items

- _A Market Item is the representation of an NFT listed for sale at the **Centaurify NFT Marketplace**._  

## Table Of Contents

- [Market Items](#market-items)  
- [Table Of Contents](#table-of-contents)  
- [What Is A Market Item?](#what-is-a-market-item)  
  

## What is a Market Item?

- _All NTFs listed for sale on the Centaurify NFT Marketplace is an **MarketItem**, with an uniqe **itemid**._
 
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


---

<-- Back to [ReadTheDocs](ReadTheDocs_marketplace.md#table-of-contents "Back to ReadTheDocs")
