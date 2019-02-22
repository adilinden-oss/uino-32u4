## \*uino-32u4

\*uino-32u4 is an Arduino compatible platform with very minimalistic features.

### Licensing

This work is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License, CC BY-SA.

You are free to copy, distribute and transmit the work. You must attribute the work in the manner specified by the author or licensor (but not in any way that suggests that they endorse you or your use of the work). you alter, transform, or build upon this work, you may distribute the resulting work only under the same or similar license to this one.

Please refer to [http://creativecommons.org/licenses/by-sa/3.0/] for the license.

### Credit

The \*uino-32u4 is derived from previous work done by:

- The Arduino team [http://arduino.cc/]
- The vinciDuiono team (fmalpartida - fm, Inizul, JMN, yOPERO, nayma, flico, josemanu and shaktale) [http://bitbucket.org/fmalpartida/vinciduino/wiki]

Also, many thanks to fm and CrossRoads and others on the Arduino forums for invaluable advise and discussion on an Atmel ATmega32u4 based board.

### Details

The board is based on the Arduino Leonardo and vinciDuino platforms. It shares the same Atmel ATmega32U4 microcontoller and utilizes the native USB feature of the ATmega32U4.

However, the mapping of microcontroller pins to analog and digital shield I/O is different. The goal of \*uino-32u4 is to preserve the I2C and SPI pin configuration of the Adrduino UNO and like boards. It is also very minimalistic in features as it lacks any of the acustomed Arduino external power and power switching features. The board is intended to be powered via the USB port only.

Two headers for jumpers have been provided to select the function of the A4/A5 analog I/O pins and an alternate pin for LED L1. The extra ATmega32U4 pin has been routed to an additional LED L2. LED L2 fills in the role of the LED_BUILTIN.

The board is compatible with the Arduino Leonardo bootloader as currently in the Arduiono 1.0 relase IDE. To use this board the Leonardo has to be selected as board in the IDE. The pin mapping table shows how the Leonardo I/O labeling corresponds to \*uino-32u4 I/O.

### Arduino IDE

The board is supported in Arduino IDE 1.6.x via the core files available at: [adilinden-oss/uino-arduino](https://github.com/adilinden-oss/uino-arduino)

To install clone uino-arduino into the hardware folder inside your Sketchbook folder. The board will then automagically appear in the Boards menu.

### Pin Mapping

This table provides a reference as to how the I/O pins of the \*uino-32u4 map to the ATmega32u4 pins. It also shows the pin usage of the Leonardo/ vinciDuino boards for comparison.

```
*uino     Leonardo    ATmega32u4                          *uino Function
A0/D18    A0          36 - PF7 (ADC7)
A1/D19    A1          37 - PF6 (ADC6)
A2/D20    A2          38 - PF5 (ADC5)
A3/D21    A3          39 - PF4 (ADC4)
A4/D22    A4          40 - PF1 (ADC1) 
                   or 19 - PD1 (SDA/INT1)                 SDA / INT
A5/D23    A5          41 - PF0 (ADC0) 
                   or 18 - PD0 (OC0B/SCL/INT0)            SCL / INT

D0        D0          20 - PD2 (RXD1/INT2)                UART RX / INT
D1        D1          21 - PD3 (TXD1/INT3)                UART TX / INT
D2        D13         32 - PC7 (ICP3/CLK/OC4A)            PWM
D3        D11         12 - PB7 (PCINT7/OC0A/OC1C)         PWM
D4/A6     D4          25 - PD4 (ICP1/ADC8)
D5        D5          31 - PC6 (OC3A/OC4A)                PWM
D6/A7     D6          27 - PD7 (T0/OC4D/ADC10)            PWM
D7        D7          1  - PE6 (INT6/AIN0)

D8/A8     D8          28 - PB4 (PCINT4/ADC11)             INT
D9/A9     D9          29 - PB5 (PCINT5/OC1A/OC4B/ADC12)   PWM / INT
D10/A10   D10         30 - PB6 (PCINT6/OC1B/OC4B/ADC13)   PWM / INT
D11       D16/ICSP    10 - PB2 (PCINT2/MOSI)              SPI MOSI / INT
D12       D14/ICSP    11 - PB3 (PCINT3/MISO)              SPI MISO / INT
D13       D15/ICSP    9  - PB1 (PCINT1/SCLK)              SPI SCK / INT

SDA/D14   D2          19 - PD1 (SDA/INT1)
SCL/D15   D3          18 - PD0 (OC0B/SCL/INT0)            PWM / INT

D16                   33 - PE2 (HWB)                      LED L1
D17       D12/A11     26 - PD6 (T1/OC4D/ADC9)             LED L2

D30       TX          22 - PD5                            TX LED
D31       RX          8  - PB0 (PCINT0/SS)                RX LED
```

Note that analog pins A0 to A10 also map to digital pins D18 to D29.

