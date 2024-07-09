# MToken

MToken is an ERC20 token contract that allows the owner to mint tokens and any user to burn tokens. The contract uses OpenZeppelin's ERC20 and Ownable implementations to ensure security and best practices.

## Features

- ERC20 standard token
- Minting by the contract owner
- Burning by any user
- Token name and symbol set during deployment

## Constructor

### parameters
* name: The name of the token (e.g., "MToken").
* symbol: The symbol of the token (e.g., "MTK").

### Work
* Calls the constructor of the ERC20 base contract with the provided name and symbol.
* Mints 100 tokens to the deployer's address (msg.sender)

```solidity
constructor(string memory name, string memory symbol) ERC20(name, symbol) {
    // Mint 100 tokens to msg.sender
    // 1 token = 1 * (10 ** decimals())
    _mint(msg.sender, 100 * 10**decimals());
}
```
## Functions

### `mint(address to, uint256 amount)`

Allows the owner to mint new tokens.

- **Parameters**:
  - `to`: The address to which the minted tokens will be sent.
  - `amount`: The number of tokens to mint (in wei).
- **Access Control**: Can only be called by the contract owner.

### `burn(uint256 amount)`

Allows any user to burn their own tokens.

- **Parameters**:
  - `amount`: The number of tokens to burn (in wei).
- **Access Control**: Can be called by any user.

### `getOwner()`

Returns the address of the contract owner.

- **Returns**: The address of the owner.
- **Access Control**: Public function, can be called by anyone.

## Usage

1. **Mint Tokens**: The owner can mint tokens by calling the `mint` function with the recipient address and the amount to be minted.
2. **Burn Tokens**: Any user can burn their own tokens by calling the `burn` function with the amount to be burned.
3. **Check Owner**: Anyone can check the owner of the contract by calling the `getOwner` function.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
