# Rust: Undefined Behavior with Raw Pointers and Vector Reallocation

This repository demonstrates a common pitfall in Rust involving undefined behavior when using raw pointers with vectors that undergo reallocation.  The `bug.rs` file contains code that attempts to modify a vector through a raw pointer after the vector's capacity has been exceeded, resulting in unpredictable behavior. The `bugSolution.rs` file presents a corrected version that avoids this issue. 

**Problem:**

Directly manipulating vector data using raw pointers without proper precautions leads to undefined behavior when the vector needs to reallocate memory.  Once the vector's capacity is reached and it reallocates to a new memory location, the previously obtained raw pointer becomes invalid.

**Solution:**

The correct approach is to avoid directly using raw pointers. Rust's ownership and borrowing system is designed to handle memory management safely. Use safe methods like indexing or iterators to access and modify vector elements.

This example highlights the importance of understanding memory management in Rust and adhering to safe programming practices. Always prefer safe, higher-level constructs over using raw pointers unless absolutely necessary and you understand the implications.