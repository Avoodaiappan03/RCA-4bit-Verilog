# RCA-4bit-Verilog
# 4-Bit Ripple Carry Adder (RCA) Verification

## Project Overview
This project involves the design and functional verification of a 4-bit Ripple Carry Adder using Verilog HDL. It was developed as part of my 4th-semester Electronics and Communication Engineering (ECE) coursework to practice RTL design and exhaustive verification methodologies.

## Design Details
- **Module**: `full_adder_4bit_bh`
- **Methodology**: Behavioral modeling using concatenation `{cout, s}` for efficient sum and carry generation.
- **Tools**: Developed and simulated using **Icarus Verilog 12.0** on the EDA Playground platform.

## Verification Strategy
To ensure 100% functional correctness, I implemented an exhaustive testbench:
- **Exhaustive Stimulus**: Used nested loops to iterate through all 512 possible input combinations ($2^4 \times 2^4 \times 2^1$).
- **Automated Monitoring**: Utilized the `$monitor` task to log every signal transition to the console for real-time debugging.
- **Waveform Analysis**: Enabled VCD (Value Change Dump) to generate timing diagrams for visual inspection of carry propagation.

## Simulation Results
The simulation successfully passed all test cases. Below is the timing diagram showing the signals $A$, $B$, $Cin$, $Sum$, and $Cout$.

![4-Bit Adder Waveform](waveform_result.png)

## How to Run
1. Upload `design.sv` and `testbench.sv` to [EDA Playground](https://edaplayground.com/).
2. Select **Icarus Verilog 12.0** as the simulator.
3. Ensure **Open EPWave after run** is checked in the left sidebar.
4. Click **Run** to execute the simulation and view the waveforms.
![4-Bit Adder Waveform](your_image_name.png)
