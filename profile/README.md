## metaCAMPUS Decentralized Transcripting System

A blockchain-based system for managing and verifying student academic transcripts. This system enables secure, transparent, and immutable record-keeping for educational institutions while providing instant verification capabilities.

## Short Summary
A Decentralized Transcripting System for immutable, student-controlled transcripts with instant, global verification and granularity to individual Student Learning Outcomes(SLOs).

### Problems metaCAMPUS Solves

Transferring credits or transcripts between colleges and universities is a slow, expensive, and fragmented process:

- Students often wait weeks for transcripts to be processed and mailed.
- The administrative cost of transcript handling is extremely high, with institutions spending significant resources on manual reviews and third-party verification services.
- Receiving institutions rely on manual checks, which makes it easy for fake transcripts or falsified records to slip through.
- Students lack direct ownership of their records and must depend on institutions every time they need to share them.

This leads to delays in admissions, transfer approvals, and job applications, while draining institutional resources and undermining trust in academic records.

### Our Solution

A Decentralized Transcripting System that directly addresses these issues:

- **Immutable Records**: Academic credentials are permanently stored via Algorand smart contracts.
- **Decentralized Verification**: Every transcript entry is cryptographically verified, eliminating the risk of fake credentials.
- **Cost Efficiency**: By removing middlemen, transcript verification becomes affordable and scalable.
- **Student Ownership**: Students control their transcripts and decide when and where to share them.
- **Global Portability**: Transcripts can be instantly verified across institutions and borders without extra overhead.

## Technical Description

- **PyTeal Smart Contracts (Algorand AVM)**: Manage student onboarding, transcript requests, approvals, and verification through immutable logic.
- **AlgoSDK (JavaScript)**: Handles client-side interactions with Algorand Testnet for verification and updates.
- **Pera Wallet SDK**: Provides secure wallet-based authentication and transaction signing for students and administrators.
- **Low Fees and Fast Finality**: Algorand processes transactions in under 5 seconds at a fraction of a cent, enabling real-time transcript operations.
- **Privacy-Preserving Design**: Only transcript hashes are stored on-chain; sensitive student data remains securely with the issuing institution.

### The Drawbacks of Other Chains and Advantages of Algorand

- **Ethereum/EVM chains**: Gas fees and slower settlement make routine transcript updates impractical.
- **Private blockchains**: Lack global transparency and still rely on centralized trust between institutions.
- **Algorand**: Combines public immutability, low fees, sub-5-second settlement, and efficient AVM smart contracts, making it uniquely suited for education systems.

### Key Features

- **Immutable Records**: Academic data stored permanently on Algorand blockchain
- **Instant Verification**: Real-time transcript verification using cryptographic hashes
- **Student Privacy**: Hash-based identification protects student personal information
- **Institution Control**: Colleges manage their own student onboarding and transcript updates
- **Global Access**: Worldwide institutions can verify transcripts instantly
- **Cost Effective**: Minimal blockchain transaction fees compared to traditional verification

## 🏗️ Technology Stack

- **Blockchain**: Algorand Testnet
- **Frontend**: Next.js 15 with TypeScript
- **UI Framework**: Tailwind CSS with shadcn/ui components
- **Wallet Integration**: Pera Algo Wallet SDK
- **Smart Contracts**: PyTeal (Python for Algorand)
- **Blockchain SDK**: AlgoSDK for JavaScript

## 🚀 Quick Start

### Prerequisites

- Node.js 18+
- npm or yarn
- Pera Algo Wallet (mobile app or browser extension)
- Algorand Testnet account with ALGO tokens

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/metacampus-org/easy-a-hackathon
   cd easy-a-hackathon/easy-a-hackathon-frontend
   ```

2. **Install dependencies**
   ```bash
   npm install --legacy-peer-deps
   ```

3. **Start the development server**
   ```bash
   npm run dev
   ```

4. **Access the application**
   - Open [http://localhost:3000](http://localhost:3000)
   - Connect your Pera Algo Wallet
   - Choose your role: Student, College Admin, or External Institution

---

Built with ❤️ for the future of education technology on the blockchain. Powered by xAI
