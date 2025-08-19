🔐 FHE Adder
FHE Adder is a privacy-preserving web application powered by ZAMA's Fully Homomorphic Encryption Virtual Machine (FHEVM). It allows users to perform encrypted addition of two numbers (0-255) on the Sepolia testnet, ensuring data privacy through FHE. The project integrates MetaMask for blockchain interaction and includes a Hardhat setup for FHE-enabled smart contract development.
🚀 Features

Encrypted Addition: Numbers are homomorphically encrypted using FHEVM.
Privacy by Design: Inputs remain encrypted; only the result is decrypted on request.
ZAMA FHEVM Integration: Leverages ZAMA's relayer-sdk-js for secure computation.
MetaMask Support: Connects to Sepolia testnet for secure transactions.
Relayer SDK Integration: Handles encryption and ZK proofs client-side.
Interactive UI: Responsive design with matrix rain, circuit nodes, and particles.
Hardhat Support: Tools for compiling, testing, and deploying FHE contracts.

🛠 Installation
Prerequisites

Node.js (>= 20.x)
Hardhat (installed via npx or globally)
MetaMask browser extension
Git
Sepolia Testnet ETH (for gas fees)
Infura API Key (for Sepolia access)
Etherscan API Key (optional, for contract verification)

Clone the Repository
git clone https://github.com/DarellBoyle/FHEAdder.git
cd FHEAdder

Install Dependencies
npm install ethers express cors dotenv

Configure Environment
Create a .env file in the project root:
PORT=3001
MNEMONIC=your_wallet_mnemonic
PRIVATE_KEY=your_private_key
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/your_infura_api_key
INFURA_API_KEY=your_infura_api_key
ETHERSCAN_API_KEY=your_etherscan_api_key
KMS_ADDRESS=0x1364cBBf2cDF5032C47d8226a6f6FBD2AFCDacAC
RELAYER_URI=https://relayer.testnet.zama.cloud
CONTRACT_ADDRESS=0x4dcF2502c67986a2EFCBc6558fd6b78BD9835e3c

Note: KMS_ADDRESS, RELAYER_URI, and CONTRACT_ADDRESS are hardcoded in index.html but can be overridden in .env.
Compile Contracts
npx hardhat compile

Deploy to Sepolia
npx hardhat run deploy/index.ts --network sepolia

Run Locally
npm start

Open http://localhost:3001 in your browser, ensuring MetaMask is connected to Sepolia.
🧠 How It Works

Users input two numbers (0-255).
Numbers are encrypted using ZAMA's Relayer SDK.
Encrypted values are sent to the smart contract for addition.
The contract stores the encrypted sum.
Users can decrypt the result via the relayer on request.

📄 Contracts
Located in the contracts/ directory. The main contract is FHECounter.sol.
📚 Technologies

Solidity + Hardhat
ZAMA FHEVM
Ethers.js (v6.15.0)
ZAMA Relayer SDK (v0.1.2)
Express.js (backend)
HTML/CSS/JS (Vanilla + futuristic styles)

✅ Demo
Hosted version: Coming soon
🔐 Disclaimer
This is a demonstration project for FHEVM integration and is not audited for production use.
📄 License
BSD-3-Clause-Clear License. See the LICENSE file for details.
Enjoy building privacy-first blockchain apps with ZAMA! 🔐✨
