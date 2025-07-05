# EIP-1153 Transient Storage

Introduces two new opcodes `TSTORE` and `TLOAD` .

### **What is it?**

**Transient Storage:** Unlike `Storage` which persists on blockchain, transient storage’s lifespan is only until the end of a current transaction. It is cleared at the end of the top-level transaction.

### **Why use it?**

**Lower Gas Cost:** The primary benefit, since we not constantly updating permanent storage onchain, which is the most expensive EVM function, the gas costs are much lower. Transient storage are more akin to memory operations in terms of gas costs.

**Automatic Reset:** Since transient storage is cleared at the end of the transaction, there's no risk of a variable remaining "locked" across separate transactions, even if a previous transaction reverted mid-execution. This provides a clean slate for each new transaction.
