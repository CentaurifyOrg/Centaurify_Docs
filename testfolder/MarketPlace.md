# Marketplace









## Methods

### ERC721_Interface

```solidity
function ERC721_Interface() external view returns (bytes4)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bytes4 | undefined |

### FeeReceiver

```solidity
function FeeReceiver() external view returns (address)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

### OwnerCutPerMillion

```solidity
function OwnerCutPerMillion() external view returns (uint256)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | uint256 | undefined |

### PublicationFeeInWei

```solidity
function PublicationFeeInWei() external view returns (uint256)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | uint256 | undefined |

### RoyaltyRegistry

```solidity
function RoyaltyRegistry() external view returns (contract IRoyaltyRegistry)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | contract IRoyaltyRegistry | undefined |

### Weth

```solidity
function Weth() external view returns (contract IWeth)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | contract IWeth | undefined |

### acceptedTokenMap

```solidity
function acceptedTokenMap(address) external view returns (bool)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bool | undefined |

### cancelOrder

```solidity
function cancelOrder(bytes32 orderId) external nonpayable
```



*Cancel an already published order  can only be canceled by seller or the contract owner*

#### Parameters

| Name | Type | Description |
|---|---|---|
| orderId | bytes32 | - ID of the published order |

### createOrder

```solidity
function createOrder(address nftAddress, uint256 tokenId, uint256 priceInWei, uint256 expiresAt, address paymentToken) external payable returns (bytes32)
```



*Creates a new order*

#### Parameters

| Name | Type | Description |
|---|---|---|
| nftAddress | address | - Non fungible registry address |
| tokenId | uint256 | - ID of the published NFT |
| priceInWei | uint256 | - Price in Wei for the supported coin |
| expiresAt | uint256 | - Duration of the order (in hours) |
| paymentToken | address | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bytes32 | undefined |

### executeOrder

```solidity
function executeOrder(bytes32 orderId) external payable
```



*Executes the sale for a published NFT*

#### Parameters

| Name | Type | Description |
|---|---|---|
| orderId | bytes32 | - ID of the published order |

### orderByOrderId

```solidity
function orderByOrderId(bytes32) external view returns (bytes32 id, address seller, address nftAddress, uint256 tokenId, uint256 price, uint256 expiresAt, address paymentToken)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _0 | bytes32 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| id | bytes32 | undefined |
| seller | address | undefined |
| nftAddress | address | undefined |
| tokenId | uint256 | undefined |
| price | uint256 | undefined |
| expiresAt | uint256 | undefined |
| paymentToken | address | undefined |

### owner

```solidity
function owner() external view returns (address)
```



*Returns the address of the current owner.*


#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

### pause

```solidity
function pause() external nonpayable
```



*lets the owner pause this contract*


### paused

```solidity
function paused() external view returns (bool)
```



*Returns true if the contract is paused, and false otherwise.*


#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bool | undefined |

### renounceOwnership

```solidity
function renounceOwnership() external nonpayable
```



*Leaves the contract without owner. It will not be possible to call `onlyOwner` functions anymore. Can only be called by the current owner. NOTE: Renouncing ownership will leave the contract without an owner, thereby removing any functionality that is only available to the owner.*


### setAcceptedToken

```solidity
function setAcceptedToken(address token, bool accepted) external nonpayable
```



*Sets the token to the specified &#39;accepted&#39; state*

#### Parameters

| Name | Type | Description |
|---|---|---|
| token | address | - Address of the token we want to edit |
| accepted | bool | - New accpeted state |

### setFeeReceiver

```solidity
function setFeeReceiver(address feeReceiver) external nonpayable
```



*Sets the receipient address for fees*

#### Parameters

| Name | Type | Description |
|---|---|---|
| feeReceiver | address | - Address of the address that receives fees |

### setOwnerCutPerMillion

```solidity
function setOwnerCutPerMillion(uint256 _ownerCutPerMillion) external nonpayable
```



*Sets the share cut for the owner of the contract that&#39;s  charged to the seller on a successful sale*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _ownerCutPerMillion | uint256 | - Share amount, from 0 to 999,999 |

### setPublicationFee

```solidity
function setPublicationFee(uint256 _publicationFee) external nonpayable
```



*Sets the publication fee that&#39;s charged to users to publish items*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _publicationFee | uint256 | - Fee amount in wei this contract charges to publish an item |

### setRoyaltyRegistry

```solidity
function setRoyaltyRegistry(address royaltyRegistry) external nonpayable
```



*Sets the royalty registry&#39;s address*

#### Parameters

| Name | Type | Description |
|---|---|---|
| royaltyRegistry | address | - New address to be used for royalty registry |

### transferOwnership

```solidity
function transferOwnership(address newOwner) external nonpayable
```



*Transfers ownership of the contract to a new account (`newOwner`). Can only be called by the current owner.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| newOwner | address | undefined |

### unpause

```solidity
function unpause() external nonpayable
```



*lets the owner unpause this contract*




## Events

### ChangedAcceptedToken

```solidity
event ChangedAcceptedToken(address token, bool accepted)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| token  | address | undefined |
| accepted  | bool | undefined |

### ChangedFeeReceiver

```solidity
event ChangedFeeReceiver(address feeReceiver)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| feeReceiver  | address | undefined |

### ChangedOwnerCutPerMillion

```solidity
event ChangedOwnerCutPerMillion(uint256 ownerCutPerMillion)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| ownerCutPerMillion  | uint256 | undefined |

### ChangedPublicationFee

```solidity
event ChangedPublicationFee(uint256 publicationFee)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| publicationFee  | uint256 | undefined |

### ChangedRoyaltyRegistry

```solidity
event ChangedRoyaltyRegistry(address royaltyRegistry)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| royaltyRegistry  | address | undefined |

### MarketFeePaid

```solidity
event MarketFeePaid(uint256 amount)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| amount  | uint256 | undefined |

### OrderCancelled

```solidity
event OrderCancelled(bytes32 id, address indexed seller, address nftAddress)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| id  | bytes32 | undefined |
| seller `indexed` | address | undefined |
| nftAddress  | address | undefined |

### OrderCreated

```solidity
event OrderCreated(bytes32 id, uint256 indexed assetId, address indexed seller, address nftAddress, uint256 priceInWei, address paymentToken, uint256 expiresAt)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| id  | bytes32 | undefined |
| assetId `indexed` | uint256 | undefined |
| seller `indexed` | address | undefined |
| nftAddress  | address | undefined |
| priceInWei  | uint256 | undefined |
| paymentToken  | address | undefined |
| expiresAt  | uint256 | undefined |

### OrderFulfilled

```solidity
event OrderFulfilled(bytes32 id, address indexed seller, uint256 totalPrice, address paymentToken, address indexed buyer)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| id  | bytes32 | undefined |
| seller `indexed` | address | undefined |
| totalPrice  | uint256 | undefined |
| paymentToken  | address | undefined |
| buyer `indexed` | address | undefined |

### OrderSuccessful

```solidity
event OrderSuccessful(bytes32 id, uint256 indexed assetId, address indexed seller, address nftAddress, address indexed buyer)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| id  | bytes32 | undefined |
| assetId `indexed` | uint256 | undefined |
| seller `indexed` | address | undefined |
| nftAddress  | address | undefined |
| buyer `indexed` | address | undefined |

### OwnershipTransferred

```solidity
event OwnershipTransferred(address indexed previousOwner, address indexed newOwner)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| previousOwner `indexed` | address | undefined |
| newOwner `indexed` | address | undefined |

### Paused

```solidity
event Paused(address account)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| account  | address | undefined |

### Unpaused

```solidity
event Unpaused(address account)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| account  | address | undefined |



