# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**
~~~
A Serial-In Serial-Out (SISO) shift register is a sequential logic circuit that accepts data one bit at a time.

The output is also produced one bit at a time, in a serial manner.

It consists of a series of flip-flops connected in a chain.

The output of each flip-flop becomes the input to the next flip-flop in the sequence.

On every clock pulse, the data bit shifts from one flip-flop to the next.

The first bit entered will be the first bit to appear at the output after moving through all stages.

SISO registers are used for temporary data storage, data transfer, and time-delay applications.

Since the shifting depends on clock pulses, it operates as a synchronous circuit.
~~~
**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**
~~~
1.Create a new project using New Project Wizard and set the working directory.

2.Create a new Verilog/VHDL file and write the SISO shift-register code.

3.Save the file and set the module/entity as the top-level design.

4.Compile the project using the Start Compilation option.

5.Assign input/output pins using Pin Planner if hardware testing is needed.

6.Run simulation (RTL or waveform) to verify serial shifting operation.

7.Program the FPGA device using Programmer if implementation on board is required.
~~~

**PROGRAM**
~~~
SERIAL IN SERIAL OUT SHIFT REGISTER

module pr(clk, sin, q);
input clk;
input sin;
output [3:0] q;
reg [3:0] q;
always @(posedge clk)
begin
q[0] <= sin;
q[1] <= q[0];
q[2] <= q[1];
q[3] <= q[2];
end
endmodule
~~~
~~~
Developed by:MANUSIYA R RegisterNumber: 25016729
~~~
**RTL LOGIC FOR SISO Shift Register**
<img width="2537" height="1351" alt="ex10(1)" src="https://github.com/user-attachments/assets/ccf460e8-5015-4e33-82ad-8058d8df0fb1" />

**TIMING DIGRAMS FOR SISO Shift Register**
<img width="2538" height="1298" alt="ex10(2)" src="https://github.com/user-attachments/assets/55aeb47e-f629-41b4-8eee-0d61715af662" />

**RESULTS**
The serial-in-serial-out shift register was successfully implemented in Quartus 13.0, and the serial input data was correctly shifted and obtained as serial output with each clock pulse.
