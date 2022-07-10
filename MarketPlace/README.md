# CentArt NFT Marketplace

Centaurify is a live event and Music NFT universe. 

## Table of Contents

- [CentArt NFT Marketplace](#centart-nft-marketplace)
  - [Table of Contents](#table-of-contents)
  - [Background](#background)
  - [Deployments](#deployments)
  - [Install](#install)
  - [Usage](#usage)
  - [Audits](#audits)
  - [Contributing](#contributing)
  - [License](#license)

## Background

Centaurify offers a music niched NFT marketplace and a full scale ticketing solution for live events.  

By tokenizing tickets with NFT and Smart contract technology using a multi chain solution Centaurify will prevent scalping, fraud, and give the control of the secondary market back to the organisers and artists.  

Built by artists for artists.  
Empowering Music!

See the [documentation](docs/), the [contracts](contracts/NFT/), and the full [documentation](https://) for more information on Centaurify and the CentArt platform.

## Deployments

CentBaseMarketplaceBETA.sol deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Goerli           | []() |

CentBase721BETA.sol deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Goerli           | []() |

CentBaseWhitelistBETA.sol deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Goerli           | []() |

CentBaseRoyaltySplitterBETA.sol deployment addresses:

| Network          | Address                                    |
| ---------------- | ------------------------------------------ |
| Ethereum Mainnet | []() |
| Goerli           | []() |

## Install

To install dependencies and compile contracts:

```bash
git clone https://github.com/CentaurifyOrg/smart_contracts.git && cd CentArt
yarn install
yarn compile
```

## Usage

**To deploy CentArt contracts to localhost you need two terminals open:**

Terminal one:

```bash
yarn ganache
```

Terminal two:  

```bash
yarn deploy_local_nft
```

**To run hardhat tests written in javascript you need two terminals open:**

Terminal one:

```bash
yarn ganache
```

Terminal two:

```bash
yarn test_local
yarn coverage
```

> Note: artifacts and cache folders may occasionally need to be removed between standard and coverage test runs.

## Audits

input an aduit text here.

## Contributing

Contributions to CentArt are welcome by anyone interested in writing more tests, improving readability, optimizing for gas efficiency, or extending the protocol via new zone contracts or other features.

When making a pull request, ensure that:

- All tests pass.
- Code coverage remains at 90% (coverage tests must currently be written in hardhat).
- All new code adheres to the style guide:
  - All lint checks pass.
  - Code is thoroughly commented with natspec where relevant.
- If making a change to the contracts:
  - Gas snapshots are provided and demonstrate an improvement (or an acceptable deficit given other improvements).
  - Reference contracts are modified correspondingly if relevant.
  - New tests (ideally via foundry) are included for all new features or code paths.
- If making a modification to third-party dependencies, `yarn audit` passes.
- A descriptive summary of the PR has been provided.

## License

[MIT](LICENSE) © 2022 Centaurify / Viken Blockchain Solutions.