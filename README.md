# Cause Taiko Platform

A blockchain-based platform for transparent charitable donations with real-time tracking, NFT rewards, and impact scoring on Taiko.

---

## Overview

The **Cause Taiko Platform** enables fully transparent charitable giving by leveraging blockchain technology on Taiko. Donors can track their contributions in real-time, earn NFT badges for their support, and monitor the impact of their donations through a comprehensive scoring system.

---

## Project Repositories

- **[Smart Contracts](https://github.com/aryan877/cause-taiko-contracts):** Solidity contracts for donation tracking and NFT rewards.
- **[Frontend](https://github.com/aryan877/cause-taiko-next.js):** Next.js web application.
- **[Indexing](https://github.com/aryan877/cause-taiko-goldsky-subgraph):** Goldsky subgraph for event indexing.

---

## Key Features

- **Transparent Fund Tracking:** Real-time monitoring of donation flows and fund utilization.
- **NFT Badge System:** Reward donors based on contribution levels (Bronze, Silver, Gold, Diamond).
- **Impact Scoring:** Quantifiable measurement of donation impact.
- **Milestone Tracking:** Track cause progress through milestones.
- **Real-time Analytics:** Visualize donation trends and impact metrics.
- **User Profiles:** Detailed donor profiles with contribution history.

---

## Technical Setup

### Smart Contracts

1. **Install dependencies**:

   - Clone the repository.
   - Run `npm install` in the project directory.

2. **Set up environment variables**:

   - Create a `.env` file with your private key:
     ```env
     PRIVATE_KEY=your_private_key_here
     ```

3. **Deploy contracts**:

   - Compile contracts: `npx hardhat compile`.
   - Deploy to Taiko testnet:
     ```bash
     npx hardhat run scripts/deploy-taiko.ts --network taiko-hekla
     ```

4. **Run tests**:
   - Execute `npx hardhat test` for unit tests.
   - For gas reporting, set `REPORT_GAS=true` and run the tests again.

---

### Goldsky Integration

1. **Set up Goldsky**:

   - Create a Goldsky account.
   - Install The Graph CLI: `npm install -g @graphprotocol/graph-cli`
   - Install Goldsky CLI: `curl https://goldsky.com | sh`
   - Obtain your API key from the Goldsky dashboard
   - Login to Goldsky: `goldsky login`

2. **Watch Tutorial**:

   For detailed setup guidance, watch [this wonderful tutorial](https://www.youtube.com/watch?v=DsqMxaWAml8) by [@javiertrujillog](https://github.com/javiertrujillog) from Goldsky.

---

### Frontend (Next.js)

1. **Install dependencies**:

   - Clone the frontend repository and run `yarn install`.

2. **Set up environment variables**:

   - Create a `.env.local` file:
     ```env
     NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID=your_project_id
     NEXT_PUBLIC_CONTRACT_ADDRESS=contract_address_here
     NEXT_PUBLIC_GRAPHQL_URL=subgraph_endpoint_here
     NEXT_PUBLIC_CHAIN_ID=167009
     ```

3. **Database setup**:

   - Use Neon PostgreSQL and configure the `DATABASE_URL` in `.env.local`.

4. **Prisma setup**:

   - Generate the Prisma client with `npx prisma generate`.
   - Push the Prisma schema with `npx prisma db push`.

5. **Run the application**:
   - Start the development server with `yarn dev`.

---

## Indexed Events

The platform tracks the following events for indexing and analytics:

- `CauseCreated`
- `DonationReceived`
- `MilestoneAdded`
- `MilestoneCompleted`
- `BadgeEarned`
- `FundsWithdrawn`
- `CauseTargetReached`
- `ImpactScoreUpdated`

---

## API Routes

- **`/api/causes`**: Get all causes.
- **`/api/causes/[id]`**: Get specific cause details.
- **`/api/users/[address]`**: Get user profile and donation history.
- **`/api/search-causes`**: Search for causes.
- **`/api/causes/[id]/feature`**: Toggle featured status for a cause.

---

## Acknowledgments

- **Taiko Labs:** For the Taiko testnet infrastructure.
- **Goldsky:** For subgraph indexing solutions.

---

## License

MIT
