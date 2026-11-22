# cl-blake3

High-Performance Pure Cluster BLAKE3 Cryptographic Tree Hash Engine.

Part of the Cluster Standard Module Ecosystem.
Managed under CCFL v2.0 copyright stewardship by Mohammad Zaid / cluster. Contributor: `zk-mohammad <ZaidKhan-alamgir@proton.me>`.

## Features
- **100% Pure Cluster**: Zero `cpp_inject`, zero `extern "C"`, zero unsafe dependencies.
- **Full BLAKE3 Tree Architecture**: Supports arbitrary length data streams with dynamic 1024-byte chunk decomposition and binary tree reduction.
- **Cryptographic Speed**: Optimized 7-round permutation with safe 32-bit right-rotation arithmetic.
- **NIST / Official Test Suite Verified**: Tested against official BLAKE3 test vectors for empty strings, single blocks, and multi-chunk trees.

## Usage
```cluster
import "cl-blake3/blake3.zk"

fn main():
    // Hash a string
    digest := blake3("Hello Cluster!")
    print("BLAKE3: " + digest)

    // Hash raw byte vector
    bytes: vector[int] := [0, 1, 2, 3, 4]
    hash_hex := blake3_hash_bytes(bytes)
    print("Hash: " + hash_hex)
```

## License
CCFL-2.0
