# Item Custody Tracking Project

## Overview
The Item Custody Tracking project utilizes DAML smart contracts to securely and transparently track the ownership and temporary custody of valuable items. It addresses scenarios where items are lent, borrowed, or transferred temporarily between individuals, ensuring that every transaction is verifiable and secure.

## Problem Statement
In many real-life scenarios, individuals and organizations lend items such as expensive equipment, cameras, electronics, or any valuable asset to others. Tracking these assets' temporary custody and ensuring their timely return can often lead to disputes and misunderstandings. Traditional methods such as manual logs, spreadsheets, or informal agreements are prone to errors, loss, fraud, and disputes.

This project aims to resolve these challenges by:
- Providing a reliable, immutable ledger of custody transfers.
- Enabling clear visibility of item custody status at any given time.
- Eliminating disputes related to the custody and ownership of valuable assets.

## Technology Stack
- **DAML (Digital Asset Modeling Language):** Used for creating secure and robust smart contracts.
- **DAML Script:** Employed to automate and test DAML contract scenarios.
- **TypeScript and Puppeteer:** Used to develop and run end-to-end integration tests simulating user interactions.
- **DAML JSON API and Sandbox:** Facilitating backend ledger interactions and providing the runtime environment.

## Smart Contract Design
The DAML smart contract (`ItemCustody`) consists of the following primary fields and choices:

### Template Definition
- **owner (Party):** The original owner of the item.
- **custodian (Party):** The current holder of the item.
- **itemName (Text):** Description or identifier for the item.

### Choices
- **ReleaseItemTo:** Allows the owner to transfer temporary custody to another party.
- **ReturnItemTo:** Enables the current custodian to return the custody back to the rightful owner.
- **Archive (Implicit):** A built-in DAML choice to archive the contract when custody tracking is no longer required.

## Testing
The DAML script tests verify the following scenarios:
- Successful creation of the item custody contract.
- Custody release from the owner to a borrower.
- Return of the item custody from the borrower to the original owner.
- Archiving of the contract upon completion.

Integration tests written in TypeScript with Puppeteer ensure that the DAML backend integrates seamlessly with a user interface, validating end-to-end functionality from user login, custody transfers, to handling error scenarios gracefully.

## Running the Project

### Prerequisites
- [DAML SDK](https://docs.daml.com/getting-started/installation.html)
- [Node.js](https://nodejs.org/en/download/) and npm

### Steps
1. Clone the repository.
```
git clone <repo_url>
```
2. Go into the project directory
```
cd <proj_dir>
```

## Testing the Project
Run DAML tests:
```shell
daml test
```

## Benefits
- **Immutability:** All custody transactions are recorded immutably.
- **Transparency:** Every involved party has transparent visibility into custody records.
- **Efficiency:** Eliminates manual paperwork and reduces administrative overhead.

## Future Enhancements
- Real-time notification system.
- Detailed audit trails for compliance.
- Integration with identity verification systems.

## Author
- **Bibek Lakra** : [BibekLakra91](https://github.com/bibeklakra91)

## License
This project is licensed under the Apache-2.0 License - see the [LICENSE](LICENSE) file for details.

