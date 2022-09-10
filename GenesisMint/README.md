![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)  

| Product      | Type               | Description                |
| :--------    | :-------           | :------------------------- |
| Genesis Mint | NFT Smart Contract | Collection AAA |

---

# README - Genesis Mint Smart Contract

This is the README for the [GenesisMint](https://github.com/Centaurifly/ethereum_repository/blob/merge_genesis_mint/smart_contracts/contracts/nft/genesis_mint/GenesisMint.sol) smart contract, developed for [Centaurify](https://www.centaurify.com), by the [Viken Blockchain Solutions](https://www.vikenblockchain.com) team.

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

## Introduction


_**Genesis mint** is an NFT Collection smart contract. It utilizes the new ERC721A library developed by the [AZUKI](https://www.azuki.com/) team on behalf of Chiru Labs.  [erc721a docs](https://chiru-labs.github.io/ERC721A/#/ "ERC721A documentation")_

**Genesis Mint - Collection AAA** is the first NFT Collection launched by the Centaurify team. 
- The smart contract has multiple pre-mint phases and a public mint phase. 
- Each pre-mint phase utilizes whitelists and  MerkleProof verification by implementing  OpenZeppelins { MerkleProof.sol } contract. 
- In the public mint phase, anyone can mint a preset amount of tokens.
- After the public mint, we have two more phases. These phases are EarlyReveal and Reveal. The EarlyReveal phase will allow an nft holder to reveal their PFP avatar. 
- The front-end and back-end servers manage all the API calls handling the metadata and the image files.   

The concept is simple, before the EarlyReveal phase, all Collection AAA nft holders will see the GoldenTicket.m4 (below) as the NFT image until their unique PFP Avatar (below) is revealed. 

<p>
  <img id="img1" src="https://user-images.githubusercontent.com/41997352/188978593-a1b66272-8d90-43c1-a3ee-c7dd5472a527.png" height="150" alt="Golden Ticket">
  <img src="https://user-images.githubusercontent.com/41997352/188979996-d2a871b0-d7a2-4893-a742-9149e0254dde.jpg" height="150" width= "150" alt="Sneek Peek">
  <img src="https://user-images.githubusercontent.com/41997352/188979962-21728958-15bb-4b93-a17e-83217673643e.jpeg" height="150" width="150" alt="Sneek Peek">
</p>

By hodling the **Collection AAA** NFTs, the hodler will get many benefits within the Centaurify ecosystem. The benefits are, among other things, listing on our future marketplace with a 0% platform fee and more benefits. 

For more information regarding the Genesis Mint and the benefits, read the Genesis Mint [pitch deck]( https://www.centaurify.com/files/FINAL%20NFT%20DECK%20f_compressed.pdf "Genesis Mint - Pitch Deck") and see the [landing page](https://www.centaurify.com/whitelist "Genesis Mint landing page.").


## Table of contents

- [README - Genesis Mint Smart Contract](#readme---genesis-mint-smart-contract)
  - [Introduction](#introduction)
  - [Table of contents](#table-of-contents)
  - [Documentation](#documentation)
  - [Instructions](#instructions)
   - [Clone the project](#clone-the-project)
   - [Install instructions](#install-instructions)
   - [Compile the smart contracts](#compile-the-smart-contracts)
   - [Deploy the smart contracts](#deploy-the-smart-contracts)
   - [Test the smart contracts](#test-the-smart-contracts)
  - [Related Contracts](#related-contracts)
  - [🧑‍⚖️ Authors](#️-authors)


## Documentation

- [Read The Docs](ReadTheDocs_Genesis_Mint.md#read-the-docs---genesis-mint "Genesis Mint READTHEDOCS")


## Instructions


### Clone the project

  ```bash
    git clone https://github.com/Centaurifly/ethereum_repository.git
  ```

- Go to the projects smart contract directory

  ```bash
    cd smart_contracts
  ```


### Install instructions

- Install all the dependencies.  
  
  ```bash
    yarn
  ```  

### Compile the smart contracts

*Contracts are **auto** compiled on **deployment** and **unit-testing**.*  

- Manually re-compile the contracts only after changes to the smart-contracts.  

  ```bash
    yarn build
  ```  


### Deploy the smart contracts

- To deploy the smart contracts in a local test enviroment, you will need two terminal tabs/windows open. 

  **In terminal one:**  

  - Spin up a local node.  
  
  ```bash
    yarn node
  ```

  **In terminal two:**  

  - deploy **GenesisMint** smart-contract.  
  
  ```bash
    yarn deploy_local_genesis
  ```


### Test the smart contracts

*Smart contracts are **auto** compiled and deployed to a local test enviroment.*   

- Run **Genesis Mint** unit-tests.  
  
  ```bash
    yarn test_local
  ```

_______________________________________


## Related Contracts

These smart contracts are part of GenesisMint.

- [GenesisMint.sol](https://github.com/Centaurifly/ethereum_repository/blob/merge_genesis_mint/smart_contracts/contracts/nft/genesis_mint/GenesisMint.sol "Main NFT Smart-contract")

- [GenesisStorage.sol](https://github.com/Centaurifly/ethereum_repository/blob/merge_genesis_mint/smart_contracts/contracts/nft/genesis_mint/GenesisStorage.sol "Genesis storage Smart-contract")


## 🧑‍⚖️ Authors

- [@dadogg80](https://www.github.com/dadogg80)
