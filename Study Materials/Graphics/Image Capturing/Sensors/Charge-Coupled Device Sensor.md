---
tags:
  - ZPO
aliases:
  - CCD sensor
  - CCD sensors
  - charge-coupled device sensor
sources:
  - "[[ZPO_02_Image_Capturing.pdf]]"
---
An older, simpler and better developed sensor technology when compared to [[Complementary Metal-Oxide-Semiconductor Sensor|CMOS sensor]] used for [[Image Capturing|image capturing]].
## Princip
Sensor is created from a grid of light sensitive flats, that capture light as an electric charge, and special long shift [[Register|registers]]. Each flat is connected to one input into the shift register. During exposure the flats capture light as an electric charge that is then stored inside the registers. Captured image can be then read from these registers by sequentially reading one pixel from each register into another shift register, shifting all others down. The master register is then fully read (emptied in series) before another row is read from the registers.
## Characteristics
Some characteristics of CCD sensors are:
- Lower noise
- Issues with moving of the captured charge
- Issues with controlling of the exposure
- Amplifiers and [[Convertor|A/D convertors]] are outside the die of the sensor
- Complex timing
- Requires several supply voltages
## Uses Cases
CCD sensors are used in common electronics, such as:
- Cameras
- Telescopes (Kepler)
- Scanners
- Bar-code readers
- Machine vision