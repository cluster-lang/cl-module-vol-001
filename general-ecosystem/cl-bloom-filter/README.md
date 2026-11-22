# cl-bloom-filter: Pure Cluster Probabilistic Bloom Filter

> **Author**: zk-mohammad <ZaidKhan-alamgir@proton.me>  
> **License**: CCFL v2.0  
> **Repository**: `modules/cl-bloom-filter`  

A 100% pure Cluster implementation of a Space-Efficient Probabilistic Bloom Filter.

Zero `cpp_inject`, zero `extern "C"`, zero external dependencies.

## Features
- **Zero False Negatives**: Guaranteed mathematical guarantee that added elements will always return `true`.
- **Kirsch-Mitzenmacher Double-Hashing**: Derives $k$ independent hash probes from two base hash functions (FNV-1a & DJB2).
- **Bit-Packed Storage**: High-density 30-bit word array minimizing memory footprint.
- **Configurable Capacity**: Custom bit sizes and hash count for tuned false-positive rates.

## Quickstart

```cluster
import "cl-bloom-filter/bloom_filter.zk"

fn main():
    bf := bloom_new(2048, 4) // 2048 bits, 4 hash functions
    bloom_add(bf, "user_alice")
    bloom_add(bf, "user_bob")

    has_alice := bloom_contains(bf, "user_alice") // true
    has_eve   := bloom_contains(bf, "user_eve")   // false
```
