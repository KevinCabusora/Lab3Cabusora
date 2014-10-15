Lab3Cabusora
============

C2C Kevin Cabusora
Dr. George York, M2
LCD Screen Code

##Mega-Prelab

###Nokia1202 LCD BoosterPack v4-5

| Name | Pin# | Type   | PxDIR | PxREN | PxOUT |
|:----:|------|--------|-------|-------|-------|
| GND  | 20   | Power  | N/A   | N/A   | N/A   |
| RST  | 8    | Output | 1     | 0     | 1     |
| P1.4 | 6    | Output | 1     | 0     | 1     |
| MOSI | 15   | Output | 1     | 0     | 1     |
| SCLK | 7    | Output | 0     | 0     | 1     |
| VCC  | 1    | Power  | N/A   | N/A   | N/A   |
| S1   | 9    | Input  | 0     | 1     | 1     |
| S2   | 10   | Input  | 0     | 1     | 1     |
| S3   | 11   | Input  | 0     | 1     | 1     |
| S4   | 12   | Input  | 0     | 1     | 1     |

###Configure the MSP430

| Mystery Label | Register |
|---------------|----------|
| A             | P1DIR    |
| B             | P1OUT    |
| C             | P2DIR    |
| D             | P2OUT    |

| D        | Bit | Function as set in the code                       |
|----------|-----|---------------------------------------------------|
| UCCKPH   | 7   | Clock phase select                                |
| UCMSB    | 5   | Controls direction of Tx/Rx shift registers       |
| UCMST    | 3   | Master mode select                                |
| UCSYNCH  | 0   | Synchronous mode enabled                          |
| UCSSEL_2 | 6-7 | Select SMCLK as BRCLK source clock in master mode |
| UCSWRST  | 0   | Software rest eneable                             |

###Communicate to the Nokia1202 Display

| Symbolic Constant            | Hex | Function                                  |
|------------------------------|-----|-------------------------------------------|
| #STE2007_REST                | E2  | Internal reset                            |
| #STE2007_DISPLAYALLPOINTSOFF | A4  | LCD display, normal display               |
| #STE2007_POWERCONTROL        | N/A | Sets on chip power supply function        |
| #STE2007_POWERCTRL_ALL_ON    | 2F  | Booster, volt regulator & follower all on |
| #STE2007_DISPLAYNORMAL       | A6  | LCD display, normal                       |
| #STE2007_DISPLAYON           | AF  | Display turned on  

##Main Lab

| Line | R12  | R13  | Purpose                                                                                                         |
|------|------|------|-----------------------------------------------------------------------------------------------------------------|
| 66   | 0x01 | 0xE7 | R12: specifies data, R13: holds an 8-bit value which translates to a 8 pixel length vertical column (1110 0111) |
| 276  | 0x00 | 0xB0 | R12: specifies command, R13: 0xB0 is prefix for page address                                                    |
| 288  | 0x00 | 0x10 | R12: specifies command, R13: 0x10 is prefix for top 4 bits in column                                            |
| 294  | 0x00 | 0x00 | R12: specifies command, R13: 0x00 is prefix for bottom 4 bits in column                                         |

| Line | Command/Data | 8-bit packet |
|------|--------------|--------------|
| 66   | Data         | 11100111     |
| 276  | Command      | 10110001     |
| 288  | Command      | 00010000     |
| 294  | Command      | 00000001     |

###Logic Analyzer Displays

First Time Interval
![First Time Interval](https://github.com/KevinCabusora/Lab3Cabusora/blob/master/First%20Time%20%20Interval.png)

Second Time Interval
![Second Time Interval](https://github.com/KevinCabusora/Lab3Cabusora/blob/master/2nd%20Time%20Interval.png)

Third Time Interval
![Third Time Interval](https://github.com/KevinCabusora/Lab3Cabusora/blob/master/3rd%20Time%20Interval.png)

Fourth Time Interval
![Fourth Time Interval](https://github.com/KevinCabusora/Lab3Cabusora/blob/master/4th%20Time%20Interval.png)

###Writing Modes

![Writing Modes](https://github.com/KevinCabusora/Lab3Cabusora/blob/master/Writing%20Modes.png)


