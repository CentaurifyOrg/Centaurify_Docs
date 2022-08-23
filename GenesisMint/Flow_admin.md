![Logo](https://www.centaurify.com/_next/image?url=%2Fimg%2Flogo%2Fcentaurify-logo.svg&w=1920&q=75)

| Product      | Type               | Description                |
| :--------    | :-------           | :------------------------- |
| Genesis Mint | NFT Smart Contract | GoldenTicket  - PFP        |

<-- Back to [ReadTheDocs](ReadTheDocs_Genesis_Mint.md#table-of-contents "Back to ReadTheDocs")

---

# Admin Flow

_This admin flow describes the different admin steps and tasks for this Genesis Mint smart contract._

_The different tasks of the admin role are listed below._

- [Deploy Smart Contract](#deploy-smart-contract).
- [Initiate Pre-Mint Phases]()
- [Initiate Public Mint Phase]()
- [Initiate Early Reveal Phase]()
- [Initiate Final Reveal Phase]()
- [Withdraw Revenue]()

- [Update State Variables]()

---

## Deploy Smart Contract 

_The deployer of the smart contract is automatically set as the owner account._

- The contract constructor will:
- Set the deployer address as the `owner` account.
- Set the `owner` account as the `recipient` account.
- Set the default `royalty` percentage to 7.5 %.
- Set the `owner` account as the `royalty` receiver.
- Mint `500` Golden Tickets to the `owner` account.


