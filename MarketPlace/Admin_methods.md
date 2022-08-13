![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product                | Type                       | Description                                               |
| :--------------------- | :------------------------- | :-------------------------------------------------------- |
| Centaurify NFT product | Marketplace Smart Contract | Used by the CentArt NFT Marketplace to mint ERC721 tokens |

---  

- [Admin Methods](#admin-methods)
    - [`updateServiceFee`](#updateservicefee)
    - [`updateServiceWallet`](#updateservicewallet)

---  

<-- Back to [ReadTheDocs](ReadTheDocs_marketplace.md#table-of-contents "Back to ReadTheDocs")

## Admin Methods

_These methods that are restricted to the `ADMIN_ROLE`._

---  

#### `updateServiceFee`

- _Updates the service fee of the contract._  
- _Restricted to only `ADMIN_ROLE`._  

```javascript
    function updateServiceFee(uint _serviceFee) external onlyRole(ADMIN_ROLE) {
        serviceFee = _serviceFee;
    }
```  

| Parameter     | Type      | Description                                                    |
| :------------ | :-------- | :------------------------------------------------------------- |
| `_serviceFee` | `uint`    | _The updated service fee in percentage to charge for selling and buying on the marketplace._ |

#### `updateServiceWallet`

- _Restricted method used to set the serviceWallet._  
- _Restricted to only `ADMIN_ROLE`._  
- _Emits the event `ServiceWalletUpdated`._

```javascript
    function updateServiceWallet(address payable _serviceWallet) external onlyRole(ADMIN_ROLE) {
       serviceWallet = _serviceWallet;
       emit ServiceWalletUpdated(serviceWallet);
    }
```  

| Parameter        | Type               | Description                                   |
| :------------    | :--------          | :-------------------------------------------- |
| `_serviceWallet` | `address payable`  | _The new account to receive the service fee._ |

---  
