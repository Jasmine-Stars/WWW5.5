# **Let Effort and Persistence Be Rewarded, Let Your Journey Be Recorded**

# ✨ Core Concept

A Web3 platform that transforms "participating in activities / persistent check-ins" into **verifiable on-chain records**. Users can join long-term challenges or one-time events, participate, check in, and settle using their wallets. Some activities use a **stake pool** to incentivize long-term commitment, while others use **NFT medals** to record participation. All of these are aggregated into your **Personal On-Chain Growth Profile (My Journey)**.

NebulaFlow is not just a check-in app; it is your **Web3 Action Ledger**. Here:

-   Long-term Challenges → Use the **Stake Pool Model**: Participants deposit a stake, and those who successfully complete the challenge split the pool.
-   One-time Events (e.g., meetups, offline gatherings) → Use the **NFT Model**: Issue **exclusive NFT medals** to eligible participants after the event.

# 💡 Pain Points Addressed

1.  **Lack of Motivation & Low Completion Rates**
    *   **Traditional Model:** Relies solely on willpower, lacking sustained external incentives, making it easy to give up halfway.
    *   **NebulaFlow:** Introduces real economic incentives (stakes and rewards), transforming "I must persist" into "persistence pays," significantly boosting engagement and the desire to complete.
2.  **Lack of Trust and Transparency**
    *   **Traditional Model:** Centralized platforms manage funds and rules, posing risks of fund misappropriation and opaque rule changes.
    *   **NebulaFlow:** All funds and core rules are managed by open-source smart contracts, publicly verifiable on-chain, enabling true disintermediation and procedural fairness.
3.  **Unverifiable Achievement Records**
    *   **Traditional Model:** Completion records are stored on centralized servers, lacking public credibility and permanence.
    *   **NebulaFlow:** Successfully completed challenges are permanently recorded on your chain address as **NFTs**, forming a verifiable, personal achievement archive.

# ⚙️ Core Features

### For Challenge Participants

*   **🦊 Web3 Wallet Login:** Seamlessly connect using MetaMask or similar wallets, no cumbersome registration required.
*   **🔍 Explore Challenges:** Browse various public stake-based challenge activities.
*   **💰 Pay Stake to Join:** Join a challenge with one click and a stake payment, then wait for it to begin.
*   **✅ Easy Check-in/Verification:** During the challenge period, complete daily check-ins via simple signatures or proof submission.
*   **🏆 Split the Pool & Earn NFTs:** Upon successful completion, automatically claim your reward share from the smart contract and receive a unique commemorative NFT achievement badge.

### For Challenge Creators

*   **🚀 Create Challenges:** Easily set up challenge name, description, duration, stake amount, and check-in rules.
*   **👥 Manage Activities:** View participant status and, under special circumstances, have the option to terminate an activity early.

### Platform Characteristics

*   **🤖 Smart Contract Auto-Settlement:** Participant elimination and reward distribution are fully automated, requiring no manual intervention.
*   **🔒 Fund Security:** User stakes are directly locked in audited smart contracts; the platform cannot access them.
*   **📊 Transparent On-Chain Records:** All transactions and state changes are traceable on the blockchain.

# 🏗️ Technical Architecture

### Frontend (UI)

*   **Framework:** Next.js
*   **UI & Styling:** React + Tailwind CSS
*   **Animations:** GSAP (for transitions and interactive effects)
*   **Web3 Interaction:** Ethers.js / wagmi
*   **Wallet:** MetaMask and other EVM-compatible wallets

Main pages include:
*   `Activity Hub` – Activity overview and creation entry point.
*   `Activity Detail` – Activity details / registration / check-in / conclusion operations.
*   `My Journey` – Personal profile displayed across three categories.

### Main Smart Contracts

*   **ChallengeFactory.sol**
    *   Responsible for creating and managing all activities.
    *   Supports two challenge types:
        *   `createDepositChallenge(...)` – Stake Pool Challenge
        *   `createNFTChallenge(...)` – NFT Event
    *   Core responsibilities:
        *   Challenge creation
        *   User registration / stake collection
        *   Daily check-in logic
        *   Pool settlement or NFT minting trigger upon challenge completion.

*   **RewardNFT.sol**
    *   Compliant with the ERC-721 standard.
    *   Mints NFT medals for users who complete activities.
    *   Configurable base Token URI / metadata.

# 🔗 A Complete User Journey

1.  **Create Activity**
    *   The organizer fills out the activity form on the Activity Hub page.
    *   Selects "Stake Mode" or "NFT Mode".
    *   The frontend calls the `ChallengeFactory` contract to create the activity.

2.  **User Registration**
    *   User connects their wallet.
    *   Clicks "Register / Participate".
    *   Stake Mode: Transfers the stake via `msg.value`.
    *   The contract records the user as a participant.

3.  **Activity Check-in**
    *   During the activity period:
        *   User navigates to the activity detail page.
        *   Clicks "Check-in".
        *   The contract updates the user's check-in progress and status.

4.  **Activity Conclusion**
    *   Organizer clicks "End Activity":
        *   Stake Mode: Filters users who completed the challenge and distributes the pool evenly among them.
        *   NFT Mode: Calls `RewardNFT` to mint NFTs for eligible participants.

5.  **My Journey Display**
    *   The frontend reads on-chain data related to the current wallet.
    *   Categorizes activities into **Professional Web3 / Social Web3 / Lifestyle** based on rules.
    *   Displays preview cards for ongoing activities and 🏆 completion cards for finished ones.

# 🗺️ Future Roadmap

NebulaFlow's evolution roadmap aims to build a more powerful, interconnected on-chain achievement ecosystem.

*   **🎮 V1.1 - Gamification & Social Features**
    *   Introduce a user level system and a leaderboard.
    *   Add team challenge mode, supporting collaboration and competition.
    *   Integrate a public discussion forum and in-task chat functionality.

*   **🤖 V1.5 - Automation & Expansion**
    *   Integrate Chainlink oracles to support automated verification based on external APIs (e.g., Strava workout data, Duolingo learning progress).
    *   Provide personalized activity recommendations based on a participant's historical activity on the platform.

*   **🌐 V2.0 - Decentralization & Open Ecosystem**
    *   Launch a platform governance token, gradually transitioning to DAO-based community governance.
    *   Release a protocol layer, allowing any third-party frontend to build their own applications based on NebulaFlow's smart contracts.
    *   Establish an open achievement graph, enabling users' on-chain achievements to be showcased and utilized in other Web3 applications.

### If you've read this far, you likely understand what NebulaFlow is about:

It's not just a simple "check-in tool," but a platform that transforms **"what I have done, what I have persisted in"** into **verifiable on-chain records**.

**Welcome to start your next challenge or event and begin your on-chain journey with NebulaFlow.**

