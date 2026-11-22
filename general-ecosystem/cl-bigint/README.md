# cl-bigint: Pure Cluster Arbitrary-Precision Integer Arithmetic

> **Author**: zk-mohammad <ZaidKhan-alamgir@proton.me>  
> **License**: CCFL v2.0  
> **Repository**: `modules/cl-bigint`  

A 100% pure Cluster implementation of arbitrary-precision integer arithmetic (BigInt) capable of handling numbers with thousands of decimal digits without 64-bit integer overflow.

Zero `cpp_inject`, zero `extern "C"`, zero external dependencies.

## Features
- **Unbounded Integer Precision**: Digits dynamically sized in a pure Cluster vector.
- **Full Signed Arithmetic**: Native support for positive and negative numbers.
- **Elementary Operations**: High-performance addition with carry, subtraction with borrow, and grade-school convolution multiplication.
- **Binary Exponentiation**: `bigint_pow` computes large exponential powers (e.g. $2^{64}$, $2^{256}$) in $O(\log n)$ time.

## Quickstart

```cluster
import "cl-bigint/bigint.zk"

fn main():
    two := bigint_from_int(2)
    p64 := bigint_pow(two, 64) // 18446744073709551616
    print("2^64 = " + bigint_to_string(p64))
```
