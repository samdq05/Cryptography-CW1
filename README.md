# Cryptography Coursework 1 — 2026

This repository contains my solution to **Coursework 1 (2026)** for a university mathematics module. The coursework explores the implementation and analysis of the **Vigenère cipher** and its use in **Cipher Block Chaining (CBC) mode**, using Python and NumPy.

## Contents

The coursework is implemented in the accompanying Jupyter Notebook:

- `Coursework 1 2026.ipynb`

The notebook contains solutions to three main questions.

### Question 1 — Vigenère Cipher

The first section introduces the Vigenère cipher using vectors over integers modulo 32.

It covers:

- Converting between strings and NumPy integer arrays
- Component-wise modular arithmetic
- Vigenère encryption
- Constructing and applying a Vigenère decryption key
- Verification of encryption and decryption

The character encoding used is:

```text
A → 0, B → 1, ..., Z → 25, [ → 26, ..., ` → 31
```

The Vigenère encryption operation is

\[
E_k(b) = (k+b)\pmod{32}.
\]

### Question 2 — Cipher Block Chaining

The second section extends the Vigenère cipher to **CBC mode**.

It covers:

- Bitwise XOR operations using NumPy
- CBC encryption
- CBC decryption
- Construction of a Vigenère decryption key
- Recovery of plaintext from ciphertext blocks
- The role of the initialisation vector (IV)

For plaintext blocks \(b_i\) and ciphertext blocks \(c_i\), encryption follows

\[
c_i = E_k(b_i \oplus c_{i-1}),
\]

where \(c_0\) is the initialisation vector.

Decryption therefore uses

\[
b_i = c_{i-1} \oplus D_k(c_i).
\]

### Question 3 — Recovering Unknown Parameters

The final section considers a Vigenère-CBC system where both the **encryption key** and **initialisation vector** are initially unknown.

Using known plaintext/ciphertext pairs, the notebook demonstrates how to recover:

- The initialisation vector
- The Vigenère encryption key

The recovered values are then converted back into their string representations.

## Requirements

The coursework was completed using:

- **Python**
- **NumPy**
- **Jupyter Notebook**

Only NumPy is required by the coursework implementation.

No external cryptography libraries are used.

## Running the Notebook

The notebook can be opened and executed using Jupyter Notebook or JupyterLab.

Install NumPy if necessary:

```bash
pip install numpy
```

Then launch Jupyter:

```bash
jupyter notebook
```

Run the notebook cells in order.

## Key Concepts

The coursework provides practical implementation of several fundamental cryptography concepts:

- Modular arithmetic
- Vectorised operations with NumPy
- Substitution/additive ciphers
- Vigenère encryption and decryption
- XOR operations
- Cipher Block Chaining (CBC)
- Initialisation vectors
- Known-plaintext attacks
- Recovery of cryptographic parameters

## Notes

This repository contains coursework completed as part of a university mathematics module. The implementation is intended for **educational purposes** and should not be considered a secure implementation of a modern cryptographic system.

The Vigenère cipher used here operates modulo 32 with fixed-length blocks and is substantially simpler than modern cryptographic algorithms.
