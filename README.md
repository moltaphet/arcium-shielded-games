# 🎮 Arcium Shielded Games
**The Engine for Hidden-Information & Zero-Knowledge Gaming**

Arcium Shielded Games is a high-performance framework designed to bring "Hidden State" mechanics to on-chain gaming. By leveraging **Multi-Party Computation (MPC)** via the Arcium Network, we enable complex game logic where player hands, strategic moves, and RNG outcomes remain encrypted throughout the gameplay.

---

## 🛡️ The Problem: The "Full Information" Curse
Traditional on-chain games (on Solana, Ethereum, etc.) are fully transparent. This transparency destroys the core mechanics of many game genres:
* **Poker/TCGs**: Everyone can see your hand in the mempool or on-chain state.
* **Strategy (Fog of War)**: Your unit positions and resources are public.
* **Social Deduction**: Roles and secret identities are easily leaked.

**Arcium Shielded Games fixes this by moving the "Game State" into a confidential computation layer.**

---

## ✨ Core Features & Architecture
### 1. Private State Management
Player hands and inventories are stored as **Secret Shares**. No one—not even the validators or other players—can see the raw data during the game.

### 2. Confidential Rules Engine
The engine executes game logic (e.g., comparing hand strengths or calculating damage) inside an MPC cluster. Only the **Outcome** (who won or the result of a move) is revealed, keeping the underlying strategy private.

### 3. Verification without Revelation
Using Arcium's infrastructure, players can prove they made a valid move (e.g., "I played a card I actually own") without showing the card itself to the public.

---

## ⚙️ Technical Deep Dive
The implementation in `src/main.rs` showcases a **Shielded Card Engine**:
* **Encrypted Dealing**: Cards are represented as structs and dealt into shielded player buckets.
* **MPC Hand Ranking**: A specialized function iterates through encrypted values to find the maximum score without decrypting individual cards.
* **Atomic Settlement**: Once the winner is determined in the dark, the pot or state update is finalized on the base layer.

---

## 🚀 Getting Started
### Prerequisites
* Rust & Cargo (Latest Stable)
* Arcium CLI (Optional for local simulation)

### Installation & Testing
Clone the repository and run the shielded simulation:
```bash
git clone [https://github.com/](https://github.com/moltaphet/arcium-shielded-games.git)
cd arcium-shielded-games
cargo test -- --nocapture

```

---

## 🛠 Project Roadmap

* [ ] **Shielded Deck Shuffling**: Implementing verifiable private shuffling.
* [ ] **Fog of War Module**: Spatial privacy for on-chain strategy games.
* [ ] **Zk-Proof Integration**: For instantaneous move validation between MPC rounds.

---

## 🤝 Contribution

Part of the Arcium Developer RTG. Building the future of private, fair, and decentralized gaming.

**Join the revolution. Play in the dark. 🛡️🔥**
