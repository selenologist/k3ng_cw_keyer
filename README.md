# k3ng_cw_keyer using Arduino Uno and 2x16 LCD keypad shield

This fork only exists to document the few config changes I made building my own version of this keyer. There aren't any meaningful code changes (yet?) but it will help to have a frozen version to link to from my blog, in case I get around to documenting this properly.

My version of the keyer uses the common 16x2 LCD keypad shield and surface-mount Uno board available on AliExpress. I built my keyer for less than AU$20.

I deadbugged everything off of the board and jacks, and I used scrap capacitors so the speed pot and left and right paddle inputs are buffered with 47nF not 10nF, which shouldn't really matter.

Put TWO wires in the 5V and BOTH GND holes, that way you can power the potentiometer and the PS/2 keyboard, and have grounds for the paddle and output.

PS/2 keyboard is attached to pins 2 (data) and 3 (clock). Don't forget to copy the library to your libraries directory.

As the keypad buttons go to A0, the wiper for the potentiometer for speed control was attached to A1.

(A2 is free)

A3 and A4 are left and right keyer inputs.

A5 is the TX output - this goes through a 1k resistor to the base of a 2n2222 transistor which is soldered with its emitter and collector across a 3.5mm jack in parallel with a 10nF capacitor, and the emitter goes to ground.

Sidetone is on pin 11 so I could get it off the ICSP header if I wanted (along with ground), but I haven't actually tried populating it yet.

You could try dimming the backlight with D10 but I haven't bothered.
(Pins 12 and 13 are free)

Original readme follows.

# k3ng_cw_keyer
K3NG Arduino CW Keyer

The K3NG Keyer is an open source Arduino based CW (Morse Code) keyer with a lot of features and flexibility, rivaling commercial keyers which often cost significantly more. The code can be used with a full blown Arduino board or an AVR microcontroller chip can be programmed and used directly in a circuit. This keyer is suitable as a standalone keyer or for use permanently installed inside a rig, especially homebrew QRP rigs. It’s open source code so you can fully customize it to fit your needs and also perhaps learn from it or find coding ideas for other projects.

Documentation is located here:
https://github.com/k3ng/k3ng_cw_keyer/wiki
