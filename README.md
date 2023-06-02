#### LFSR

The LFSR module operates on each rising edge of the clock signal and utilizes flip-flops to store the 
current state of the register and perform the necessary shift and feedback operations.

The key operations of the LFSR are as follows:

* Reset

 The LFSR can be asynchronously reset by activating the reset signal ('reset_n').
 When the reset signal is low, the LFSR is cleared to an initial state. In your code, the 
 initial state is set to 'b1 (binary 1).

* Enable

 The LFSR can be enabled by activating the enable signal ('enb').
 When the enable signal is high, the LFSR advances to the next state on each clock cycle.

* Shift and Feedback

 On each clock cycle, the LFSR performs a shift operation, 
 moving the bits to the right. The most significant bit is discarded, and a
 new bit is inserted at the least significant position. The specific feedback
 function used is an XOR operation between the second-to-last bit and the last bit of the LFSR.

* Output

 The current state of the LFSR, represented by the bits stored in the shift register, is 
 provided as the output of the module. The output is assigned to the signal 'lfsr_out'.

It's important to note that the sequence generated by this LFSR is pseudo-random, meaning
it appears random but is ultimately deterministic. The length of the sequence before it repeats
is determined by the size of the LFSR, which in this case is 'n'. For a 3-bit LFSR, the maximum 
period of the generated sequence is 2^3 - 1 = 7 clock cycles.

By configuring the feedback taps and the number of bits in the LFSR,
different LFSR sequences can be generated with varying properties.
The specific feedback tap configuration you have chosen produces a pseudo-random
sequence of 3-bit values that repeat every 7 clock cycles.

* In summary


the LFSR module implements a pseudo-random sequence generator
using a linear feedback shift register. The generated sequence appears random,
but it follows a repeating pattern determined by the feedback function and the number of bits in the LFSR.
The module provides the current state of the LFSR as the output, allowing you to utilize the pseudo-random sequence
for various applications that require deterministic yet seemingly random behavior.

כםר
# For the complete model of an LFSR with "n" bits,
# you can refer to the following resource: xilinx.com/support/documentation/application_notes/xapp052.pdf
