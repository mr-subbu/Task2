Name: Patnana Revanth

Company: CODTECH IT SOLUTIONS

ID: CT08STK

Domain: VLSI

Duration: March 10th TO April 10th 2025.

Mentor: NEELA SANTHOSH KUMAR

## Overview of the Project

### Project: RAM-DESIGN

### Report on Synchronous RAM Module with Read and Write Operations
    The development of a synchronous RAM (Random Access Memory) module is crucial for understanding how memory works in a digital system. This report explains the design and simulation of a simple synchronous RAM module with read and write operations using Verilog. The module was designed to perform memory operations synchronously, controlled by clock signals, and simulated to observe its behavior.

Design Overview
The synchronous RAM module was designed to simulate a 256x32-bit memory, where each memory location is 32 bits wide, and there are 256 addressable locations. The module includes the following input and output ports:

Inputs:

clk: The clock signal that synchronizes the operations.
reset: A reset signal that initializes the memory and output when set to high.
address: A 8-bit address input that selects a specific memory location (0 to 255).
data_in: A 32-bit input used to write data into the memory.
write_enable: A signal that controls whether data is written into memory.
read_enable: A signal that controls whether data is read from memory.

data_out: A 32-bit output that holds the data read from the selected memory location.
The RAM design uses an internal memory array, ram[255:0], which is a 256-entry register array where each entry holds a 32-bit value.

Functional Description
The write operation allows data to be written into memory. When the write_enable signal is high, the data_in value is written into the memory location specified by the address input. Similarly, the read operation enables reading from the memory. When read_enable is high, the data stored at the address specified by the address input is read and outputted to the data_out signal.

The operations are synchronized with the clock signal, ensuring that memory access occurs at the rising edge of the clock. The reset input ensures that the module initializes correctly by clearing any outputs, making the system robust to initial conditions.

### Testbench and Simulation
The testbench is used to verify the functionality of the RAM module by simulating write and read operations. It includes the following steps:

Reset: The reset signal is initially set to high to ensure the module starts from a known state.
Write Operation: The testbench writes a value (32'hABCD1234) into the memory location at address 5. The write_enable signal is set to high, while read_enable is kept low.
Read Operation: After the write operation completes, the testbench sets the read_enable signal to high and verifies that the data stored at address 5 is correctly outputted as 32'hABCD1234.
Another Write/Read Operation: The testbench performs another write operation at address 10, followed by a read operation to ensure the memory module works correctly at multiple addresses.
The testbench also includes the $monitor command to display real-time values of the address, data_in, and data_out signals. Additionally, the $dumpfile and $dumpvars commands are included to generate a VCD (Value Change Dump) file, which is used to visualize the waveform of the memory operations.

### VCD Waveform
  The VCD file generated by the simulation contains the timing information of the signals during the simulation. This file can be opened with waveform viewers such as GTKWave or WebWave. The waveform shows how the data_out signal transitions between values based on the memory read and write operations, as well as the effects of the clock signal and reset.

From the waveform, we can see the write operation where the data_in value is stored at the specified address. We can also observe the read operation where the data_out reflects the stored data at the correct address.

### Conclusion
    The synchronous RAM module is a fundamental digital component that mimics how real-world memory systems work. The Verilog implementation simulates memory with both read and write operations, synchronized with the clock signal. By using a testbench to verify the functionality, the design is tested for correctness. The generated VCD file allows us to observe the signal transitions and validate the RAM module’s behavior. This process of designing, simulating, and verifying the module helps in understanding memory operations in a digital system.

### Output: 
![output](https://github.com/mr-subbu/Task2/blob/main/IMG-20250325-WA0016.jpg)
