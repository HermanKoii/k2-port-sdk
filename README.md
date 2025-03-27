# @_koii/k2-port: Proof of Reliable Transmission (PoRT) Library

## Project Overview

`@_koii/k2-port` is a TypeScript library designed for generating and submitting Proof of Reliable Transmission (PoRT) to the Koii Network. This library facilitates the process of creating and propagating verifiable transmission proofs across distributed nodes.

### Key Features
- Node discovery for Koii Network attention game nodes
- Automatic wallet generation and management
- Cryptographically signed transmission proofs
- Flexible configuration options
- Support for both browser and Node.js environments

### Use Cases
- Decentralized content verification
- Reliable data transmission tracking
- Blockchain-based proof generation

## Installation

Install the library using npm or yarn:

```bash
npm install @_koii/k2-port
# or
yarn add @_koii/k2-port
```

## API Reference

### `PoRT` Class

#### Constructor
```typescript
constructor(initParams?: InitParams)
```

**Initialization Parameters:**
- `trustedNodeAddress` (optional): URL to a trusted node. Default: `"https://k2-tasknet.koii.live"`
- `propagationCount` (optional): Number of nodes to send PoRT to. Default: `3`
- `namespaceId` (optional): Namespace identifier. Default: `"Attention"`
- `walletLocation` (optional): Key of wallet in local storage. Default: `"k2-wallet"`
- `ignoreRejection` (optional): Flag to ignore connection rejections. Default: `false`
- `connectionWait` (optional): Wait for connection/rejection before sending anonymous PoRTs. Default: `false`

#### Methods

##### `propagatePoRT(id: string)`
Submit a Proof of Reliable Transmission for a given content ID.

**Parameters:**
- `id`: Content identifier for which to generate and submit PoRT

**Example:**
```typescript
const port = new PoRT();
await port.propagatePoRT('content_identifier');
```

##### `signPort(id: string)`
Generate signed transmission proof for a content ID.

**Parameters:**
- `id`: Content identifier to sign

**Returns:** Signed port data with public key and signed message

## Repository Structure
- `src/`: TypeScript source files
  - `index.ts`: Main library implementation
  - `types.ts`: Type definitions
- `webpack.config.js`: Webpack configuration for bundling
- `tsconfig.json`: TypeScript compilation settings
- `package.json`: Project metadata and dependencies

## Dependencies
- `tweetnacl`: Cryptographic signing
- `bs58`: Base58 encoding
- `js-sha256`: SHA-256 hashing

## Contributing

### Setup
1. Clone the repository
2. Install dependencies: `yarn install`
3. Build the project: `yarn build`

### Running Tests
Currently, no specific test suite is configured. Contributions to add comprehensive testing are welcome!

### Guidelines
- Use TypeScript
- Follow existing code style
- Add/update documentation with your changes
- Submit pull requests with clear descriptions

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Disclaimer
This library is part of the Koii Network ecosystem and is provided as-is. Use with caution in production environments.