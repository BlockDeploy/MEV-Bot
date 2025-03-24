

# MevBot - Advanced MEV Arbitrage Bot on Ethereum

[**Visit BlockDeploy**](https://blockdeploy.tech) | [**Explore Contracts**](https://blockdeploy.tech/contracts.html)

![MevBot Screenshot](https://i.ibb.co/20q8XfQd/image-3.jpg)

**MevBot** is the ultimate tool for maximizing profits through **Maximal Extractable Value (MEV)** strategies on Ethereum Mainnet. Specializing in **sandwich attacks** within the mempool, this bot targets high-slippage trades on decentralized exchanges (DEXs) like **Uniswap**, **Sushiswap**, **1inch**, **Curve**, and **Balancer**. With its advanced automation and fast liquidity analysis, MevBot is a top choice for arbitrageurs and traders looking to exploit price discrepancies effortlessly.

---

## Why MevBot Stands Out

- **Efficiency:** Achieves up to **97% profitability** with sufficient capital (5-10 ETH).  
- **Versatility:** Supports multiple DEXs and customizable slippage settings.  
- **Memecoin Advantage:** Thrives during trends like SHIB and DOGE due to high volatility and slippage.  
- **High Activity:** Processes an average of **1,500 transactions daily**, reflecting its market demand.  
- **Passive Income:** Automates MEV strategies with minimal user intervention.

---

## Features

- **Sandwich Attacks:** Buys tokens before large trades and sells after, profiting from price swings.  
- **Mempool Scanning:** Uses `fetchMempoolData` and `findNewContracts` to identify lucrative opportunities.  
- **DEX Flexibility:** Operates on Uniswap, Sushiswap, 1inch, Curve, Balancer, or all simultaneously.  
- **Slippage Control:** Adjustable settings to target specific trade thresholds (1-49%).  
- **Security:** Blacklist/whitelist functions for token and wallet filtering.  
- **Profit Withdrawal:** Simple ETH withdrawal to your wallet.

---

## Getting Started

### Prerequisites

- Ethereum Mainnet wallet with **0.25 ETH (minimum)** + gas fees.  
- Access to [BlockDeploy](https://blockdeploy.tech) for deployment.  
- Basic understanding of Solidity and MEV strategies.

### Compilation

1. Visit the "Deploy Contracts" page on [BlockDeploy](https://blockdeploy.tech).  
2. Paste the MevBot contract code into the "Contract Code" field.  
   - The code imports Uniswap V2 interfaces for token interactions.  
3. Select **Solidity version 0.6.6** from the dropdown.  
4. Click **Compile** — the "ABI" and "Bytecode" fields will populate automatically.

### Deployment

1. Navigate to the "Deploy Contract" section in BlockDeploy.  
2. Select **Ethereum (Mainnet)** as the network (testnets are not supported).  
3. Enter the **private key** of a wallet with sufficient ETH (minimum 0.25 ETH + gas) in the "Private Key" field.  
4. Specify the initial **slippage percentage** in the constructor (e.g., `5` for 5%, range 1-49).  
5. Click **Deploy**, review the network and fees in the modal window, and confirm.  
   - After deployment, you’ll receive the contract address (e.g., `0xYourBotAddress`) in the BlockDeploy logs.

---

## How to Use MevBot

### 1. Fund the Contract
- Transfer **ETH** to the contract address (`0xYourBotAddress`) — from **0.25 to 10 ETH**.  
- *More capital = higher profitability (see table below).*

### 2. Start the Bot
- In the BlockDeploy interface, locate the contract in the logs.  
- Select the **`start`** function and call it.  
- The bot will begin scanning the mempool and executing sandwich attacks.

### 3. Adjust Slippage
- Call **`updateSlippage`**, specifying a new percentage (e.g., `10` for 10%).  
- This determines which trades the bot targets.

### 4. Select DEX
- Call **`setDex`**, specifying the exchange ID:  
  - `0` - Uniswap  
  - `1` - Sushiswap  
  - `2` - 1inch  
  - `3` - Curve  
  - `4` - Balancer  
  - `5` - ALL (all at once)  
- Example: `setDex(2)` for 1inch.

### 5. Check Current DEX
- Use **`getCurrentDex`** to see which exchange the bot is operating on (returns a number from 0 to 5).

### 6. Withdraw Profits
- Call **`withdrawal`** to transfer accumulated ETH back to your wallet.

### 7. Stop the Bot
- Call **`Stop`** to temporarily halt operations (the bot will stop scanning the mempool).

---

# Interface

![MevBot Transaction Screenshot](https://i.ibb.co/SDb24rb6/Interface.png)

## Operational Details

- **Mempool Analysis:** Actively scans using `fetchMempoolData` and `findNewContracts`.  
- **Sandwich Strategy:** Executes buy/sell trades around large transactions for profit.  
- **Memecoin Boost:** Excels in high-volatility markets like memecoin trends.  
- **Transaction Volume:** Averages **~1,500 daily transactions**.  
- **Security:** Use `blacklist` and `whitelist` to filter tokens and wallets.

### Example Activity
[![MevBot Transaction Screenshot](https://i.ibb.co/kgQ0CHRy/transaction.png)](https://ibb.co/8D62ZKWB)  
*The screenshot shows typical bot activity in the mempool.*

---

## Profitability

| Capital (ETH) | Avg. Daily Profit (ETH) | Notes                     |
|---------------|--------------------------|---------------------------|
| 0.25          | 0.01 - 0.03             | Low volume, basic trades  |
| 1             | 0.05 - 0.15             | Moderate activity         |
| 5             | 0.3 - 0.8               | High profitability        |
| 10            | 0.6 - 1.5               | Optimal for memecoin runs |

*Profitability depends on capital, mempool activity, and token volatility.*

---

## Built With

- **Solidity 0.6.6**: Smart contract language.  
- **Uniswap V2 Interfaces**: For token interactions.  
- **BlockDeploy**: Deployment platform ([blockdeploy.tech](https://blockdeploy.tech)).  

---

## Disclaimer

MEV strategies involve risks, including gas fee fluctuations and market volatility. Use at your own discretion and ensure compliance with local regulations.
