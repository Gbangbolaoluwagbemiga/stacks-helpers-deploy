# gbangbola-stx-deploy

[![npm version](https://img.shields.io/npm/v/gbangbola-stx-deploy.svg)](https://www.npmjs.com/package/gbangbola-stx-deploy)

Deploy, verify, and manage **Stacks L2** smart contracts.

| | Link |
|---|------|
| **npm** | [`gbangbola-stx-deploy`](https://www.npmjs.com/package/gbangbola-stx-deploy) |
| **Repository** | [Gbangbolaoluwagbemiga/gbangbola-stx-deploy](https://github.com/Gbangbolaoluwagbemiga/gbangbola-stx-deploy) |

## Install

```bash
npm install gbangbola-stx-deploy
```

Depends on `@stacks/transactions`, `@stacks/network`, and `richiey1-stacks-helpers-types`.

## Usage

```typescript
import { deployContract, getContractInfo, isContractDeployed } from "gbangbola-stx-deploy";

// Deploy a contract
const result = await deployContract({
  contractName: "my-contract",
  codeBody: "(define-public (hello) (ok \"world\"))",
  senderKey: "your-private-key",
});

// Check if a contract is deployed
const exists = await isContractDeployed("SP...", "contract-name");

// Get contract info
const info = await getContractInfo("SP...", "contract-name");
// Returns: { source, publishHeight, clarityVersion, txId }
```

## API

### `deployContract(options)`

Deploy a Clarity contract to mainnet/testnet. Options:

- `contractName` — Name of the contract
- `codeBody` — Clarity source code
- `senderKey` — Deployer's private key
- `network?` — Stacks network
- `nonce?` — Transaction nonce
- `fee?` — Transaction fee

### `getContractInfo(contractAddress, contractName, networkUrl?)`

Fetch deployed contract information.

### `isContractDeployed(contractAddress, contractName, networkUrl?)`

Check if a contract exists on-chain.

## Development

```bash
npm install
npm run build
```

## License

MIT

## Author

gbangbolaoluwagbemiga
