# 💧 FlowFaucet

A simple **token faucet smart contract** built in Solidity that allows users to request test tokens (FLOW) once per day.  
Deployed on **Flow Testnet** at:  
👉 `0xeA7b9bD23322645DAA70AA0b3A846d01e989cf91`

---

## 🧠 Overview

The **FlowFaucet** contract lets users request a fixed amount of test tokens at controlled intervals (e.g., once per day).  
The contract owner can:
- Refill the faucet  
- Adjust token drip amount  
- Modify waiting time  
- Reset user timers  
- Withdraw tokens if needed  

This makes it perfect for testing dApps or educational blockchain demonstrations.

---

## ⚙️ Features

| Feature | Description |
|----------|--------------|
| 💸 **Drip System** | Users can claim tokens once every set interval (default: 1 day). |
| 🔒 **Access Control** | Only the contract owner can refill or withdraw funds. |
| ⚡ **Adjustable Parameters** | Owner can change drip amount and cooldown time. |
| 🕒 **Timer Reset** | Owner can reset individual or all user timers. |
| 🧾 **Event Logs** | All major actions emit events for transparency. |
| 🪙 **ETH-Compatible** | Works seamlessly on any EVM-compatible chain. |

---

## 🚀 Deployment Details

- **Network:** Flow Testnet  
- **Contract Address:** `0xeA7b9bD23322645DAA70AA0b3A846d01e989cf91`  
- **Solidity Version:** `0.8.20`  
- **License:** MIT  

---

## 📜 Contract Functions

### 🔹 Public Functions
| Function | Description |
|-----------|--------------|
| `requestTokens()` | Allows any user to request tokens once per day. |
| `getBalance()` *(optional to view in Remix)* | Use Remix “Balance” field to check contract funds. |

### 🔹 Owner-Only Functions
| Function | Description |
|-----------|--------------|
| `refill()` | Send FLOW to refill the faucet balance. |
| `withdraw(uint256 amount)` | Withdraw specific amount to the owner’s address. |
| `withdrawAll()` | Withdraw all remaining tokens. |
| `resetTimer(address user)` | Reset a specific user's cooldown timer. |
| `resetAllTimers()` | Reset all stored user timers. |
| `setDripAmount(uint256 amount)` | Change the token amount users receive. |
| `setWaitTime(uint256 time)` | Modify the cooldown period (in seconds). |

---

## 📡 Events

| Event | Trigger |
|--------|----------|
| `TokensRequested(address user, uint256 amount)` | When a user successfully requests tokens. |
| `BalanceAdded(address sender, uint256 amount)` | When the owner or others send tokens to the contract. |
| `DripAmountUpdated(uint256 newAmount)` | When drip amount changes. |
| `WaitTimeUpdated(uint256 newWaitTime)` | When cooldown time changes. |
| `Withdrawn(address owner, uint256 amount)` | When funds are withdrawn. |
| `TimerReset(address user)` | When a single user’s timer resets. |
| `AllTimersReset()` | When all timers reset. |

---

## 🧑‍💻 Usage (via Remix)

1. Open [Remix IDE](https://remix.ethereum.org).  
2. Create a new file named `FlowFaucet.sol` and paste the contract code.  
3. Compile using **Solidity 0.8.20**.  
4. Deploy on **Flow Testnet** using the **Injected Provider** (Metamask).  
5. Optionally, send test FLOW to the contract to refill the faucet.  
6. Interact with functions under the "Deployed Contracts" tab.

---

## 🔐 Security Notes

- The contract uses `require()` checks to prevent re-requests within cooldown time.  
- It ensures that withdrawals are **restricted to the owner only**.  
- Proper event logging ensures transparency of all operations.  

---

## 🧾 License
This project is licensed under the **MIT License** — free for modification and reuse.
