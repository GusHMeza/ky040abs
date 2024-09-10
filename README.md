# ky040abs
Turn a KY040 incremental encoder to an absolute encoder with a 1 wire interface.
The KiCAD project is provided for the adapter board. 

IMPORTANT: Use avrboy by kimio-kosaka to program the ATTINY10 chip before soldering it to this adapter module. The PCB does not have a TPI interface connector.

# HOW TO USE
1. Flash an ATTINY10 chip with the provided script.
2. Use the suggested connector in the BOM or solder wires to the power inputs and the signal wire.
3. Power the module.
4. The SIG wire works as an active HIGH input, when it receives a HIGH pulse, it switches to an active HIGH output.
4.1. Use an I/O pin from a MCU to pulse the SIG wire, then read how many pulses the ky040abs answers with.
5. To adjust the resolution (given you have a gear ratio between the encoder and and a spinning shaft), modify the *angulo_en_pulsos* variable.
5.1. The provided code shows a bidirectional rotation reading, where the ATTINY10 starts at 15 counts that either increment up to 30 or decrement down to 0 depending on the direction of rotation. 

