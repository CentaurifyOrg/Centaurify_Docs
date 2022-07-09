## Scripts

### Script: generate_merkle_tree.js

[generate_merkle_tree.js](/generate_merkle_tree.js)

_This script is used to generate a merkletree from the whitelist CSV files and return the merkle root hash of the whitelisted accounts._

Run this command in your console:
```bash
node generate_merkle_tree.js
``` 

You will be prompted to input what list to generate, choose between :  
- mainnet_combined
- mainnet_phase1
- mainnet_phase2
- testnet 
- manual
- localtest

The response should look something like this :  

```bash
whitelist length: 3
MerkleTree Root Hash - 
> 0xb0e0daeaa9458bf08ee48808428d753f6b8517f66837bc7c0116bed2561f8a4c
``` 

### Script: frontend.js 

[frontend.js](/frontend.js)
