# UBPE Tokenizer

> [![PyPI - Version](https://img.shields.io/pypi/v/ubpe?style=flat)](https://pypi.org/project/ubpe/)
[![GitHub License](https://img.shields.io/github/license/Scurrra/ubpe?style=flat)](https://github.com/Scurrra/ubpe/tree/master?tab=MIT-1-ov-file)


> UBPE -- Universal Byte-Pair Encoding. Universal means that it works not only with strings, but with general sequences too.

The package provides Universal Byte-Pair Encoding tokenizers:
 - `UBPEClassic` -- *optimized* version of classic BPE algorithm
 - `UBPE` -- novel approach to BPE tokenization which allows you to choose between multiple different variants of encodings according to scores of tf-idf metric or something else; the most optimal encoding from this implementation was *shorter* than the encoding from classic implementation

## Guides and theory
 - [Description of tokenizer fitting algorithms](https://scurrra.github.io/blog/ubpe-tokenizers-i/)
 - [Description of encoding and decoding algorithms for classic and novel approaches](https://scurrra.github.io/blog/ubpe-tokenizers-ii/)
 - [Google Colab Demo for `ubpe v0.2` (with precomputed cells)](https://colab.research.google.com/drive/1QhQZlgggwtWByEWOwLcoWV37UgOA8VCI?usp=sharing)
 - [Google Colab Demo for `ubpe v0.3` (with precomputed cells)](https://colab.research.google.com/drive/1kp6lQtsI0mLdX54ASkuaiz4SqhOK6TKh?usp=sharing)

## Roadmap
 - [x] Python native implementation
 - [x] Cython implementation with C++ backend
   - [ ] Publish standalone C++ library (it is already usable)
   - [ ] Other types than `uint32_t` as inner token type
 - [ ] Rust backend with standalone package
 - [x] Subdocument tokenization (since v0.3)
   - [x] RegEx support
   - [x] Support for known word tokens in alphabet
   - [x] Ignored tokens
 - [ ] Collaborative training
   - [ ] Training checkpoints
   - [ ] Training on large datasets 
   - [ ] Training on splitted datasets
 - [ ] Other Features:
   - [ ] One token -- Many subsequences
   - [ ] Spelling correction support
   - [ ] Vocabulary pruning
 - [ ] Examples:
   - [x] Demo with visualizaton of pros of the UBPE novel algorithm
   - [x] Subdocument tokenization example
  
## Installation

It is planned to deliver different implementations for the algorithm, so the package is divided into general import package (this one), and implementations (for now, Python native and Cython with C++20 backend). To install use:

```bash
pip install ubpe[native]
```

Or,

```bash
pip install ubpe[cython]
```

> [!NOTE]
> Starting with version 0.3, the C++ backend has become faster while the native one has become slower, so there's no reason to use the native backend except for educational purposes.

> [!NOTE]
> While Google Colab is supported, interactive logging doesn't work in it due to complications with redirecting stderr to the cell output.

> [!WARNING]
> Encoding candidates from different backends of the novel tokenizer (`UBPE`) may differ in order, i.e. two encodings with the same length and weight may be returned in different ordered, but are still valid.

## Bug reports

If you find a bug that occurs under certain circumstances in some tests, please report it.

## Contribution

Bugfixes and optimizations are welcomed!

P.S. if you are working at Hugging Face or OpenAI, you can write me and hire me. Please.
