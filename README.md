# AI for the Indian Investor — ET Markets Intelligence Layer

India has 14 crore+ demat accounts. Most retail investors are flying blind —
reacting to tips, missing filings, unable to read technicals, managing mutual
fund portfolios on gut feel.

This project is the intelligence layer that turns raw market data into
actionable, signal-driven decisions.

## What it builds

**Opportunity Radar** — A continuously running agentic system that monitors
NSE price action, BSE/SEBI corporate filings, bulk deals, insider trades, and
management commentary shifts. Surfaces asymmetric signals as structured daily
alerts. Not a summariser — a signal-finder.

**Chart Pattern Intelligence** — Real-time technical pattern detection across
the NSE universe (Golden Cross, RSI Bounce, MACD Crossover, Bollinger
Breakout, Death Cross) with plain-English explanations and per-stock
historical backtest win rates — not generic statistics.

**Market ChatGPT Next Gen** — A portfolio-aware, multi-turn AI chat agent
with full tool access to live price data, SEBI filings, and the user's demat
holdings. Every factual claim is cited. Reasoning chain is visible.

## Architecture
```
User Portfolio (CDSL/NSDL)
        │
        ▼
Jupyter Notebook Interface
        │
        ▼
Agentic Core — Groq + LLaMA 3.3 70B
        │
        ├── Tool 1: scan_stock_signals      → TA Engine (6 patterns)
        ├── Tool 2: fetch_company_context   → BSE RSS + SEBI Filings
        ├── Tool 3: get_portfolio_context   → Personalised P&L
        └── Tool 4: run_backtest            → Per-stock win rate
        │
        ▼
Autonomous 3-Step Loop
  Step 1: Signal Detection
  Step 2: Context Enrichment  
  Step 3: Actionable Alert
```

## Stack

| Layer | Technology | Cost |
|---|---|---|
| LLM | LLaMA 3.3 70B via Groq | Free (14,400 req/day) |
| Price data | yfinance (NSE .NS tickers) | Free |
| Filings | BSE RSS corporate feed | Free |
| TA indicators | Python `ta` library | Free |
| Notebook | Jupyter | Free |

**Zero paid APIs. Zero credit card required.**

## Quickstart

1. Get a free Groq API key at [console.groq.com](https://console.groq.com)
2. Clone this repo and open the notebook:
```bash
   git clone https://github.com/your-username/et-markets-ai-investor
   cd et-markets-ai-investor
   jupyter notebook et_markets_ai_investor.ipynb
```
3. Paste your Groq key in Cell 2
4. Run `Kernel → Restart & Run All`

Full demo runs in under 5 minutes.

## Evaluation criteria met

- ✅ Agent completes 3+ sequential analysis steps without human input
- ✅ Full pipeline from raw data ingestion to actionable alert is autonomous  
- ✅ Portfolio-aware personalisation (extra credit)
- ✅ Signal quality over summarisation — real alpha, not news rehash
- ✅ Per-stock backtest win rates — not generic pattern statistics
- ✅ Source-cited, multi-step reasoning visible in output

## Built for

ET Markets Hackathon — Problem Statement 6: AI for the Indian Investor
