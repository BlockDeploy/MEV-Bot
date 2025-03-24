
### Instructions for Using MevBot

![Screenshot](https://i.ibb.co/20q8XfQd/image-3.jpg)

**Description:**  `MevBot`  is the most efficient MEV bot for arbitrage on Ethereum,  
actively used on decentralized exchanges (DEXs). It is designed for sandwich attacks in the mempool,  
enabling profits from large trades on Uniswap, Sushiswap, 1inch, and other DEXs. The bot actively scans the mempool  
(the pool of unconfirmed transactions), identifying profitable opportunities with high slippage,  
and automatically executes trades to maximize revenue. It operates exclusively on Ethereum Mainnet — testnets  
are not supported since transactions there lack real value.  
**Why it’s the best:**  Currently, this is one of the most advanced bots for MEV strategies,  
delivering up to 97% profitability with high capital (5-10 ETH). Amid the memecoin trend (e.g., SHIB, DOGE),  
the bot shows outstanding results due to its fast liquidity analysis and targeted attacks on large trades.  
Support for multiple DEXs (Uniswap, Sushiswap, 1inch, Curve, Balancer) and flexible slippage settings make it  
a versatile tool for experienced traders and arbitrageurs.  
**Statistics:**  The bot’s average daily transaction volume is around 1,500, confirming its high  
activity and demand in the market.  
**What it offers:**  Passive income through MEV strategies, exploitation of price discrepancies,  
and automation of trading operations on DEXs with minimal user intervention.

**Compilation:**  Go to the "Deploy Contracts" page in BlockDeploy,  
paste the code into the "Contract Code" field (it imports Uniswap V2 interfaces for token interactions),  
select Solidity version 0.6.6 from the dropdown menu,  
click "Compile" — the "ABI" and "Bytecode" fields will populate automatically.

**Deployment:**  In the "Deploy Contract" section:  
- Select the "Ethereum (Mainnet)" network — the bot works only on Ethereum’s main network,  
- Enter the private key of a wallet with sufficient ETH (minimum 0.25 ETH + gas) in the "Private Key" field,  
- Specify the initial slippage percentage in the constructor (e.g., 5 for 5%, range 1-49),  
- Click "Deploy," review the network and fees in the modal window, and confirm.  
After deployment, you’ll receive the contract address (e.g.,  `0xYourBotAddress`) in the BlockDeploy logs.

**How to Use MevBot:**  

-   **Fund the Contract:**  Transfer ETH to the contract address (`0xYourBotAddress`) — from 0.25 to 10 ETH.  
    The more capital, the higher the profitability (see table below).
-   **Start the Bot:**  In the BlockDeploy interface, locate the contract in the logs, select the  
    `start`  function, and call it.  
    The bot will begin scanning the mempool and executing sandwich attacks on high-slippage trades.
-   **Adjust Slippage:**  Call  `updateSlippage`,  
    specifying a new percentage (e.g., 10 for 10%). This determines which trades the bot targets.
-   **Select DEX:**  Call  `setDex`,  
    specifying the exchange ID: 0 - Uniswap, 1 - Sushiswap, 2 - OneInch, 3 - Curve, 4 - Balancer, 5 - ALL (all at once).  
    For example,  `setDex(2)`  for 1inch.
-   **Check Current DEX:**  Use  `getCurrentDex`,  
    to see which exchange the bot is currently operating on (returns a number from 0 to 5).
-   **Withdraw Profits:**  Call  `withdrawal`,  
    to transfer accumulated ETH back to your wallet.
-   **Stop the Bot:**  Call  `Stop`,  
    to temporarily halt operations (the bot will stop scanning the mempool).

**Operational Features:**  
- The bot actively scans the mempool using functions like  `fetchMempoolData`  and  `findNewContracts`,  
to identify trades with high profit potential.  
- Supports sandwich attacks: buys tokens before a large trade and sells after, profiting from the price difference.  
- During memecoin trends, the bot excels due to the high volatility and slippage of these tokens.  
- Blacklists/whitelists (`blacklist`,  `whitelist`) allow filtering of tokens and wallets for security.  
- Average daily transactions: ~1,500, showcasing its activity and ability to handle numerous trades.

**Example Activity:**  
[![MevBot Transaction Screenshot](https://i.ibb.co/kgQ0CHRy/transaction.png)](https://ibb.co/8D62ZKWB)  
_The screenshot shows typical bot activity in the mempool._

_Profitability depends on capital, mempool activity, and token volatility. The memecoin trend boosts results._
