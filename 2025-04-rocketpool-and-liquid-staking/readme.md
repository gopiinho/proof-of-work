# RocketPool rETH and Liquid Staking

## **What is rocket pool ?**

RocketPool is a decentralized ETH staking protocol allowing validators and stakers to stake their ETH.

## **Why use rocket pool ?**

Because running a validator node requires

- 32 ETH
- Technical knowledge

So rocket pools allows multiple stakers to stake their ETH using rocket pool contracts without needing full 32 ETH or technical knowledge.

## What is rETH ?

rETH us a token issued by rocket pool upon staking your ETH.

It is not necessarily 1:1 to ETH, since its a yield bearing token and is usually more valuable than ETH, currently trading for 1 ETH = 0.88 rETH

ETH/rETH = Amount of ETH backed by 1 rETH

To acquire rETH we can directly stake with its contracts or buy from secondary markets like, uniswap, curve.

rETH is a rebase token.

## **Rebase vs non-rebase token**

### **Rebase**

Rebase token is a token which supply is based on a algorithm, for ex. Lido with its **stETH**

For example a user deposits 10 ETH and gets 10 stETH in return.
After X amount of time their stETH holdings become 11 without any interactions since its a rebase token and they will be able to exchange that 11 stETH > 11 ETH.

This is because their ETH acquired staking rewards which they receive in form of their stETH increasing in supply.

**Token supply and balances change algorithmically over time without user interaction**

### **Non-rebase**

A non-rebase tokens total supply does not dependent on an algorithm but rather events such as mint / burn.

For example a user deposits 10 ETH and gets 10 rETH in return.
After that X amount of time after accumulating their staking rewards they will be able to exchange their 10 rETH > 11 ETH since its a yield bearing token that accrues value.

**ETH/rETH = Amount of ETH backed by 1 rETH**

## **Mint / Burn**

The process of burning and minting rETH utilizes 3 major contracts:

- RocketDepositPool
- RocketStorage
- RocketTokenRETH

**RocketDepositPool**: The contract there ETH is initially sent to, and is responsible for making external contract calls to **RocketStorage** to check if deposits are enabled and then lastly mints rETH through **RocketTokenRETH** and then is sent to the user.

**RocketStorage**: The database of the protocol, holds the persistent storage.

**RocketTokenRETH**: The ERC20 that is minted upon deposit of ETH.

## rETH / ETH Exchange Rate

To calculate how much 1 rETH is worth in ETH we have this mathematical equation.

ETH = (rETH / rETH supply) \* ETH Supply

E = Total ETH deposited in protocol
R = Total rETH supply

r = rETH amount

e = ETH amount

e = ( r / R ) \* E

**Example:**

R = 2500

E = 3000

How much ETH will a user get per 1 rETH burned ?

e = ( 1 / 2500 ) \* 3000

e = 0.0004 \* 3000

e = 1.2

Hence, if total **rETH** supply minted is 2500 and total **ETH** deposited is 3000, then a user will get in return 1.2 **ETH** every 1 **rETH** they burn.

**How much rETH will a user get per 1 ETH deposited ?**

Here our equation is r = ( e \* R ) / E

r = ( 1 \* 2500 ) / 3000

r = 2500 / 3000

r = **0.8333**
