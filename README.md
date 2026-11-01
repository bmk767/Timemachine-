# timemachine

An open-source, event-driven backtesting and fully automated quantitative trading framework. `timemachine` bridges the gap between historical market data simulation (Time Machine mode) and live execution by orchestrating self-evolving, multi-agent AI logic with low-latency brokerage infrastructure.

## 🚀 Ecosystem Gap & Core Purpose

Most open-source trading bots either focus exclusively on simple technical indicator strategies or require heavy enterprise infrastructure. `timemachine` fills a critical ecosystem gap by providing an accessible, terminal-first Python framework that accomplishes two main goals:
1. **High-Fidelity Chronological Backtesting:** Rewind market states to execute high-frequency strategies against historical order books.
2. **AI Agentic Execution:** Natively orchestrates LLM trading brains (such as Grok or Claude via automated API pipelines) to adjust risk parameters, analyze real-time news sentiment, and dynamically modify execution parameters without human intervention.

---

## 🛠️ Key Architectural Features

* **Multi-Agent Orchestration:** Dynamic runtime routing for multi-agent LLM systems to analyze market volatility, manage active API key pairs, and handle risk limits.
* **Robust Socket Connectivity:** Built-in asynchronous connection handling specifically optimized for Interactive Brokers (IBKR) Native Sockets, featuring zero-lag polling and automated reconnection back-offs.
* **Cross-Platform CLI Utilities:** Pure terminal-based environment built using standard Bash/Zsh runtime configurations, featuring background execution utilities to prevent system idleness during multi-day simulation cycles.
* **Flexible Execution Backends:** Programmatic abstraction layers designed to easily transition paper trading environments to live multi-broker execution matrices (e.g., Alpaca, IBKR).

---

## 🏗️ System Architecture

```text
               +----------------------------------------+

               |         AI Agentic Brain               |
               |  (Grok / LLM Framework Orchestration)  |
               +-------------------+--------------------+
                                   |
                                   v
+------------------+   +-----------+-----------+   +--------------------+

|  Historical Data |-->|   Execution Engine    |<--| Real-Time Sockets  |
|  (Time Machine)  |   | (Strategy Evaluation) |   |    (IBKR / TWS)    |
+------------------+   +-----------+-----------+   +--------------------+
                                   |
                                   v
                       +-----------+-----------+

                       |    Broker API Layer   |
                       |   (Alpaca / Live)     |
                       +-----------------------+
```

---

## 📋 Prerequisites & Installation

### System Dependencies
Ensure your environment running macOS or Linux has Node.js (v18+) and Python (3.10+) installed.

```bash
# Verify system runtimes
node --version
python3 --version
```

### Installation
Clone the repository and install the core framework packages natively:

```bash
git clone https://github.com
cd timemachine
pip install -r requirements.txt
```

---

## ⚡ Quick Start Guide

### 1. Initialize the Environment
Configure your local API credentials and multi-agent environment variables:

```bash
cp .env.example .env
nano .env
```

### 2. Run a Historical Simulation (Time Machine Mode)
To spin up a backtest utilizing historical SPY order book data across a custom timeline:

```bash
python3 main.py --mode backtest --ticker SPY --days 30
```

### 3. Deploy the Automated Trading Daemon
To keep the automation pipeline active on your machine continuously without going idle, execute using the native background daemon:

```bash
# Keeps the terminal processing active during market hours
caffeinate -i python3 main.py --mode live --agent automated
```

---

## 🛣️ Development Roadmap

- [x] Initial event-driven architecture and core execution engine loop.
- [x] Integrated asynchronous socket connection handling for IBKR data streams.
- [ ] Implement multi-token minimization strategies to cut prompt overhead in trading loops.
- [ ] Add native support for programmatic portfolio balance restructuring (e.g., automated default sizing shifts).
- [ ] Build automated unit test workflows targeting websocket disconnect edge-cases.

---

## 🤝 Contributing

We welcome contributions from the quantitative trading and open-source AI community! Please feel free to open an issue or submit a pull request. 

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

