🔐 FHE Adder
FHE Adder is a web application showcasing Fully Homomorphic Encryption (FHE) using ZAMA's fhEVM protocol 🚀. It enables secure addition of two numbers (0-255) on the Sepolia testnet, leveraging MetaMask for blockchain interaction and ZAMA's relayer for encryption/decryption. The project also includes a Hardhat setup for developing and deploying FHE-enabled Solidity smart contracts. 🛡️
✨ Features

🔢 Encrypted Addition: Add two integers (0-255) using FHE for data privacy.
🦊 MetaMask Integration: Connects to Sepolia testnet for secure blockchain transactions.
🔒 ZAMA fhEVM: Uses relayer-sdk-js for encrypting/decrypting inputs and results.
🎨 Interactive UI: Responsive design with matrix rain, circuit nodes, and particle animations.
📜 Debug Console: Real-time logs for transparency during encryption and blockchain operations.
🛠️ Hardhat Support: Compile, test, and deploy FHE-enabled smart contracts.

📋 Prerequisites

Node.js: Version 20 or higher 🟢.
MetaMask: Browser extension configured for Sepolia testnet 🦊.
Sepolia Testnet ETH: Required for transaction gas fees ⛽.
ZAMA Relayer SDK: Loaded via CDN in the frontend (relayer-sdk-js v0.1.2) 📡.
npm/yarn/pnpm: Package manager for installing dependencies 📦.
Infura API Key: For Sepolia testnet access 🌐.
Etherscan API Key (optional): For contract verification 🔍.

🛠️ Installation

Clone the Repository 📂:
git clone https://github.com/DarellBoyle/FHEAdder.git
cd FHEAdder


Install Dependencies 📦:
npm install ethers express cors dotenv


Set Up Environment Variables ⚙️:Create a .env file in the project root with the following:
PORT=3001
MNEMONIC=your_wallet_mnemonic
PRIVATE_KEY=your_private_key
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/your_infura_api_key
INFURA_API_KEY=your_infura_api_key
ETHERSCAN_API_KEY=your_etherscan_api_key
KMS_ADDRESS=0x1364cBBf2cDF5032C47d8226a6f6FBD2AFCDacAC
RELAYER_URI=https://relayer.testnet.zama.cloud
CONTRACT_ADDRESS=0x4dcF2502c67986a2EFCBc6558fd6b78BD9835e3c

Note: KMS_ADDRESS, RELAYER_URI, and CONTRACT_ADDRESS are hardcoded in index.html but can be overridden in .env for flexibility.

Compile Smart Contracts 🔧:
npm run compile


Run Tests 🧪:
npm run test



🚀 Usage
Running the Application

Start the Server 🌐:
npm start


Access the Application 🌍:Open http://localhost:3001 in your browser.

Connect MetaMask 🔗:

Click "Connect MetaMask" 🦊.
Ensure MetaMask is set to the Sepolia testnet.


Perform Encrypted Addition ➕:

Enter two integers (0-255) in the input fields.
Click "Add Numbers" to perform encrypted addition.
Click "Show Result" to decrypt and view the result 🎉.



Deploying Smart Contracts

Start a Local FHEVM Node 🖥️:
npx hardhat node


Deploy to Local Network 🚀:
npx hardhat deploy --network localhost


Deploy to Sepolia Testnet 🌐:
npx hardhat deploy --network sepolia


Verify Contract on Etherscan 🔍:
npx hardhat verify --network sepolia 0x4dcF2502c67986a2EFCBc6558fd6b78BD9835e3c


Test on Sepolia Testnet 🧪:
npx hardhat test --network sepolia



📂 Project Structure
FHEAdder/
├── contracts/           # Smart contract source files
│   └── FHECounter.sol   # Example FHE counter contract
├── deploy/              # Deployment scripts
├── tasks/               # Hardhat custom tasks
├── test/                # Test files
├── frontend/
│   └── public/
│       └── index.html   # Frontend with HTML, CSS, and JS 🎨
├── server.js            # Express server to serve the frontend 🖥️
├── .env                 # Environment variables (PORT, MNEMONIC, etc.) ⚙️
├── hardhat.config.ts    # Hardhat configuration
├── package.json         # Node.js dependencies and scripts 📜
└── README.md            # This file 📖

📜 Available Scripts



Script
Description



npm run compile
Compile all smart contracts 🔧


npm run test
Run all tests 🧪


npm run coverage
Generate test coverage report 📊


npm run lint
Run linting checks ✅


npm run clean
Clean build artifacts 🧹


npm start
Start the Express server 🌐


🔍 Technical Details

Backend 🖥️:

Built with Express.js to serve static files and handle requests.
Uses cors for cross-origin requests and dotenv for environment variables.
Sets COOP (same-origin) and COEP (require-corp) headers for security 🔐.
Serves index.html from frontend/public.


Frontend 🌐:

Uses ethers.js (v6.15.0) for Ethereum blockchain interaction ⛓️.
Integrates ZAMA's relayer-sdk-js (v0.1.2) for FHE operations 🔒.
Features a responsive UI with animations (matrix rain, circuit nodes, particles) ✨.
Handles MetaMask connection, input validation, and blockchain transactions.


Smart Contract 📝:

Deployed on Sepolia at 0x4dcF2502c67986a2EFCBc6558fd6b78BD9835e3c.
ABI includes add (encrypted addition) and getLastResult (retrieve results).
Interacts with ZAMA's KMS contract at 0x1364cBBf2cDF5032C47d8226a6f6FBD2AFCDacAC.


Hardhat Integration 🛠️:

Configured in hardhat.config.ts for compiling, testing, and deploying FHE contracts.
Supports local FHEVM node and Sepolia testnet deployments.


Security 🔒:

Enforces COOP (same-origin) and COEP (require-corp) headers.
Validates inputs (integers 0-255) for FHE compatibility.
Uses EIP-712 signatures for secure decryption requests 🖋️.



🛠️ Troubleshooting

MetaMask Not Detected 🦊: Ensure MetaMask is installed and unlocked.
Incorrect Network 🌐: Switch to Sepolia testnet in MetaMask.
KMS Contract Error ❌: Verify KMS contract address and Sepolia connectivity.
Invalid Inputs 🚫: Use integers between 0 and 255.
Transaction Failures ⛽: Check for sufficient Sepolia ETH and gas limits.
Hardhat Errors 🛠️: Ensure MNEMONIC, INFURA_API_KEY, and other variables are set in .env.

📄 License
This project is licensed under the BSD-3-Clause-Clear License 📜. See the LICENSE file for details.
🆘 Support
Built with ❤️ by the ZAMA team. For assistance, refer to the FHEVM Hardhat Quick Start Tutorial or open an issue on GitHub.
