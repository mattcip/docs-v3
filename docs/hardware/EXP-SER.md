# EXP-SER

The EXP-SER expansion board allows your application to communicate over RS485, RS232 and CAN interfaces, enables communication with PC, Devices, boards or sensors communicating over serial channels.
The board features pin headers to connect terminals of CAN bus, R485 and RS232, in addition to exposing the UART/USART pins, I2C and SPI pins in the Z-bus pin header.The board features pin headers to connect terminals of CAN bus, R485 and RS232, in addition to exposing the UART/USART pins, I2C and SPI pins in the Z-bus pin header.


Zerynth expansion boards work seamlessly with all of Zerynth Development boards, combined they can act as a Development Board for prototyping a Product, and a core for industrial applications.

The Z-bus allows the connection in a cascade of different add-on modules to create specific industrial applications that fit into a DIN-RAIL case.

![](img/4zerobox_v1.png)

## Resources

For more infos about electrical connections, and how to use EXP-SER with sensors and other hardware, see the  [user manual](https://www.zerynth.com/download/13894/).

For more information on the EXP-SER Library as software drivers, Its features, functions and examples
[Please check this Link](/latest/reference/libs/zerynth/4zerobox/docs/)

Other useful documents are:

-   [Quick Guide](https://www.zerynth.com/download/15283/)

## Pin Mapping

![](img/4zeroboxpin.png)

## Device Summary

* CAN: The board uses the MCP2518FD IC, It is an External CAN FD Controller.
The board also uses NCV7357 as a CAN FD Transceiver.
Connections between the controller and the transceiver are digitally isolated by the ISO7763 IC.
* RS232 interface: The board uses the MAX3232 IC, 3-V to 5.5-V Multichannel RS-232 Line Driver/Receiver. The output pins of the IC are directly connected to the header P1.
* RS485 interface: The board uses SN65HVD1786D RS485 Transceiver. The output pins of the IC are directly connected to the header P2.

### Rotary Switch SW1
Controls the Interrupt output of the MCP2518 CAN controller.

| Position | Pin on Z-Bus |
|----------|--------------|
|    0     |     INTR     |
|    1     |     INTB     |
|    2     |     INTE1    |
|    3     |     INTE2    |

### S1 Switch
**Warning**: pins 2 and 3 must never be in the ON position at the same time

| PIN |       OFF       |             ON                |
|-----|-----------------|-------------------------------|
|  1  | Select Serial 1 | Select Serial 2               |
|  2  |        -        | Connect CTS with CS MCP2518   |
|  3  |        -        | Connect CTS with RS232/RS485  |

### S2 Switch

| PIN |            OFF           |            ON               |
|-----|--------------------------|-----------------------------|
|  1  |             -            | RS485 120 Ohm Connection    |
|  2  | Disable RX channel RS485 | Enable RX channel RS485     |
|  3  |             -            | CAN 120 Ohm Connection      |

## Power

Power to the EXP-SER is supplied directly by the ZM1-DB.
