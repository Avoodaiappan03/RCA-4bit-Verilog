# RCA-4bit-Verilog
# 4-Bit Behavioral Full Adder (SystemVerilog)

## 📌 Overview
This repository contains a digital design implementation of a **4-bit Full Adder** using behavioral modeling in SystemVerilog. The project demonstrates a clean RTL (Register Transfer Level) approach to multi-bit addition, including a self-checking testbench that generates standard VCD (Value Change Dump) waveforms for timing analysis.



## 🏗️ Design Architecture
The design utilizes a high-level behavioral description to perform 5-bit addition (4-bit sum + 1-bit carry). By using the concatenation operator, the carry-out logic is implicitly handled by the compiler, ensuring an optimized synthesis path.

### Specifications:
* [cite_start]**Word Length:** 4 bits[cite: 54].
* [cite_start]**Modeling Style:** Behavioral (using `always@(*)` blocks)[cite: 54].
* [cite_start]**Logic Operation:** `{cout, s} = a + b + cin`[cite: 54].

### Pin Mapping:
| Signal | Direction | Width | Description |
| :--- | :--- | :--- | :--- |
| `a[3:0]` | Input | 4 | [cite_start]Augend vector [cite: 54] |
| `b[3:0]` | Input | 4 | [cite_start]Addend vector [cite: 54] |
| `cin` | Input | 1 | [cite_start]Input carry bit [cite: 54] |
| `s[3:0]` | Output | 4 | [cite_start]Summation result [cite: 54] |
| `cout` | Output | 1 | [cite_start]Final carry-out bit [cite: 54] |

## 🧪 Verification Environment
The testbench (`testbench.sv`) provides an exhaustive stimulus to verify the adder's functionality across various input transitions.

* [cite_start]**Monitor Task:** Automatically logs signal changes to the console with timestamps[cite: 50].
* [cite_start]**Waveform Generation:** Dumps simulation data into `dump.vcd` for visualization[cite: 51].
* [cite_start]**Stimulus Loop:** Employs nested `repeat` blocks to iterate through 16 iterations of inputs `a` and `b`, toggling `cin` to ensure full coverage[cite: 51, 52, 53].

## 🛠️ Simulation Workflow
This project is configured for the **Icarus Verilog** toolchain.

### Prerequisites:
* Icarus Verilog (iverilog)
* GTKWave (for waveform viewing)

### Execution:
1. **Compile the Source:**
   ```bash
   iverilog -g2012 -o simulation.out design.sv testbench.sv
## 🚀 How to Run (via EDA Playground)

This project is configured to run on [EDA Playground](https://edaplayground.com/) for quick verification without local installation.

1.  **Upload Files:** Copy the contents of `design.sv` and `testbench.sv` into the respective editors on EDA Playground.
2.  **Configure Environment:** * Set the **Languages & Libraries** to **SystemVerilog/Verilog**.
    * [cite_start]Select **Icarus Verilog 12.0** as the simulator[cite: 1, 23].
3.  [cite_start]**Enable Waveforms:** Ensure **Open EPWave after run** is checked in the left sidebar to view the timing diagrams[cite: 12, 13, 23].
4.  **Execute:** Click **Run** to execute the simulation. [cite_start]The console will display the `$monitor` output, and the waveform viewer will launch automatically[cite: 11, 24].

## 📊 Waveform Analysis
Below is the expected simulation waveform showing the relationship between inputs ($a, b, cin$) and outputs ($s, cout$):

![4-Bit Adder Waveform](your_image_name.png)
![4-Bit Adder Waveform](your_image_name.png)
