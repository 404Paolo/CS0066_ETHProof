# MyToken Smart Contract

A simple Ethereum-based token smart contract written in Solidity.

## Features
- Public variables to store token details:
  - **Token Name**: `LebronCoin`
  - **Token Symbol**: `LBC`
  - **Total Supply**: Tracks the total number of tokens in circulation.

- A **mapping** to track the balance of each address.

- Functions to:
  - **Mint tokens**: Increase the total supply and the balance of a specific address.
  - **Burn tokens**: Decrease the total supply and the balance of a specific address with validation.

---

## Contract Details

### Public Variables
- **`name`**: The name of the token, "LebronCoin".
- **`symbol`**: The token symbol, "LBC".
- **`total`**: The total supply of tokens, initially set to `0`.

### Mappings
- **`balance`**: A mapping of addresses to their respective token balances.

---

## Functions

### 1. `increaseSupply`
- **Description**: Mints new tokens to a specific address.
- **Parameters**:
  - `receiver` (address): The address to receive the tokens.
  - `supply` (uint64): The number of tokens to mint.
- **Effects**:
  - Increases `total` by `supply`.
  - Adds `supply` to the `receiver`'s balance.

### 2. `burnSupply`
- **Description**: Burns tokens from a specific address.
- **Parameters**:
  - `holder` (address): The address to burn tokens from.
  - `amount` (uint64): The number of tokens to burn.
- **Conditions**:
  - The `holder`'s balance must be greater than or equal to the `amount`.
- **Effects**:
  - Decreases `total` by `amount`.
  - Subtracts `amount` from the `holder`'s balance.

---

## Usage Example

1. **Minting Tokens**
   ```solidity
   increaseSupply(0xYourAddress, 100);
