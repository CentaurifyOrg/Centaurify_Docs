## Deploy scripts

### File: deploy_and_verify.js

[deploy_and_verify.js](/deploy/deploy_and_verify.js)

_This script is used to deploy and verify the smart contract on etherscan or equal blockexplorer._

### Instructions 

Run this command in your console:

```bash
yarn deploy_and_verify --network YOUR_NETWORK_OF_CHOICE
``` 

This should deploy and verify the smartcontracts on the given network.

### File: depoy_local.js

[deploy_local.js](/deploy/deploy_local.js)

_This script is used to deploy the smart contract on a local dev-chain like ganache._

### Instructions 

Run this command in your console:

```bash
yarn deploy_local
``` 

This should deploy the smartcontracts on the local dev-chain.

The output should look like below:

```bash
Deploying contract now...
Contract deployed to: 0x67B5b22098B00161bcF4b811EC1c794692A6fdb5
Contract deployed by: 0xb57c3804433c0320C8470d680aC76FE5210531ab
```  

```bash
Successfully submitted source code for contract
contracts/GenesisMint.sol:GenesisMint at 0x67B5b22098B00161bcF4b811EC1c794692A6fdb5
for verification on Etherscan. Waiting for verification result...

Successfully verified contract GenesisMint on Etherscan.
https://mumbai.polygonscan.com/address/0x67B5b22098B00161bcF4b811EC1c794692A6fdb5#code
Verified Contract: 0x67B5b22098B00161bcF4b811EC1c794692A6fdb5
Done in 45.75s.
```