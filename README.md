
# CryptoZombies DApp — Midterm Project

## Academic Context
**Institution:** California State University, Fullerton  
**Course:** CPSC 559 - Advanced Blockchain Technologies  
**Project Type:** Midterm Project  
**Semester:** Fall 2025  
**Instructor:** Prof. Wenlin Han  

---

## Team Members

| Name | CWID | Email |
|------|------|--------|
| Shrutik Kupekar | 884426727 | shrutikkupekar@csu.fullerton.edu |
| Janya Jaiswal | 878062934 | janyaj@csu.fullerton.edu |
| Gaurav Desai | 830343299 | gdesai19@csu.fullerton.edu |
| Indrayani Bhosale | 842614851 | indrayanibhosale75@csu.fullerton.edu |

---

## Project Overview
This **Decentralized Application (DApp)** extends the original CryptoZombies tutorial into a **fully interactive blockchain game**.  
It is developed using **Solidity**, **Truffle**, **Web3.js**, and **Ganache** for local blockchain simulation.

### Gameplay Features
Players can:
- Create, breed, rename, and delete individual zombies.  
- Form entire **Zombie Armies** through a multiple-minting feature.  
- **Level up** zombies using Ether payments.  
- View unique, DNA-based zombie visuals and traits in a **Halloween-themed UI**.  

---

## Local Setup & Execution Guide

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/dgkans/CryptoZombie-main.git
````

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Start Ganache

* Open **Ganache GUI**.
* Verify configuration:

  * **RPC Server:** `http://127.0.0.1:7545`
  * **Network ID:** `5777`
* Import the **first Ganache account’s private key** into your MetaMask wallet.

### 4️⃣ Compile & Deploy Contracts

```bash
truffle compile
truffle migrate --reset --network development
```

#### 4.1 Connect the Contract Address

* Locate your deployed contract address inside:

  ```
  build/contracts/ZombieOwnership.json
  ```

  under the key:
  `networks["5777"].address`
* Copy this address and update it in:

  ```html
  const CONTRACT_ADDRESS = "<your_contract_address_here>";
  ```

  inside your `index.html` file.

### 5️⃣ Run Local Web Server

```bash
npx http-server . -p 8080
```

### 6️⃣ Open in Browser

Visit [http://127.0.0.1:8080](http://127.0.0.1:8080)
Connect your MetaMask wallet and select the **Localhost 7545** network.

---

## Key Features & Improvements

### Smart Contract Enhancements

* **Zombie Breeding:** Combine DNA from two owned zombies to create a new one.
* **Delete Zombie:** Added `deleteZombie()` with `ZombieDeleted` event.
* **Rename Zombie:** `changeName()` allows custom naming of owned zombies.
* **Level-Up with Ether:** Pay `0.001 ETH` to upgrade a zombie’s level.
* **Improved Events:** Real-time event logs for leveling, deletion, and creation.
* **Zombie Army:** Batch minting of multiple zombies with a single click.

### Frontend / UI Enhancements

* **Halloween-Themed UI:** Pumpkin background, neon-orange text, spooky fonts.
* **3D Flip-Card Animations:** Flip to reveal DNA traits and random personality.
* **DiceBear Integration:** Unique avatars generated from DNA hashes.
* **Responsive Grid:** Display all zombies owned by the connected account.
* **Transaction Feedback:** Real-time MetaMask status (pending, success, fail).

---

## Smart Contract Summary

| Contract                | Description                                             |
| ----------------------- | ------------------------------------------------------- |
| **ZombieFactory.sol**   | Core logic for zombie creation and DNA generation.      |
| **ZombieFeeding.sol**   | Handles breeding and feeding interactions.              |
| **ZombieHelper.sol**    | Utility functions for renaming and leveling up zombies. |
| **ZombieAttack.sol**    | Placeholder for future battle mechanics.                |
| **ZombieOwnership.sol** | Implements ERC-721 NFT ownership and transfer logic.    |

---

## Troubleshooting

| Problem                 | Solution                                                       |
| ----------------------- | -------------------------------------------------------------- |
| MetaMask not connecting | Switch to **Localhost 7545** network.                          |
| Contract mismatch       | Use the **ZombieOwnership** address from Truffle build output. |
| Ganache desync          | Restart Ganache and re-deploy using `truffle migrate --reset`. |
| JSON-RPC error          | Refresh local blockchain and MetaMask connection.              |
| UI not updating         | Refresh the page and reconnect the wallet.                     |

---

## Tech Stack

* **Solidity** – Smart Contract Development
* **Truffle** – Compilation & Deployment Framework
* **Ganache** – Local Blockchain Environment
* **Web3.js** – Ethereum Frontend Interaction
* **MetaMask** – Wallet Integration
* **HTML / CSS / JS** – Frontend UI Development


