# yoRadio_PCB
Made a PCB for yoRadio internet radio.
The PCB is dimensioned to fit exactly on the back on the 3.5" LCD display.

Additional to the 3.5" LCD display connectors there are pin headers to connect other size or type of LCD displays.

The PCB is made for ESP32S3 with PSRAM in 44-pin dev board.

For audio the I2S PCM5102A DAC is used, the output signal goes trought a pinheader trought a potentiometer or it can be wired with jumpers directly
to the PAM8403 amplifier module. The power supply can be directly 5V or from the MP1584 DC-DC Buck converter, here the input voltage cany vary between 9 - 24VDC.

There are Pin headers for two encoders, VSPI for SD card reader, two I2C, two type LCD and a big Pin header taht can be used for push buttons, IR Remote receiver, another SD card interface or RS232.

You can order the PCB from https://jlcpcb.com/ just by uploading the atached gerber.zip file.

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

### Assembly instructions
The PCB is designed to work with different configurations, so not all the components in the schematic are nedded to be soldered on.
Populate the components you need in this order
:
##### SMD jumpers:
SJ1 needs to be connected only if we use LCD with Touch  
SJ2 disconnected  
SJ3 needs to be connected only when we do not use the LD1117-3.3V regulator. The regulator is recommended when use LCD wit 3.3V supply or microSD card.  
J1-0R selects the supply voltage for the 3.5 LCD and JP17 connectors. Check your LCD datasheet.  
J2-OR selects the supply voltage for the JP14.  
SJ4, SJ5, SJ6, SJ7 connect only if use 3.5 LCD onboard SD card reader with VSPI pins

##### SMD capacitors and resistors:
C1, C2, C3, C4, C8, C13, C14, C15 C17, C19, C20 future features, do not asembly.  
C6, C7, C9, C10, C11, C12 - Encoder pins filtering, necesarry when using just encoders but not needed when using encoder boards wich have the capacitors onboard.  
C21, C22, C23, C24, C25, C25, C27 100nF supply pins decoupling, recommended to asembly.  
R21, R22 = 2.2k, R23, R24 = 1k voltage divider from DAC to AMP, necessary.  
R6, R7, R10, R11, R13, R14 = 10k Encoder Pull-up resistors, necesarry when using just encoders but not needed when using encoder boards wich have the resistor onboard and may interfere with operation.  
R1, R2, R3, R4, R5, R8, R15, R16, R17, R18, R19 future features, do not asembly  
R9, R10 = 10k I2C Pull-up, recommended.  
R20 = 10k IR receiver Pull-up, recommended with IR receiver.  
R25 = 1k needed only with T1 BC817 NPN transistor on JP17 connector for reverse backlight LCD, like this one: 2.25-inch TFT LCD ST7789 small screen 76*284 module

##### Other SMD Components:

T1 BC817 or any NPN transistor required only for LCD ST7789_76 backlight inverting on JP17  
IC1 LD1117 - 3.3V Voltage regulator optional for 3.3V supply, use with SJ3 disconnected  
D1 = 1N5819, D2 = SS34, D3 = SS14 required one of these schottky diodes for input DC polarity protection if MP1584  Converter is used  
D4 = SS14 schottky diode reverse polarity protection on 5V input, recommended if 5V is supplyed trough JP7

##### THT capacitors:

C5 = 220uF/35V, size Ø8x16mm, optional with MP1584 converter, mounded on the bottom side, on the side  
C16 = 470uF/16V, size Ø8x16mm, optional 5V buffer capacitor, mounded on the bottom side, on the side  
C18 = 470uF/16V, size Ø8x16mm, optional 5V buffer capacitor, mounded on the top side, when no MP1584 converter board is used

##### Pin headers & connectors:

Use only what you need.  
DC - Input 9 - 24V  
JP1 - Encoder1 connector  
JP2 - Encoder2 connector  
JP3, JP6 - I2C connector, used for I2C display or RTC module  
JP4 - Jumper to connect 5V from MP1584 to the circuit, connect jumper only afther adjust MP1584 module  
JP5 - future features  
JP7 - 5V input or output  
JP8 - SD card reader on SPI3 (VSPI)  
JP9 - IR Receiver  
JP10, JP11 - Audio connector for potentiometer and audio line out connectors, connect on one of them pins 1-2 and pins 3-4 to route audio to amplifier module  
JP12 - future features  
JP13 - SPI2 (VSPI) for SDcard  
JP14 LCD connector for simple LCD1602 display or other SPI LCD, with selectable supply 3.3-5V. WARNING: Pins are not in order for SPI displays, use custom wiring  
JP15, JP16 Speakers output  
JP17 - LCD ST7789_76 connector, it has reversed + with - and backlight is reversed with T1

##### Solder boards:

Put female headers on ESP32-S3 DevKit board too keep them straight and solder them to PCB. It is recommended to use pin header pair, so tha the ESP32-S3 module can be removable.

Check solder jumpers on PCM5102A board as shown in the pictures, then solder with the pinheads on the PCB  
https://github.com/dxter2000/yoRadio_PCB/blob/main/PCM5102_JUMPER.JPG  
https://github.com/dxter2000/yoRadio_PCB/blob/main/PCM5102_SCK.JPG

If want to use onboard amplifier, solder the PAM 8403 amplifier module

If want to use 9-24V DC supply input, on the MP1584 DC-DC converter adjust the output to 5V. I higly recommend NOT to set from the tiny trimmer, because it could drift away easily. The best method is to desolder the trimmer and put a 38kΩ resistor there. I made this value from 3 SMD 1206 resistor of 47k + 250k + 1Mega paralell (one on top of the another). Check the output voltage. Solder it on PCB, If output voltage is 5V +/-0.5V you can connect JP4.

##### Load the software and enjoy the Radio!
