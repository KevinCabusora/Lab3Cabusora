Lab3Cabusora
============

LCD Screen Code

Nokia1202 LCD BoosterPack v4-5

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

Configure the MSP430

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

Communicate to the Nokia1202 Display

| Symbolic Constant            | Hex | Function                                  |
|------------------------------|-----|-------------------------------------------|
| #STE2007_REST                | E2  | Internal reset                            |
| #STE2007_DISPLAYALLPOINTSOFF | A4  | LCD display, normal display               |
| #STE2007_POWERCONTROL        | N/A | Sets on chip power supply function        |
| #STE2007_POWERCTRL_ALL_ON    | 2F  | Booster, volt regulator & follower all on |
| #STE2007_DISPLAYNORMAL       | A6  | LCD display, normal                       |
| #STE2007_DISPLAYON           | AF  | Display turned on  

| Line | R12 | R12 | Purpose |
|:----:|-----|-----|---------|
|      |     |     |         |
|      |     |     |         |
|      |     |     |         |
|      |     |     |         |
