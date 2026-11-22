# cl-base58: Pure Cluster Base58 & Base58Check Engine

> **Author**: zk-mohammad <ZaidKhan-alamgir@proton.me>  
> **License**: CCFL v2.0  
> **Repository**: `modules/cl-base58`  

A 100% pure Cluster implementation of the Base58 binary-to-text encoding algorithm used in Bitcoin, IPFS, and decentralized protocols.

Zero `cpp_inject`, zero `extern "C"`, zero external dependencies.

## Features
- **Standard Alphabet**: Uses the human-friendly 58-character alphabet excluding ambiguous symbols (`0`, `O`, `I`, `l`).
- **Leading Zero Preservation**: Maps each leading `0x00` byte strictly to `'1'`.
- **String & Byte Vector APIs**: Encode and decode raw binary byte arrays or UTF-8 strings.

## Quickstart

```cluster
import "cl-base58/base58.zk"

fn main():
    encoded := base58_encode("Hello World") // "JxF12TrwUP45BMd"
    decoded := base58_decode(encoded)       // "Hello World"
```
