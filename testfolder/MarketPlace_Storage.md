# MarketplaceStorage









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



