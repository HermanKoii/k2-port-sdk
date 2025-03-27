# @_koii/k2-port

## Project Overview

`@_koii/k2-port` is a TypeScript library for generating and submitting Proof of Rendering Time (PoRT) data to the KOII network. This library provides developers with a streamlined way to interact with KOII's decentralized infrastructure, specifically for the Attention Game mechanism.

### Key Features
- Generate cryptographically signed Port data
- Submit PoRT to multiple KOII network nodes
- Automatic wallet key management
- Flexible configuration for node interactions
- Support for browser and Node.js environments

### Use Cases
- Decentralized content verification
- Tracking content rendering and engagement
- Generating proof of content interaction

## Installation

Install the library using npm or yarn:

```bash
npm install @_koii/k2-port
# or
yarn add @_koii/k2-port
```

### Prerequisites
- Node.js (v14 or higher)
- TypeScript (recommended)
- A compatible browser with localStorage support (for browser environments)

## API Reference

### `PoRT` Class

#### Constructor
```typescript
constructor(initParams?: InitParams)
```

**Initialization Parameters**:
- `trustedNodeAddress` (optional): URL to a trusted KOII node. 
  - Default: `"https://k2-tasknet.koii.live"`
- `propagationCount` (optional): Number of nodes to send PoRT to.
  - Default: `3`
- `namespaceId` (optional): Namespace identifier.
  - Default: `"Attention"`
- `walletLocation` (optional): Key for wallet storage in localStorage.
  - Default: `"k2-wallet"`
- `ignoreRejection` (optional): Whether to ignore connection rejections.
  - Default: `false`
- `connectionWait` (optional): Wait for connection before sending anonymous PoRTs.
  - Default: `false`

#### Methods

##### `propagatePoRT(id: string)`
Submit Proof of Rendering Time for a specific content ID.

**Parameters**:
- `id`: A string representing the content identifier

**Returns**: 
- Submits PoRT to multiple KOII network nodes

**Example**:
```typescript
const port = new PoRT();
await port.propagatePoRT("your-content-id");
```

##### `signPort(id: string)`
Generate signed Port headers for a given content ID.

**Parameters**:
- `id`: A string representing the content identifier

**Returns**:
- `PoRTData`: Signed message and public key

## Repository Structure
- `src/`: Source TypeScript files
  - `index.ts`: Main library implementation
  - `types.ts`: TypeScript type definitions
- `package.json`: Project metadata and dependencies
- `tsconfig.json`: TypeScript configuration
- `webpack.config.js`: Webpack build configuration

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a Pull Request

### Running Tests
Currently, no specific test suite is configured. Please ensure code quality through careful review and testing.

## License

This project is licensed under the MIT License. See the package.json for details.

## Dependencies
- bs58
- tweetnacl
- js-sha256
- node-fetch

## Contact
For more information, visit [KOII Network](https://www.koii.network)