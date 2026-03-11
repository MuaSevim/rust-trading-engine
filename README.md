# 🦀 RustyEngine: High-Performance Order Matching System

A **low-latency, systems-level trading engine built in Rust**.
This project demonstrates the implementation of **complex financial trading logic** using Rust’s **zero-cost abstractions**, **memory safety guarantees**, and **high-performance systems programming model**.

The engine simulates a simplified **electronic exchange matching system** capable of handling **limit orders and price-time priority matching**.

---

# 🚀 Technical Architecture

The engine is designed for **high throughput and low latency**, using a **decoupled architecture** capable of supporting **multiple concurrent markets**.

### 📊 Order Book Management

Implements an efficient **OrderBook** structure using **hash-mapped price levels** to achieve:

* **O(1) lookup** for price levels
* Fast insertion and cancellation of orders
* Efficient volume tracking

---

### ⚡ Matching Logic

A specialized **MatchingEngine** coordinates multiple **TradingPairs**, ensuring:

* Atomic order matching
* Correct bid/ask priority
* Consistent order state transitions

---

### 🧠 Systems-Level Optimization

The engine leverages **Rust’s ownership model** to manage order lifecycles without requiring a garbage collector.

Benefits include:

* Deterministic memory management
* Reduced latency spikes
* Improved throughput under heavy load

---

# 🛠 Key Components

The codebase separates **market state** from **execution logic**.

```text
trading_engine_rust/
│
├── matching_engine/
│   ├── orderbook.rs     # Core structures: Order, Limit, OrderBook
│   └── engine.rs        # MatchingEngine managing multiple trading pairs
│
├── main.rs              # CLI entry point for simulation
│
└── README.md
```

### `/matching_engine/orderbook.rs`

Contains core data structures:

* `Order`
* `Limit`
* `OrderBook`

Handles:

* Price level storage
* Volume calculations
* Order matching and filling logic

---

### `/matching_engine/engine.rs`

Defines the **MatchingEngine** responsible for:

* Managing active trading pairs
* Coordinating order matching
* Maintaining market state

---

### `/main.rs`

Application entry point providing a **CLI interface** that allows:

* Real-time market simulation
* Manual order placement
* Testing matching behavior

---

# 💻 Tech Stack & Core Concepts

### Programming Language

* **Rust (100%)**

### Data Structures

* `HashMap`-backed price levels for fast order discovery

### Financial Trading Concepts

* Limit Orders
* Price-Time Priority Matching
* Volume Analysis
* Bid / Ask Spread Simulation

---

# ⚙️ Getting Started

## Prerequisites

Ensure the **Rust toolchain** is installed.

Install Rust if needed:

```bash
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

Verify installation:

```bash
rustc --version
cargo --version
```

---

# 📥 Installation

Clone the repository:

```bash
git clone https://github.com/Muasevim/trading_engine_rust.git
cd trading_engine_rust
```

---

# ▶️ Build and Run

Compile and execute the engine:

```bash
cargo run --release
```

The `--release` flag enables **Rust compiler optimizations**, significantly improving runtime performance and making it suitable for **benchmarking latency and throughput**.

---

# 🧪 Example Use Case

The CLI simulation allows you to:

1. Start the engine
2. Submit **buy/sell limit orders**
3. Observe how the **matching engine executes trades**

Example workflow:

```
Start engine
   ↓
Place BUY order
   ↓
Place SELL order
   ↓
Engine matches orders
   ↓
Trade executed
```

---

# 🗺 Roadmap & Performance Goals

### 🔒 Lock-Free Concurrency

Implement **thread-safe multi-market matching** using:

* `Arc`
* `Mutex`
* Rust concurrent primitives

Goal: support **parallel order matching across markets**.

---

### 📡 FIX Protocol Support

Add compatibility with the **Financial Information eXchange (FIX) protocol**, enabling integration with:

* Trading platforms
* Broker systems
* Market gateways

---

### 🌐 WebAssembly (WASM) Bridge

Compile the engine to **WebAssembly** to enable:

* High-speed trading simulations in the browser
* Integration with the **Bridge SaaS frontend**
* Client-side order book visualization

---

# 📄 License

This project is **open-source** and available under the **MIT License**.
