# Multichain Crypto Wallet

A Multichain crypto wallet library that supports Ethereum, Bitcoin, Solana, Waves, and other EVM-compatible blockchains such as Binance Smart Chain, Polygon, and Avalanche.

---

## About

A library for building multi-chain crypto wallets with support for Ethereum, Bitcoin, Solana, Waves, and various EVM-compatible chains.

---

## Installation

```bash
npm install multichain-crypto-wallet
# or
yarn add multichain-crypto-wallet
```

---

## Usage

```javascript
const MultiChainWallet = require('multichain-crypto-wallet');

// Example usage here
```

---

## Features

- Generate mnemonics and create wallets for multiple blockchains.
- Fetch balances for native coins and tokens.
- Generate wallets from mnemonic phrases.
- Get addresses from private keys.
- Retrieve transaction details.
- Transfer native coins or tokens.
- Encrypt and decrypt private keys.
- Token information queries.
- Smart contract calls on supported blockchains.

---

## Supported Networks

- Ethereum & EVM-compatible chains (Binance Smart Chain, Polygon, Avalanche, etc.)
- Bitcoin
- Solana
- Waves
- Tron

---

## Methods

- **Generate Mnemonic**
- **Create Wallet**
- **Get Balance (Native coins & Tokens)**
- **Generate Wallet from Mnemonic**
- **Get Address from Private Key**
- **Get Transaction**
- **Transfer**
- **Encryptions (Encrypt/Decrypt Private Keys)**
- **Token Info**
- **Smart Contract Call (Ethereum, Waves, Tron, etc.)**

*See the full documentation and code examples in source files for more details.*

---

## Smart Contract Call Example

### Ethereum network

```javascript
const data = await multichainWallet.smartContractCall({
  rpcUrl: 'https://ethereum-sepolia-rpc.publicnode.com',
  network: 'ethereum',
  contractAddress: '0x5592EC0cfb4dbc12D3aB100b257153436a1f0FEa',
  method: 'transfer',
  methodType: 'write',
  params: ['0x2455eC6700092991Ce0782365A89d5Cd89c8Fa22', '1000000000000000000'],
  contractAbi: [
    {
      constant: false,
      inputs: [
        { name: '_to', type: 'address' },
        { name: '_value', type: 'uint256' },
      ],
      name: 'transfer',
      outputs: [{ name: '', type: 'bool' }],
      payable: false,
      stateMutability: 'nonpayable',
      type: 'function',
    },
  ],
});
```

### Waves network

```javascript
const data = await multichainWallet.smartContractCall({
  network: 'waves',
  methodType: 'write',
  rpcUrl: 'https://nodes-testnet.wavesnodes.com',
  contractAddress: '3N9uzrTiArce1h9VCqK3QUUZmFqBgg5rZSW',
  privateKey: 'your_private_key',
  method: 'deposit',
  payment: [{ assetId: null, amount: 1000 }],
  params: [],
});
```

### Tron network

```javascript
const data = await multichainWallet.smartContractCall({
  network: 'tron',
  rpcUrl: 'https://nile.trongrid.io',
  contractAddress: 'TXLAQ63Xg1NAzckPwKHvzw7CSEmLMEqcdj',
  method: 'transfer(address,uint256)',
  methodType: 'write',
  contractAbi: [
    {
      constant: false,
      inputs: [
        { name: '_to', type: 'address' },
        { name: '_value', type: 'uint256' },
      ],
      name: 'transfer',
      outputs: [{ name: '', type: 'bool' }],
      payable: false,
      stateMutability: 'nonpayable',
      type: 'function',
    },
  ],
  params: [
    { type: 'address', value: 'TEVuGfgLkQCVXs7EtjMiQp3ZSSUkEbNnVS' },
    { type: 'uint256', value: 1000000 },
  ],
  privateKey: 'your_private_key',
});
```

---

## License

This project is licensed under the MIT License.
