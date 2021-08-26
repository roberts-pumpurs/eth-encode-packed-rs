# Ethereum abi.encodePacked() in Rust

This project allows data serialization and packing in Rust as it's being done in Solidity with abi.encodePacked()

## Example usage

```rust
// this is supposed to be uint24 variable in solidity
let input = vec![SolidityDataType::NumberWithShift(U256::from(4001), TakeLastXBytes(24))];
let (bytes, hash) = abi::encode_packed(&input);
let hash = format!("0x{:}", hash);
let expected = "0x000fa1";
assert_eq!(hash, expected);
```
