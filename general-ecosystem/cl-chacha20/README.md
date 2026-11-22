# cl-chacha20

High-Performance Pure Cluster RFC 8439 ChaCha20 Stream Cipher.

Part of the Cluster Standard Module Ecosystem.
Managed under CCFL v2.0 copyright stewardship by Mohammad Zaid / cluster. Contributor: `zk-mohammad <ZaidKhan-alamgir@proton.me>`.

## Features
- **100% Pure Cluster**: Zero `cpp_inject`, zero `extern "C"`, zero unsafe dependencies.
- **IETF RFC 8439 Compliant**: 256-bit key, 96-bit nonce, 32-bit counter, 20 rounds (10 column + 10 diagonal).
- **Verified Against RFC Test Vectors**: Exact match with Section 2.3.2 block function keystream and Section 2.4.2 encryption/decryption.
- **High-Throughput Streaming**: Arbitrary length streaming encryption and decryption with byte-aligned keystream masking.

## Usage
```cluster
import "cl-chacha20/chacha20.zk"

fn main():
    // 32-byte key
    key: vector[int] := []
    // 12-byte nonce
    nonce: vector[int] := []
    counter := 1

    plaintext := "Confidential message for Cluster network"
    cipher_bytes := chacha20_encrypt_string(key, counter, nonce, plaintext)
    cipher_hex := chacha20_bytes_to_hex(cipher_bytes)
    print("Ciphertext: " + cipher_hex)

    decrypted := chacha20_decrypt_string(key, counter, nonce, cipher_bytes)
    print("Restored: " + decrypted)
```

## License
CCFL-2.0
