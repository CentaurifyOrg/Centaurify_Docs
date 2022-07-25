# ERC721Interface



> Interface for contracts conforming to ERC-721





## Methods

### approve

```solidity
function approve(address _to, uint256 _tokenId) external nonpayable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _to | address | undefined |
| _tokenId | uint256 | undefined |

### getApproved

```solidity
function getApproved(uint256 _tokenId) external view returns (address)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

### isApprovedForAll

```solidity
function isApprovedForAll(address _owner, address _operator) external view returns (bool)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _owner | address | undefined |
| _operator | address | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bool | undefined |

### ownerOf

```solidity
function ownerOf(uint256 _tokenId) external view returns (address _owner)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _owner | address | undefined |

### safeTransferFrom

```solidity
function safeTransferFrom(address _from, address _to, uint256 _tokenId) external nonpayable
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _from | address | undefined |
| _to | address | undefined |
| _tokenId | uint256 | undefined |

### supportsInterface

```solidity
function supportsInterface(bytes4) external view returns (bool)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _0 | bytes4 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bool | undefined |




