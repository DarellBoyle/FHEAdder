# 🔐 FHE Adder

FHE Adder is a web application showcasing Fully Homomorphic Encryption (FHE) using ZAMA's fhEVM protocol 🚀. It enables secure addition of two numbers (0–255) on the Sepolia testnet, leveraging MetaMask for blockchain interaction and ZAMA's relayer for encryption/decryption. The project also includes a Hardhat setup for developing and deploying FHE-enabled Solidity smart contracts. 🛡️

## ✨ Features

* 🔢 **Encrypted Addition**: Add two integers (0–255) using FHE for data privacy.
* 🦊 **MetaMask Integration**: Connect to the Sepolia testnet for secure blockchain transactions.
* 🔒 **ZAMA fhEVM**: Uses `relayer-sdk-js` for encrypting/decrypting inputs and results.
* 🎨 **Interactive UI**: Matrix rain, circuit nodes, and particle animations.
* 📜 **Debug Console**: Real-time logs for transparency during encryption and blockchain operations.
* 🛠️ **Hardhat Support**: Compile, test, and deploy FHE-enabled smart contracts.

## 📋 Prerequisites

* **Node.js**: v20+
* **MetaMask**: Installed and configured for Sepolia
* **Sepolia ETH**: For gas fees
* **ZAMA Relayer SDK**: Loaded via CDN (v0.1.2)
* **Package Manager**: npm/yarn/pnpm
* **Infura API Key**: For Sepolia RPC
* **Etherscan API Key** (optional): For verification

## 🛠️ Installation

```bash
git clone https://github.com/DarellBoyle/FHEAdder.git
cd FHEAdder
npm install ethers express cors dotenv
```

### Set Up `.env`

Create a `.env` file with:

```env
PORT=3001
MNEMONIC=your_wallet_mnemonic
PRIVATE_KEY=your_private_key
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/your_infura_api_key
INFURA_API_KEY=your_infura_api_key
ETHERSCAN_API_KEY=your_etherscan_api_key
KMS_ADDRESS=0x1364cBBf2cDF5032C47d8226a6f6FBD2AFCDacAC
RELAYER_URI=https://relayer.testnet.zama.cloud
CONTRACT_ADDRESS=0x4dcF2502c67986a2EFCBc6558fd6b78BD9835e3c
```

> ℹ️ These are also hardcoded in `index.html`, but `.env` allows overrides.

## 🔧 Compile & Test

```bash
npm run compile
npm run test
```

## 🚀 Usage

### Start Server

```bash
npm start
```

Visit [http://localhost:3001](http://localhost:3001)

### Connect MetaMask

1. Click "Connect MetaMask"
2. Ensure you're on Sepolia testnet

### Perform Encrypted Addition

1. Enter two integers (0–255)
2. Click "Add Numbers"
3. Click "Show Result" to decrypt 🎉

## 📦 Deploying Smart Contracts

```bash
npx hardhat node                  # Local Node
npx hardhat deploy --network localhost
npx hardhat deploy --network sepolia
npx hardhat verify --network sepolia <contract_address>
npx hardhat test --network sepolia
```

## 📂 Project Structure

```
FHEAdder/
├── contracts/           # Smart contracts
├── deploy/              # Deployment scripts
├── tasks/               # Hardhat tasks
├── test/                # Tests
├── frontend/public/     # HTML/CSS/JS frontend
├── server.js            # Express backend
├── .env                 # Env vars
├── hardhat.config.ts    # Hardhat config
├── package.json         # Node config
└── README.md            # This file
```

## 📜 Scripts

| Script             | Description                      |
| ------------------ | -------------------------------- |
| `npm run compile`  | Compile smart contracts 🔧       |
| `npm run test`     | Run tests 🧪                     |
| `npm run coverage` | Generate test coverage report 📊 |
| `npm run lint`     | Lint the code ✅                  |
| `npm run clean`    | Clean artifacts 🧹               |
| `npm start`        | Start Express server 🌐          |

## 🔍 Technical Details

### Backend

* Express.js
* `cors`, `dotenv`
* Sets COOP & COEP headers

### Frontend

* `ethers.js` v6.15.0
* `relayer-sdk-js` v0.1.2
* Matrix/circuit animations

### Smart Contract

* Sepolia: `0x4dcF2502c67986a2EFCBc6558fd6b78BD9835e3c`
* Uses ZAMA KMS: `0x1364cBBf2cDF5032C47d8226a6f6FBD2AFCDacAC`

### Hardhat

* Local & testnet deploys
* Secure `.env` management

### Security

* COOP/COEP enforced
* Input validation (0–255)
* EIP-712 for decryption 🖋️

## 🛠️ Troubleshooting

* **MetaMask Missing**: Install and unlock it
* **Wrong Network**: Switch to Sepolia
* **KMS Error**: Check address & connectivity
* **Input Invalid**: Must be 0–255
* **TX Failures**: Check Sepolia ETH balance
* **Hardhat Issues**: Verify `.env` setup

## 📄 License

BSD-3-Clause-Clear. See [LICENSE](./LICENSE).

## 🆘 Support

Built with ❤️ by the ZAMA team.
Check the [FHEVM Quick Start Tutorial](https://docs.zama.ai) or open an issue.

---

Let me know if you'd like this as a downloadable file or pushed directly to your repo.

