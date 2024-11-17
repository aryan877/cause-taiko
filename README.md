# Cause Taiko Platform

A blockchain-based platform for transparent charitable donations with real-time tracking, NFT rewards, and impact scoring on Taiko.

## Overview

The Transparent Donation Platform enables fully transparent charitable giving by leveraging blockchain technology. Donors can track their contributions in real-time, earn NFT badges for their support, and monitor the impact of their donations through a comprehensive scoring system.

## Project Repositories

- [Smart Contracts](https://github.com/aryan877/cause-taiko-contracts) - Solidity contracts for donation tracking and NFT rewards
- [Frontend](https://github.com/aryan877/cause-taiko-next.js) - Next.js web application
- [Indexing](https://github.com/aryan877/cause-taiko-goldsky-subgraph) - Goldsky subgraph for event indexing

## Key Features

- **Transparent Fund Tracking**: Real-time monitoring of donation flows and fund utilization
- **NFT Badge System**: Reward donors with NFT badges based on contribution levels
  - Bronze: 0.1 ETH
  - Silver: 0.5 ETH
  - Gold: 1.0 ETH
  - Diamond: 5.0 ETH
- **Impact Scoring**: Quantifiable measurement of donation impact
- **Milestone Tracking**: Track cause progress through defined milestones
- **Real-time Analytics**: Visualize donation trends and impact metrics
- **User Profiles**: Detailed donor profiles with contribution history

## Technical Architecture

### Smart Contracts

- Deployed on Taiko Hekla Testnet
- Solidity 0.8.20
- Uses OpenZeppelin contracts for security
- Implements ERC721 for NFT badges
- Comprehensive event emission for indexing

### Frontend

- Next.js 15
- Wagmi
- Shadcn/ui components
- ECharts
- Responsive design

### Data Indexing & Storage

- Goldsky for event indexing and transformation
  - Real-time event processing
  - Custom entity schemas
  - Automated indexing pipeline
- Neon PostgreSQL Database
  - Mirror of Goldsky subgraph data
  - High-performance queries
  - Serverless scaling
  - Automatic backups
- Mirror Pipeline Integration
  - Real-time data synchronization
  - Custom data transformations
  - Efficient data retrieval

### Smart Contracts (Taiko Hekla Testnet)

- Cause Taiko Smart Contract: [0xEF8594BAA7697BfD0bC5A9a721ADf73c4487b96c](https://explorer.hekla.taiko.xyz/address/0xEF8594BAA7697BfD0bC5A9a721ADf73c4487b96c)

### Goldsky Subgraph

- Endpoint: [https://api.goldsky.com/api/public/project_clng3ev6y7xrd01uj96bz4n7k/subgraphs/cause-taiko/0.0.1/gn](https://api.goldsky.com/api/public/project_clng3ev6y7xrd01uj96bz4n7k/subgraphs/cause-taiko/0.0.1/gn)

### Neon Database

- Region: AWS us-east-1
- Type: Serverless v2
- Connection pooling enabled
- Auto-scaling configuration

## Event Indexing Architecture

### Indexed Events

- CauseCreated
- DonationReceived
- MilestoneAdded
- MilestoneCompleted
- BadgeEarned
- FundsWithdrawn
- CauseTargetReached
- ImpactScoreUpdated

### Data Flow

1. Events emitted from smart contract
2. Goldsky indexes events in real-time
3. Mirror Pipeline transforms data
4. Neon DB stores processed data
5. Frontend queries data through API routes

## API Routes

- /api/causes - Get all causes
- /api/causes/[id] - Get specific cause details
- /api/users/[address] - Get user profile and donations
- /api/search-causes - Search causes
- /api/causes/[id]/feature - Toggle cause featured status

## Contributing

1. Fork the repository
2. Create your feature branch (git checkout -b feature/amazing-feature)
3. Commit your changes (git commit -m 'Add some amazing feature')
4. Push to the branch (git push origin feature/amazing-feature)
5. Open a Pull Request

## License

MIT

## Acknowledgments

Built during The Grant Factory Hackathon by Taiko Labs. Special thanks to:

- Taiko Labs for the testnet infrastructure
- Goldsky for their subgraph indexing solution
