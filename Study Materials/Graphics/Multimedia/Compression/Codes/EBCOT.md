---
tags:
  - MUL
aliases:
  - ebcot
sources:
  - "[[MUL_07_Image_Formats.pdf]]"
---
An image [[Compression|compression]] algorithm used in [[JPEG2000]].
## Encoding
The algorithm goes through the image in three passes and takes in blocks of either $32 \times 32$ or $64 \times 64$ pixels. 
- The bite alignment goes from [[MSB]] to [[LSB]]. 
- The algorithm goes through the block in sections, where:
	- The pixels are encoded in blocks of 4 high strips.
	- The algorithm goes through 4 pixels strips and then returns back up for the next column.
	- At the end of the row the algorithm goes back to the front and down 4 pixels.
- The three passes are:
	- Propagation of significance
	- Setting of magnitude
	- Clean-up