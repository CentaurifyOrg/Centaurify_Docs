# IMarketplace









## Methods

### cancelOrder

```solidity
function cancelOrder(bytes32 orderId) external nonpayable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| orderId | bytes32 | undefined |

### createOrder

```solidity
function createOrder(address nftAddress, uint256 tokenId, uint256 priceInWei, uint256 expiresAt, address paymentToken) external payable returns (bytes32)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| nftAddress | address | undefined |
| tokenId | uint256 | undefined |
| priceInWei | uint256 | undefined |
| expiresAt | uint256 | undefined |
| paymentToken | address | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bytes32 | undefined |

### executeOrder

```solidity
function executeOrder(bytes32 orderId) external payable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| orderId | bytes32 | undefined |

### setAcceptedToken

```solidity
function setAcceptedToken(address token, bool accepted) external nonpayable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| token | address | undefined |
| accepted | bool | undefined |

### setFeeReceiver

```solidity
function setFeeReceiver(address setFeeReceiver) external nonpayable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| setFeeReceiver | address | undefined |

### setPublicationFee

```solidity
function setPublicationFee(uint256 _publicationFee) external nonpayable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _publicationFee | uint256 | undefined |

### setRoyaltyRegistry

```solidity
function setRoyaltyRegistry(address _royaltyRegistry) external nonpayable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _royaltyRegistry | address | undefined |




