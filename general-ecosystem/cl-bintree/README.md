# cl-bintree: Pure Cluster Binary Search Tree Container

> **Author**: zk-mohammad <ZaidKhan-alamgir@proton.me>  
> **License**: CCFL v2.0  
> **Repository**: `modules/cl-bintree`  

A 100% pure Cluster implementation of a Binary Search Tree (BST) container using a flat arena-allocated node vector.

Zero `cpp_inject`, zero `extern "C"`, zero raw pointer memory hazards.

## Features
- **Flat Arena Allocation**: Cache-friendly vector allocation avoids pointer overhead and fragmentation.
- **Logarithmic Search & Insert**: $O(\log n)$ average time complexity.
- **Iterative In-Order Traversal**: Generates a sorted vector in $O(n)$ time without stack overflow risk.
- **Min/Max Discovery**: Fast extreme element queries.

## Quickstart

```cluster
import "cl-bintree/bintree.zk"

fn main():
    t := bintree_new()
    bintree_insert(t, 50)
    bintree_insert(t, 25)
    bintree_insert(t, 75)

    has_25 := bintree_contains(t, 25) // true
    sorted := bintree_inorder(t)       // [25, 50, 75]
```
