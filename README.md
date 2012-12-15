Ominus Project
==============

Ominus Project is both a place to experiment with MCUs and an attempt to create a fully integrated prototype
of a wirelessly controlled multi-colour lighting unit

This project is split into two parts. A wireless transmitter which sends the desired colour sequence over the air
to multiple wireless recievers. The recievers then modulate a RGB LED to the desired colour combination and brightness

Receiver
--------

The Receiver is a single PIC18F1230 driving a 3W three colour LED over 3 separate PWM channels. This will ensure smooth and accurate control.
The colour values will be recieved from UART by a 434MHz Radio module or just a wire in prototyping situations. The UART frame will
consist of 8 bit device select, 8 bit device mask, and 3x 8 bit colour values for Red, Green, and Blue channels.

The LED driver will be made up of 3 low power MOSFETs, however, as the PICs output pins can source ~25mA the prototype can forgo the MOSFET stage.

Transmitter
-----------

The implementation of a transmitter unit is undecided as of now, as its implementation would differ based on input requirenments.
There are three possible configurations:

1. Using Minimus 32k AVR with USB connection to output the required UART signal
1. Use PIC18F2550 USB capability to expose a native interface
1. Use GPIO of a Raspberry Pi to provide the UART signal, benefiting from an Ethernet connectio


