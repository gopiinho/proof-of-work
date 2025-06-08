# WETH Basics

WETH is essentially a standard ERC-20 token which mimics ETH 1:1. Since ETH is not ERC-20 compliant, instead WETH is used in dApps that require ERC20 tokens.

## 🧱 Basics of a WETH Contract

### Purpose

- Wraps native ETH into an ERC-20 token so it can be used to interact with other Defi protocols and smart contracts requiring ERC-20 tokens.

### Backing

- Each 1 WETH token is backed up by exactly 1 ETH held inside the contract.
- The amount of ETH held in the contract should never be lesser or more than the total supply of WETH.

### Deposit

- User deposits x amount of ETH into the contract using `deposit` function.
- The contract mints x amount of WETH and assigns it to users token balance.

### Withdraw

- User calls `withdraw` with x amount of WETH.
- Contract burns that x amount of WETH and sends x amount of ETH to the user.
