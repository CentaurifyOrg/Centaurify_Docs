![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product                     | Type                       | Description                                               |
| :--------                   | :-------                   | :-------------------------                                |
| Centaurify NFT Marketplace  | Marketplace Smart Contract | Used by the CentArt NFT Marketplace to mint ERC721 tokens |

---

# Contract Modifiers

## Table of contents

- [Contract Modifiers](#contract-modifiers)
  - [Table of contents](#table-of-contents)
    - [Modifiers](#modifiers)
      - [`isAuthorized(itemId)`](#isauthorizeditemid)
      - [`isNotActive(bytes32 itemId)`](#isnotactivebytes32-itemid)
      - [`costs`](#costs)

<-- Back to [Read-The-Docs](ReadTheDocs_marketplace.md#table-of-contents "Back to Read-The-Docs")

---

### Modifiers

> _The different modifiers is set to validate specific contract parameters to pass._  
> _The modifiers validating the function calls in this smart contract._  
> _Validates the correct status of the market item_.

#### `isAuthorized(itemId)`  

- _Modifier `isAuthorized` will validate if the caller is authorized._
- _Used by the method [`createMarketOrder`]( "Link to createMarketOrder()")._
- _Used by the method [`createMarketAuction`]("Link to createMarketAuction")._

```javascript
    /// @notice Modifier will validate if the caller is authorized.
    /// @param itemId The tokenId of the nft to validate.
    modifier isAuthorized(bytes32 itemId) {
        MarketItem memory _item = itemsMapping[itemId];
        if (_item.tokenOwner != _msgSender()) revert NotAuth();
        _;
    }
```  

| Parameter | Type     | Description                    |
| :-------- | :------- | :-------------------------     |
| `itemId`      | `bytes32`| _The itemId._|  


#### `isNotActive(bytes32 itemId)`

- _Modifier `isNotActive` will validate that the marketItem is not already a live item._
- _Parameter `itemId` The tokenId of the nft to validate._
- _Used by the method [`createMarketOrder`]( "Link to createMarketOrder()")._
- _Used by the method [`createMarketAuction`]("Link to createMarketAuction")._

```javascript
    /// @notice Modifier will validate that the marketItem is not already a live item.
    /// @param itemId The id of the marketItem.
    modifier isNotActive(bytes32 itemId) {
        MarketItem memory _item = itemsMapping[itemId];
        if (_item.active) revert IsActive(_item.itemId, _item.status);
        _;
    }
```  

| Parameter | Type     | Description                    |
| :-------- | :------- | :-------------------------     |
| `itemId`      | `bytes32`| _The itemId._|  


#### `costs`

- _Modifier `costs` validates if `msg.value` is enough to pay for the servicefee and the nft cost._
- _Used by the methods [`bid`]( "Link to bid"), [`executeOrder`]( "Link to executeOrder")._

```javascript
    modifier costs(uint status, bytes32 id) {
        if (status == 1 || status == 2) {
            if (status == 1) {
                MarketOrder memory _order = ordersMapping[id];
                (uint256 serviceAmount, uint256 sellerAmount, ) = _calculateFees(
                    _order.priceInWei
                );
                uint256 sum = (_order.priceInWei + serviceAmount);
                if (msg.value < sum) revert LowValue(sum);
            } else {
                MarketAuction memory _auction = auctionsMapping[id];
                (uint serviceAmount, uint sellerAmount, ) = _calculateFees(
                    _auction.highestBid
                );
                uint sum = (_auction.highestBid + serviceAmount);
                if (msg.value < sum) revert LowValue(sum);
            }
        } else {
            revert ErrorMessage("Wrong Status");
        }
        _;
    }
```  

| Parameter | Type     | Description                    |
| :-------- | :------- | :-------------------------     |
| `status`  | `uint`   | _Pass 1 for MarketOrder / Pass 2 for MarketAuction._|
| `id`      | `bytes32`| _The id of the Order or Auction._|

---
