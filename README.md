# UBPE Tokenizer

> UBPE -- Universal Byte-Pair Encoding. Universal means that it works not only with strings, but with general sequences too.

The package provides Universal Byte-Pair Encoding tokenizers:
 - `UBPEClassic` -- *optimized* version of classic BPE algorithm
 - `UBPE` -- novel approach to BPE tokenization which allows you to choose between multiple different variants of encodings according to scores of tf-idf metric or something else; the most optimal encoding from this implementation was *shorter* than the encoding from classic implementation

## Guides and theory
 - [Description of tokenizer fitting algorithms](https://scurrra.github.io/blog/ubpe-tokenizers-i/)
 - [Description of encoding and decoding algorithms for classic and novel approaches](https://scurrra.github.io/blog/ubpe-tokenizers-ii/)
 - [Google Colab Demo (with precomputed cells)](https://colab.research.google.com/drive/1QhQZlgggwtWByEWOwLcoWV37UgOA8VCI?usp=sharing)

## Roadmap
 - [x] Python native implementation
 - [x] Cython implementation with C++ backend
   - [ ] Publish standalone C++ library (it is already usable)
   - [ ] Other types than `uint32_t` as inner token type
 - [ ] Rust backend with standalone package
 - [ ] Subdocument tokenization
   - [ ] RegEx support
   - [ ] Support for known word tokens in alphabet
   - [ ] Ignored tokens
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
   - [ ] Subdocument tokenization example
  
## Installation

It is planned to deliver different implementations for the algorithm, so the package is divided into general import package (this one), and implementations (for now, Python native and Cython with C++20 backend). To install use:

```bash
pip install ubpe[native]
```

Or,

```bash
pip install ubpe[cython]
```

## Bug reports

If you find a bug that occurs under certain circumstances in some tests, please report it.

## Contribution

Bugfixes and optimizations are welcomed!

P.S. if you are working at Hugging Face, you can write me and hire me. Please. 