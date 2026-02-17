---
tags:
  - MUL
aliases:
  - compression
sources:
  - "[[MUL_02_Compression_Techniques.pdf]]"
---
Compression is used in many fields of computer science, but most commonly it is used in [[Sound|sound]], [[Image|image]] and [[Video|video]] compression to reduce file size. Compression is usually hardware accelerated through graphics cards, audio cards, multimedia [[SIMD]] instructions and more.
## Types
There are two main types of compression:
- **Lossless** compression
	- Not as used compression type.
	- Lossless formats include PNG and FLAC.
- **Loss** compression
	- Much more commonly used.
	- Loss formats include JPEG, MPEG, MP3, H.265, DVB-T2 and digital cinema.
These types can be expanded as:
- **Reduction** of redundancy (lossless)
	- The original signal can be reconstructed without distortion.
- **Irelevance** from the human point of view.
	- Removing of any irrelevant data (loss).
	- The original signal cannot be reconstructed without distortion.
## Terms
There are several terms useful in compression, such as:
### Encoding/Decoding
Mutually exclusive assignment of symbols from one [[Alphabet|alphabet]] to another [[Alphabet|alphabet]]. This can for example by `'A' -> 0110`. This is reduction of redundancy and can be done either in [[Software]] (compressor) or in [[Hardware]] ([[Coder|encoder]]). Backwards translation can also be done through either [[Software]] (decompressor) or in [[Hardware]] ([[Decoder|decoder]]).
The type and way of encoding/decoding is decided by the data format, which can have different formats for [[Sound|audio]] and [[Video|video]]. 
#### Variable Length Coding
VLC is a style of coding that uses short codes for commonly occurring symbols and longer once for those that appear less often. This is realized through entropic coding and an example of this is Huffman code.
#### Prefix Code
The main characteristic of prefix codes is that no code (symbol) is a prefix of another code (symbol). During decoding the symbols are unambiguous without dividers.
#### Dictionary
A data structure that contains fragments of the uncompressed file that can then be used to encode or decode the file.
### Data Model
The data model can be either:
- **Probabilistic** (statistic) model
- **Context** (Markov) model
### Compression Methods
Compression method are divided by:
- **Complexity**:
	- Symmetric
	- Asymmetric
- **Symbol Arrangement**:
	- Block
	- Stream
- **Passes**:
	- Single-pass
	- Dual-pass
	- Multi-pass
From these there are groups such as:
- **Static**: single-pass, data model predefined
- **Semi-adaptive**: dual-pass, data model is needed to be transferred
- **Adaptive**: single-pass, data model is modified during runtime
Another way of dividing compression methods is as:
- **Static**
- **Context**
- **Dictionary**
Final way of dividing compression methods is:
- **Predictive** (predictor, error)
- **Transformative** (DCT)
### Compression Ration
A simple metric of $\frac{\text{input size}}{output size}$ that says how well the target file has been compressed. Any results under $1$ are compression, while results above $1$ are expansion.
### Compression Evaluation
Compression is evaluated based on these characteristics:
- Effectivity (compression ration)
- [[Time and Space Complexity]]
- Influence of the data type on the compression ration
- In loss compression how much is the quality degraded
- Interaction between quality and compression ration (Rate-Distortion curve)
### Data Entropy
Data entropy is a variable that say the amount of information, information contents, how many bits are necessary. It can be interpreted as the amount of yes/no question, through which the contents of the file can be revealed.
The basic unit is bit and the entropy can be calculated as:
$$H = - \sum_{a\in A}p(a)\log_{2}(p(a))$$
Entropy encoders compress data nearly optimally in relation to their entropy.
### Multi-Dimensional Data
There are several way of walking through and compressing multi-dimensional data, such as pictures, spaces, arrays, etc:
- **Raster Pass** (by rows)
- **Zig-Zag** (by rows diagonally) such as DCT in JPEG
- **Morton's Pass** (Z-curves)
### Artefacts
Compression, especially loss compression, can create artefacts, which are out of place visual or audio things that are caused by the compression and are usually undesired.