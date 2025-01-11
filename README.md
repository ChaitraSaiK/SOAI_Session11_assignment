# Byte Pair Encoding (BPE) Compression Implementation

[![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=flat&logo=PyTorch&logoColor=white)](https://pytorch.org/)
[![Lightning](https://img.shields.io/badge/-Lightning-792ee5?logo=lightning&logoColor=white)](https://www.pytorchlightning.ai/)
[![DVC](https://img.shields.io/badge/DVC-Data%20Version%20Control-945DD6?logo=dvc)](https://dvc.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com)

This repository contains an implementation of Byte Pair Encoding (BPE) for Telugu text encoding. It works by iteratively merging the most frequent pairs of adjacent symbols (characters or tokens) in the text into a single new symbol. This process is repeated until a desired vocabulary size or compression goal is achieved. The compression ratio achieved in this example is approximately 3.91X.

# Features
Text Cleaning: Removes special characters, extra whitespace, punctuation, and digits from the input texts.

Tokenization: Converts the cleaned text into UTF-8 encoded byte tokens.

Byte Pair Encoding (BPE): Iteratively merges the most frequent token pairs into new tokens to reduce the dataset size.

Compression Statistics: Reports the compression ratio and token count before and after applying BPE.

# How It Works

Text Cleaning:

- Special characters (\r, \n, \xa0) are replaced with spaces.

- Punctuation and digits are removed.

- Multiple spaces are collapsed into a single space.

Tokenization:

- Each cleaned text is encoded into a sequence of UTF-8 byte tokens.

- These tokens are stored as integers for processing.

BPE Training:

- A vocabulary size is set (in this example, 350 tokens).

- The algorithm iteratively merges the most frequent pairs of tokens.

- Each new merge is assigned a unique token ID starting from 256.

Merge Process:

- The merge() function replaces occurrences of a token pair with a new token ID in the token sequence.

Compression Statistics:

- The script calculates the compression ratio based on the lengths of the original and compressed token sequences.

Results

- The script demonstrates the compression capabilities of BPE with the following results:

Original tokens length: 12,326
Compressed tokens length: 3,156
Compression ratio: 3.91X