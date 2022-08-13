
![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product                | Type                       | Description                                               |
| :--------------------- | :------------------------- | :-------------------------------------------------------- |
| Centaurify NFT Marketplace  | Marketplace Smart Contract | This is the Base NFT Marketplace smart contract |

---

# Market Orders

> _A **Market Order** is a **market item** that is listed for sale to a **fixed price** at the **Centaurify NFT Marketplace**._  

- [Market Orders](#market-orders)
  - [What Is A Market Order?](#what-is-a-market-order)
    - [Contract Code](#contract-code)
      - [Struct MarketOrder](#struct-marketorder)
      - [Variables](#variables)
      - [Market Orders Mapping](#market-orders-mapping)
      - [Market Order Methods](#market-order-methods)
        - [`createMarketOrder`](#createmarketorder)
        - [`removeMarketOrder`](#removemarketorder)
        - [`getMarketOrder`](#getmarketorder)
        - [`fetchMarketOrders`](#fetchmarketorders)
    - [Market Order Events](#market-order-events)
      - [`MarketOrderCreated`](#marketordercreated)
      - [`MarketOrderRemoved`](#marketorderremoved)
  
---

<-- Back to [Read The Docs](ReadTheDocs_marketplace.md#table-of-contents "Back to Read The Docs")

## What Is A Market Order?

- _A Market Order is a market item listed for sale to a fixed price._

- _Who can create a new Market Order?_
  - Only the TokenOwner of an market item can create a new market order.  

---

### Contract Code

These are the methods related to Market Orders :  

- [`createMarketOrder` - Creates a new market order.](#createmarketorder "Create a new market orders")

- [`removeMarketOrder` - Removes a market order.](#removemarketorder "Remove a market orders")

- [`getMarketOrder` - Get information of a market order.](#getmarketorder "Get a specific market order")  

- [`fetchMarketOrders` - Returns the id's of all market orders.](#fetchmarketorder "Get all market orders id's")

---  

#### Struct MarketOrder

- _A `MarketOrder` is a Solidity type **Struct** as shown below._

```javascript
    struct MarketOrder {
        bytes32 orderId;
        bytes32 itemId;           
        uint priceInWei;            
        bool isOrder;
        bool sold; 
    }
```

| Parameter     | Type      | Description                                    |
| :------------ | :-------- | :--------------------------------------------- |
| `orderId`     | `bytes32` | _The uniqe id of this marketOrder._            |
| `itemId`      | `bytes32` | _The uniqe id of this marketItem._             |
| `priceInWei`  | `uint`    | _The salesPrice of this marketOrder in wei._   |
| `isOrder`     | `bool`    | _Is true if this market order is active._      |
| `Sold`        | `bool`    | _Is true when this market order is sold._      |

---  

#### Variables  

| Variable Name       | Type        | Visibility | Description                           |
| :------------------ | :---------- | :--------- | :-------------------------------------|
| `arrayOfOrderIds`   | `bytes32[]` | `internal` | _bytes32 Array containing order ids._ |  

---  

#### Market Orders Mapping  

| Mapping Name     | Type                    | Visibility | Description                                   |
| :-------------   | :---------------------- | :--------- | :------------------------------------------   |
| `orderssMapping` | `bytes32 => MarketOrder`| `public`   | _Mapping is used to store the MarketOrderss._ |

---  

#### Market Order Methods

##### `createMarketOrder`

- _Creates an new `MarketOrder` withg fixed price on the marketplace._  
- _Restricted with only `nonReentrant` modifier._  
- _Restricted with only `isAuthorized` modifier._  
- _Restricted with `isNotActive` modifier._  
- _Returns the `OrderId` of the market order._  

```javascript
        function createMarketOrder(bytes32 itemId, uint priceInWei) 
        external
        nonReentrant
        isNotActive(itemId)
        returns (bytes32)
    {}
```  

| Parameter     | Type      | Description                                                    |
| :------------ | :-------- | :------------------------------------------------------------- |
| `itemId`      | `bytes32` | _The contract address of the token to add to the marketplace._ |
| `priceInwei`  | `uint`    | _The salesPrice of this market order in wei._                  |


| Returns   | Type      | Description                          |
| :-------- | :-------- | :----------------------------------- |
| `_itemId` | `bytes32` | _Returns the bytes32 market itemId._ |


##### `removeMarketOrder`

- _Method used to remove a market order from our marketplace._ 
- _This method does not remove the market item, only the market order._ 
- _Restricted with modifier `isAuthorized` to validate the caller._
- _Emits the event `MarketOrderRemoved(bytes32 orderId, address sender)`._  

```javascript
    function removeOrder(bytes32 orderId) external isAuthorized(ordersMapping[orderId].itemId){
        bytes32 _itemId = ordersMapping[orderId].itemId;
        if (_msgSender() != itemsMapping[_itemId].tokenOwner) revert NotAuth();
        ordersMapping[orderId].isOrder = false;

        _orderRemove(orderId);
        emit MarketOrderRemoved(orderId, _msgSender());
    }
```

| Parameter | Type      | Description                                  |
| :-------- | :-------- | :------------------------------------------- |
| `orderId` | `bytes32` | _The Id of the order to remove from the marketplace._ |


##### `getMarketOrder`

- _Method used to get information of a specific market order._  

```javascript
    function getMarketOrder(bytes32 orderId) external view returns (MarketOrder memory) {
        MarketOrder memory _order = ordersMapping[orderId];
        return _order; 
    }
```  

| Parameter | Type      | Description                        |
| :-------- | :-------- | :-------------------------------   |
| `orderId`  | `bytes32` | _The orderId to query data from._ |

| Returns      | Type     | Description                                                   |
| :----------- | :------- | :------------------------------------------------------------ |
| `MarketOrder`| `struct` | _Returns the struct with the information of the market order._ |


##### `fetchMarketOrders`

- _Method used to fetch information of live all Market orders._  
- _Returns a list of all market orders._

```javascript
    function fetchMarketOrders() external view returns (MarketOrder[] memory) {
        uint orderCount = _orderIds.current();
        uint unsoldOrderCount = _orderIds.current() - _ordersSold.current();
        uint currentIndex = 0;

        MarketOrder[] memory _orders = new MarketOrder[](unsoldOrderCount);
        for (uint i = 0; i < orderCount; i++) {
            bytes32 currentId = bytes32(i + 1);
            MarketOrder storage currentOrder = ordersMapping[currentId];
            _orders[currentIndex] = currentOrder;
            currentIndex += 1;
            
        }
        return _orders;
    }
```  

| Returns             | Type             | Description                                                |
| :------------------ | :----------      | :------------------------------------------------------    |
| `_orders`           | `MarketOrders[]` | _Returns an array of all the active marketOrders structs._ |

---  

### Market Order Events  

#### `MarketOrderCreated`  

- _Emitted when a new market order is created._  

```javascript
    event MarketOrderCreated(
        bytes32 indexed orderId,
        bytes32 indexed itemId,                
        uint priceInWei,              
        bool indexed isOrder
    );
```  

| Parameter    | Type      | Description                                  |
| :----------- | :-------- | :------------------------------------------- |
| `orderId`    | `bytes32` | _Indexed - The Id of this marketOrder._      |
| `itemId`     | `bytes32` | _Indexed - The itemId in this marketOrder._  |
| `priceInWei` | `uint`    | _The salesprice nominated in wei._           |
| `isOrder`    | `bool`    | _Indexed - true if this is an active order._ |

#### `MarketOrderRemoved`  

- _Emitted when a market order is removed._ 

```javascript
    event MarketOrderRemoved(
        bytes32 indexed orderId, 
        address indexed tokenOwner
    );
```  

| Parameter    | Type      | Description                               |
| :----------- | :-------- | :---------------------------------------- |
| `orderId`    | `bytes32` | _Indexed - The Id of this market order._    |
| `tokenOwner` | `address` | _Indexed - The token owner of this market order._ |
