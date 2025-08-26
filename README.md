# 🔗 Python Blockchain Exchange

> **A fully functional blockchain exchange built in Python** — from hashing algorithms to block validation, this project brings blockchain theory to life with an interactive, educational twist.

---

## 📚 What is a Blockchain?

A **blockchain** is a distributed ledger that stores data in a chain of **blocks**.
Each block contains:

* 📄 **Data** — transactions or information to be recorded
* ⏱ **Timestamp** — when the block was created
* 🔑 **Hash** — a unique digital fingerprint for the block
* 🔗 **Previous Hash** — connects this block to the one before it

Once a block is added to the chain, it’s **immutable** — changing it would break every block after it.

**Why is blockchain secure?**

1. **Cryptographic Hashing** — SHA-256 ensures every block has a unique, tamper-evident signature.
2. **Consensus Mechanisms** — nodes agree on the blockchain’s state (e.g., Proof of Work, Proof of Stake).
3. **Decentralization** — multiple copies exist across the network, making it resistant to single-point failure.

Here’s a visual:

```
[ Block #1 ] → [ Block #2 ] → [ Block #3 ]
   Hash: A1       Hash: B2       Hash: C3
Prev: None     Prev: A1       Prev: B2
```

---

## ⚙️ How I Implemented It in Python

This project started with **Codecademy’s "Learn the Basics of Blockchain with Python"** and expanded into a more interactive **exchange simulation**.

### 🧩 Core Features

* **Block & Blockchain Classes**

  * `Block`: stores transactions, timestamp, hash, and previous hash
  * `Blockchain`: manages the chain, adds blocks, and verifies integrity
* **Hashing with SHA-256**

  * Creates secure, unique identifiers for each block
* **Chain Verification**

  * Detects tampering by checking hash consistency
* **Exchange Simulation**

  * Users can "buy" and "sell" tokens in a simulated blockchain marketplace
* **Interactive Console Output**

  * Color-coded logs for mining, transaction recording, and chain validation

---

## 🖥 Sample Code Snippet

```python
class Block:
    def __init__(self, index, timestamp, data, previous_hash):
        self.index = index
        self.timestamp = timestamp
        self.data = data
        self.previous_hash = previous_hash
        self.hash = self.calculate_hash()

    def calculate_hash(self):
        import hashlib, json
        block_string = json.dumps(self.__dict__, sort_keys=True)
        return hashlib.sha256(block_string.encode()).hexdigest()

class Blockchain:
    def __init__(self):
        self.chain = [self.create_genesis_block()]

    def create_genesis_block(self):
        return Block(0, "2025-08-26", "Genesis Block", "0")

    def add_block(self, new_block):
        new_block.previous_hash = self.chain[-1].hash
        new_block.hash = new_block.calculate_hash()
        self.chain.append(new_block)
```

---

## 🎨 Interactive & Visual Output

* 🟩 **Green** = Block successfully mined
* 🔴 **Red** = Blockchain tampering detected
* 📊 **Transaction History** displayed in a tabular format in console

---

## 🚀 How to Run Locally

```bash
# Clone the repo
git clone https://github.com/yourusername/python-blockchain-exchange.git

# Enter directory
cd python-blockchain-exchange

# Run the blockchain exchange
python main.py
```

---

## 🛠 Tech Stack

* **Language**: Python 3.x
* **Libraries**: `hashlib`, `json`, `datetime`, `colorama` (for colorful output)
* **Concepts**: Blockchain architecture, SHA-256 hashing, transaction validation

---

## 📈 Future Improvements

* Implement **Proof of Work**
* Add **real-time transaction visualization**
* Create a **web-based UI** for block exploration
* Multi-user support with a peer-to-peer network simulation

---

## 📷 Screenshots

*(Add GIFs or images showing your blockchain in action here)*
