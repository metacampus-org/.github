## metaCAMPUS Decentralized Transcripting System

A blockchain-based system for managing and verifying student academic transcripts using Algorand. This system enables secure, transparent, and immutable record-keeping for educational institutions while providing instant verification capabilities.

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

## 📋 User Roles & Workflows

### 1. College Administrator (`/admin/transcript`)

**Purpose**: Onboard students and manage academic transcripts

**Workflow**:
1. Connect Pera Wallet to authenticate
2. **Onboard Student**: 
   - Enter student personal information
   - Generate unique blockchain hash identifier
   - Student receives their permanent hash ID
3. **Manage Transcripts**:
   - Search by student hash
   - Add course completion records
   - Update grades and credits
   - Submit to blockchain with digital signature

### 2. Student (`/student`)

**Purpose**: View and share their own academic records

**Workflow**:
1. Obtain student hash from their institution
2. Enter hash to view complete transcript
3. Download transcript data for offline access
4. Share verification hash with other institutions
5. Monitor academic progress and GPA

### 3. External Institution (`/verify`)

**Purpose**: Verify academic records for admissions/employment

**Workflow**:
1. Receive student hash from applicant
2. Enter hash into verification portal
3. Instantly receive verified transcript data
4. Download official verification report
5. Confirm authenticity via blockchain

## 🔐 Security & Privacy

### Data Protection
- **On-Chain**: Only hashed identifiers and encrypted academic data
- **Off-Chain**: Personal information stored securely by institutions
- **Access Control**: Students control who can access their records
- **Immutability**: Records cannot be altered once written to blockchain

### Verification Process
1. Student provides their information to the institution
2. Institution queries Algorand blockchain
3. Smart contract returns encrypted academic data
4. System verifies cryptographic signatures
5. Institution receives verified transcript with authenticity proof

## Smart Contract Architecture

### Contract 1: Badge Request Manager
**Purpose**: Handles creation of transcript or badge requests by students or administrators.
- `create_badge_request(request_data)`: Initiates transcript entry requests.
- Stores request data with timestamps.

### Contract 2: Approval Manager
**Purpose**: Ensures only authorized institutions can approve transcript or badge requests.
- `approve_badge_request(request_id)`: Institution admin approves pending requests.
- Records approval status and timestamp.

### Contract 3: Badge Issuance Manager
**Purpose**: Issues academic badges once approved.
- `create_meta_badge(badge_data)`: Institution mints transcript or course completion badge.
- Each badge is tied to a unique hash and issuance timestamp.

### Contract 4: Verification Manager
**Purpose**: Enables third-party verification of academic credentials.
- `verify_badge(badge_hash)`: Confirms transcript authenticity using Algorand's immutable ledger.

## System Interaction Flow

1. **Student Onboarding** - Admin creates a unique student hash on Algorand.
2. **Transcript Request** - Student or admin submits course completion record as a badge request.
3. **Approval** - Institution admin reviews and approves the request.
4. **Issuance** - Smart contract mints a transcript badge tied to the student hash.
5. **Verification** - External institution queries the student hash.
   - Smart contract verifies and confirms authenticity instantly, eliminating fake transcripts.

## Key Security Features

- **On-Chain Immutability**: Records cannot be altered once written.
- **Fraud Elimination**: Decentralization ensures transcripts are cryptographically verified, eliminating fake ones.
- **Auditability**: Every request, approval, and issuance is timestamped.
- **Role-Based Access**: Only verified institution admins can approve or issue.
- **Selective Disclosure**: Students only share transcript hashes, not raw personal data.

## 🛠️ Development

### Project Structure

```
easy-a-hackathon-frontend/
├── app/                          # Next.js app directory
│   ├── admin/transcript/         # College admin interface
│   ├── student/                  # Student portal
│   ├── verify/                   # Verification interface
│   └── page.tsx                  # Home page
├── components/                   # Reusable UI components
│   ├── ui/                       # shadcn/ui components
│   └── wallet-connect.tsx        # Wallet integration
├── lib/                          # Core business logic
│   ├── transcript-service.ts     # Main service layer
│   ├── algorand.ts               # Blockchain connection
│   ├── wallet.ts                 # Wallet management
│   └── utils.ts                  # Utility functions
├── contracts/                    # Smart contract code
│   └── transcript_manager.py     # PyTeal contract
└── public/                       # Static assets
```

### Key Services

#### TranscriptService
- `onboardStudent()`: Create new student blockchain record
- `updateTranscript()`: Add/modify academic data
- `verifyTranscript()`: Retrieve and verify student records
- `generateStudentHash()`: Create unique identifiers
- `calculateGradePoints()`: GPA calculations

#### WalletService  
- `connectWallet()`: Pera Wallet integration
- `signTransaction()`: Cryptographic signing
- `getWalletState()`: Connection status management

#### AlgorandService
- `createApplicationCall()`: Smart contract interactions
- `submitTransaction()`: Blockchain submissions
- `queryBlockchain()`: Data retrieval

## 🎯 Benefits

### For Students
- **Ownership**: Complete control over academic records
- **Portability**: Records travel with student globally
- **Privacy**: FERPA compliance 
- **Permanence**: Records never lost or destroyed

### For Institutions
- **Efficiency**: Automated verification processes
- **Security**: Elimination of transcript fraud
- **Cost Savings**: Reduced administrative overhead
- **Trust**: Cryptographic proofs for authenticity

### For Employers
- **Confidence**: Verified academic credentials
- **Speed**: Instant background checks
- **Compliance**: Audit trail for verification
- **Accuracy**: No human verification errors

## 🔮 Future Enhancements

### Phase 2
- **TBD**
- 
### Phase 3
- **TBD**
- 
## 🆘 Support

### Documentation
- [Algorand Developer Docs](https://developer.algorand.org/)
- [Pera Wallet Integration](https://perawallet.app/developers/)
- [Next.js Documentation](https://nextjs.org/docs)

### Promotional Video
[metaCAMPUS](https://drive.google.com/file/d/1G789QVUFMOTKkMTlcoXe3GHM2r7CZGvU/view?usp=sharing)

## FAQ

**Q: How secure is student data on the blockchain?**
A: Only transcript hashes and badge proofs are stored on-chain. Personal data remains securely off-chain with institutions, while Algorand ensures authenticity and immutability.

**Q: What happens if a student loses their transcript hash?**
A: Institutions can regenerate access by validating the student's enrollment history.

**Q: Can transcripts be modified after being stored on Algorand?**
A: No. Once a transcript or badge is issued, it cannot be altered. Updates are appended as new entries, preserving an audit trail.

**Q: How does this system eliminate fake transcripts?**
A: Each transcript is cryptographically verified on Algorand. Institutions and employers can instantly confirm authenticity against the immutable ledger, making it impossible to forge.

**Q: Is this FERPA compliant?**
A: Yes. Students control sharing of their transcript hashes, aligning with FERPA's student privacy requirements.

---

Built with ❤️ for the future of education technology on Algorand blockchain.
