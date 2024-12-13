# OnChain Arbitrage Bot

## Overview
The **OnChain Arbitrage Bot** is a Python-based trading tool that identifies and exploits funding rate discrepancies between Kwenta and DYDX platforms. It dynamically calculates net profits by factoring in market skew, liquidity, and associated costs, providing an efficient and robust solution for on-chain arbitrage opportunities.

---

## Features
- **Cross-Platform Arbitrage:** Integrates Kwenta and DYDX to fetch funding rates and market data.
- **Advanced Arbitrage Logic:** Incorporates leverage, skew, liquidity, and transaction costs for profit optimization.
- **Error Handling:** Includes comprehensive error management for robust execution.
- **Blockchain Integration:** Supports seamless interaction with Optimisms blockchain via middleware injection.
- **Scalable Design:** Capable of monitoring multiple markets and adapting to changing market conditions.

---

## Requirements
- **Python:** 3.8+
- Libraries:
  - `numpy`
  - `pandas`
  - `scikit-learn`
  - `kwenta`
  - `dydx3`
  - `web3`

---

## Setup
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-repo/onchain-arbitrage-bot.git
   cd onchain-arbitrage-bot
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure API Keys:**
   Update the placeholders in the `OnChainArbitrageBot` initialization with your credentials:
   - `provider_rpc`
   - `wallet_address`
   - `private_key`
   - `gql_endpoint_perps`
   - `dydx_api_url`
   - `dydx_api_key`
   - `dydx_api_secret`
   - `dydx_passphrase`

4. **Run the Bot:**
   ```bash
   python onchain_arbitrage_bot.py
   ```

---

## Usage
- **Fetch Funding Rates:**
   Use methods like `fetch_kwenta_funding_rate()` and `fetch_dydx_funding_rate()` to retrieve funding rates from Kwenta and DYDX.
- **Calculate Arbitrage:**
   Call `advanced_arbitrage()` with the necessary parameters to compute potential profits.

Example:
```python
bot = OnChainArbitrageBot(
    initial_capital=10000,
    leverage=10,
    provider_rpc="YOUR_PROVIDER_RPC",
    wallet_address="YOUR_WALLET_ADDRESS",
    private_key="YOUR_PRIVATE_KEY",
    gql_endpoint_perps="YOUR_GQL_ENDPOINT",
    dydx_api_url="YOUR_DYDX_API_URL",
    dydx_api_key="YOUR_DYDX_API_KEY",
    dydx_api_secret="YOUR_DYDX_API_SECRET",
    dydx_passphrase="YOUR_DYDX_PASSPHRASE"
)

profit = bot.advanced_arbitrage(
    funding_rate1=0.01,
    funding_rate2=0.02,
    skew1=0.5,
    skew2=0.8,
    liquidity1=1000000,
    liquidity2=800000,
    costs=[20, 25, 5, 10]
)
print(f"Net Profit: ${profit:.2f}")
```

---

## Contributing
Contributions are welcome! Feel free to submit a pull request or open an issue to suggest features or report bugs.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---

## Disclaimer
This bot is intended for educational purposes only. Users are responsible for ensuring compliance with applicable regulations and for any risks associated with live trading.
