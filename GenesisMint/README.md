![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)  

| Product      | Type               | Description                |
| :--------    | :-------           | :------------------------- |
| Genesis Mint | NFT Smart Contract | GoldenTicket  - PFP |

---

# README - Genesis Mint Smart Contract

This is the README for the [GenesisMint](GenesisMint.sol) smart contract, developed for [Centaurify](https://www.centaurify.com), by the [Viken Blockchain Solutions](https://www.vikenblockchain.com) team.

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

## Introduction

Be part of the next generation music scene, with the most exclusive web3 music community and social club in the solar system.

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
    git clone https://github.com/CentaurifyOrg/smart_contracts.git
  ```

- Go to the project directory

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
    yarn compile
  ```  


### Deploy the smart contracts

- To deploy the smart contracts in a local test enviroment, you will need two terminal tabs/windows open. 

  **In terminal one:**  

  - Spin up a local node.  
  
  ```bash
    yarn ganache
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

- [GenesisMint.sol](https://github.com/CentaurifyOrg/smart_contracts/blob/main/contracts/NFT/GenesisMint/GenesisMint.sol "Main NFT Smart-contract")


## 🧑‍⚖️ Authors

- [@dadogg80](https://www.github.com/dadogg80)

