---
tags:
  - ZPO
aliases:
  - CMOS sensor
  - CMOS sensors
  - complementary metal-oxide-semiconductor sensor
sources:
  - "[[ZPO_02_Image_Capturing.pdf]]"
---
A more modern and complex sensor architecture when compared to [[Charge-Coupled Device Sensor|CCD sensor]] used for [[Image Capturing|image capturing]].
## Princip
The main idea/princip of a CMOS sensor, when compared to [[Charge-Coupled Device Sensor|CCD sensors]] is that each pixel is addressable. Instead of have each photosensitive flat write into a shared shift register each segment keeps its own memory, each segment can be addressed and then read through amplifiers. This change introduces additional levels of complexity for each segment when compared to CCD.
## Characteristics
Some characteristics of CMOS sensors are:
- Higher structural noise
- Does not have any issues with transporting charge
- Camera can have a more complex dei that include amplifiers, [[Convertor|A/D convertors]] and other components as parts of the segments drastically speeding up processing.
- Simple interfacing
- Lower consumption
- Only one supply voltage
- High range of resolutions (160x160 to ~8000x6000)
- Typically lower sensitivity
- Lower cost