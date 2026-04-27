# yoRadio_PCB
Made a PCB for yoRadio internet radio.
The PCB is dimensioned to fit exactly on the back on the 3.5" LCD display.
Additional to the 3.5" LCD display connectors there are pin headers to connect other size or type of LCD displays.
The PCB is made for ESP32S3 with PSRAM in 44-pin dev board.
For audio the I2S PCM5102A DAC is used, the output signal goes trought a pinheader trought a potentiometer or it can be wired with jumpers directly 
to the PAM8403 amplifier module. The power supply can be directly 5V or from the MP1584 DC-DC Buck converter, here the input voltage cany vary between 9 - 24VDC.
There are Pin headers for two encoders, VSPI for SD card reader, two I2C, two type LCD and a big Pin header taht can be used for push buttons, IR Remote receiver, another SD card interface or RS232.

Used modules from Aliexpress:

ESP32-S3 DevKit C1 N16R8 ipex weld:
https://www.aliexpress.com/item/1005008750977454.html
3.5" LCD:
https://www.aliexpress.com/item/1005004605415404.html
Rotary encoders:
https://www.aliexpress.com/item/1005007129508312.html
Pin headers:
https://www.aliexpress.com/item/4000873858801.html
PAM8403 D-Class 2*3W amplifier board:
https://www.aliexpress.com/item/1005010355411369.html
Optional you can use this type of pcb, it has a potentiometer and a large 470uf capacitor:
https://www.aliexpress.com/item/1005008554577465.html
MP1584EN Step Down DC-DC module, if you want to power it with voltage between 9-24V:
https://www.aliexpress.com/item/1005010535958276.html

Components from TME:
Electrolitic capacitors mounted on the side on the bottom of the PCB.
C16: 470uF/16V and C5: 220uF/35V Ø8x16mm
https://www.tme.eu/ro/details/ed1c471mnn0816/condensatoare-electrolitice-tht/elite/
https://www.tme.eu/ro/details/ed1v221mnn0816/condensatoare-electrolitice-tht/elite/
Optional LD1117 - 3.3V LDO voltage regulator:
https://www.tme.eu/ro/details/ldl1117s33r/regulatoare-de-tensiune-neregulata-ldo/stmicroelectronics/
SMD capacitors 100nF:
https://www.tme.eu/ro/details/cl21b104kbcnnnc/condensatoare-mlcc-smd/samsung/
SMD resistors 1kΩ, 2.2kΩ, 10kΩ
https://www.tme.eu/ro/details/crcw08051k00fktabc/rezistente-smd/vishay/
https://www.tme.eu/ro/details/smd0805-2k2-1%25/rezistente-smd/royalohm/0805s8f2201t5e/
https://www.tme.eu/ro/details/smd0805-10k-1%25/rezistente-smd/royalohm/0805s8f1002t5e/
Schottky Diode for reverse supply polarity protection:
https://www.tme.eu/ro/details/fss14trtb/diode-schottky-smd/fagor/fss14-trtb/
https://www.tme.eu/ro/details/ss34-cdi/diode-schottky-smd/cdil/ss34/
https://www.tme.eu/ro/details/1n5819_st/diode-schottky-tht/stmicroelectronics/1n5819/
Screwed spacer:
https://www.tme.eu/ro/details/tff-m3x10_dr123/distantiatoare-din-metal/dremec/123x10/
Optional connector:
https://www.tme.eu/ro/en/details/cc-114/rca-connectors/changzhou-dahua-imp-and-exp-group-co/vg03094black/
https://www.tme.eu/ro/en/details/cc-115/rca-connectors/changzhou-dahua-imp-and-exp-group-co/vg03094-red/
https://www.tme.eu/ro/en/details/jc-204s/jack-connectors/ninigi/
### PCB images
https://github.com/dxter2000/yoRadio_PCB/blob/main/ESP32_S3_Radio_3.5v1.01_pcb_top.png
https://github.com/dxter2000/yoRadio_PCB/blob/main/ESP32_S3_Radio_3.5v1.01_pcb_bottom.png
https://github.com/dxter2000/yoRadio_PCB/blob/main/ESP32_S3_Radio_3.5v1.01_schematic.png

