# Gas Optimization

## Variable Packing

Solidity has 32 byte (256bit) storage slots. When we fit in multiple variables in a single slot, its called variable packing.

**Why ?**

Because each storage slot costs gas, so when possible its important to fit in variables together in other to save gas.

If we pack in a variable that exceeds this 32 byte in current slot then it gets stored in a new one.

### **Example**

Unpacked Variables:

```jsx
uint256 x = 3;     //slot 0
uint256 y = 33;    //slot 1
uint256 z = 333;   //slot 2
```

Here x, y and z uses 3 - 32 byte slots which means 3x the storage cost!

More slots = More gas.

Packed Variables:

```jsx
uint8 x = 3;     //slot 0
uint8 x = 33;    //slot 0
uint16 x = 333;  //slot 0
```

In this packed example - x, y and z all 3 uses the same storage slot.

### SSTORE

SSTORE is one of most expensive EVM operations because it modifies the state of the blockchain.

In case of a single function updating all 3 packed variables:

1. Reads slot 0 once
2. Performs **only one SSTORE** at the end of the function execution

```jsx
function updateAll() external {
    x = 4;    // First write to slot 0
    y = 44;   // Second write to slot 0
    z = 444;  // Third write to slot 0
}
```

The EVM automatically combines multiple updates to the same slot into a single SSTORE operation (~20K gas once vs multiple times in case of unpacked variables).
