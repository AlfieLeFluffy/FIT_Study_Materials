---
tags:
  - MUL
aliases:
  - jpeg
sources:
  - "[[MUL_07_Image_Formats.pdf]]"
---
An [[Image|image]] format using loss or lossless [[Compression|compression]]. The name JPEG is truly accurate as that is the *Joint Photographic Experts Group* that create the format and the format itself is called JFIF or Exif with the standard [[International Organization for Standardization|ISO]]/[[IEC]] 10918-1.
## Characteristics
Some of the basic characteristics are:
- Loss/lossless [[Compression|compression]]
- Sequence and progressive transmission
- Defined JIF
- Baseline:
	- Blocks of $8\times 8$ pixels
	- 8 bit
	- [[Huffman Encoding|Huffman encoding]] with 2AC + 2DC
- Extended:
	- 8 + 12 bits
	- 4AC + 4DC
## Encoding
The base pipeline for encoding is:
1. Image is split into blocks of $8 \times 8$ pixels.
2. Each block is converted through [[DCT]]
3. Each block is quantized through a quantization table
4. Each block is run through [[Run-Length Encoding|run-length encoding]]
5. Each block is encoded through [[Huffman Encoding|Huffman encoding]] with a predefined table of codes
6. Output is a compressed data stream
The input image is within the [[YCbCr]] color space, the samples can be down-sampled to 4:2:2 or 4:2:0. The edges of where blocks would not make a full $8 \times 8$ the image is extended. The basic expected output from the DCT is 1 DC + 63 AC.