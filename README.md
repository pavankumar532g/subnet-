
## Overview

This repository contains two core smart contracts:

1. **ERC20 Contract**: Implements the ERC20 standard for creating and managing fungible tokens on the Ethereum blockchain.
2. **Vault Contract**: A secure storage mechanism that allows users to deposit and withdraw ERC20 tokens, often used in DeFi applications.

These contracts are designed for flexibility, security, and ease of integration with decentralized applications.

---

## Contracts

### 1. **ERC20 Contract**
The ERC20 contract provides a standard interface for fungible tokens, enabling seamless interaction with wallets, exchanges, and other smart contracts.

**Features**:
- Token creation with customizable name, symbol, and initial supply.
- Standard ERC20 functions: `transfer`, `approve`, `transferFrom`, `allowance`, and `balanceOf`.
- Events: `Transfer` and `Approval` for tracking transactions and approvals.
- Optional minting and burning functions (if enabled).

**Usage**:
1. Deploy the contract by specifying:
   - `name`: The name of the token (e.g., MyToken).
   - `symbol`: The token symbol (e.g., MTK).
   - `initialSupply`: The total number of tokens created at deployment.
2. Interact using the ERC20 interface.

**Example Deployment**:
```solidity
ERC20 myToken = new ERC20("MyToken", "MTK", 1000000);
```

---

### 2. **Vault Contract**
The Vault contract securely manages deposits and withdrawals of ERC20 tokens. This is ideal for applications such as staking, lending, or holding collateral.

**Features**:
- Deposit functionality for storing ERC20 tokens.
- Withdrawal functionality with optional access controls.
- Balance tracking for each depositor.
- Integration with any ERC20-compliant token.

**Usage**:
1. Deploy the Vault contract.
2. Configure it to accept deposits of a specific ERC20 token.
3. Users can deposit tokens by calling the `deposit` function and withdraw their balance using `withdraw`.

**Example Flow**:
- **Deposit**:
  ```solidity
  vault.deposit(tokenAddress, amount);
  ```
- **Withdraw**:
  ```solidity
  vault.withdraw(amount);
  ```
---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
