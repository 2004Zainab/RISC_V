# RISC-V Single-Cycle Processor

A **32-bit RISC-V single-cycle processor** implemented in **Verilog HDL**. This project focuses on designing the fundamental components of a RISC-V CPU, integrating them into a complete datapath, and verifying their functionality using directed testbenches.

##  Overview

The processor follows a basic **single-cycle datapath**, where instruction fetch, decode, execution, memory access, and write-back are handled within the processor architecture.

The design is built using independent and reusable RTL modules, making it easier to understand, simulate, debug, and extend the processor.

##  Main Modules

* **Program Counter (PC)** – Maintains and updates the current instruction address.
* **Instruction Memory** – Stores and provides instructions based on the PC.
* **Register File** – Provides two read ports and one write port for the 32 general-purpose registers.
* **ALU** – Performs arithmetic and logical operations.
* **ALU Control** – Generates ALU control signals based on instruction fields.
* **Control Unit** – Generates control signals required for instruction execution.
* **Immediate Extension** – Generates and sign-extends immediate values for different instruction formats.
* **Data Memory** – Handles processor memory read and write operations.
* **Multiplexer & Adders** – Used for datapath selection and address calculations.
* **Clock Divider** – Generates the processor clock from the input clock.

##  Supported Instruction Types

The implementation includes the basic structure required for:

* R-Type instructions
* I-Type instructions
* Load instructions
* Store instructions
* Branch instructions

Example instructions used during testing include:

```text
ADD
SUB
ADDI
LW
SW
BEQ
BNE
```

##  Verification

Each major RTL module is accompanied by a **directed testbench** to verify its functionality independently.

The complete processor is also tested using an integrated testbench that monitors:

```text
PC
Instruction
Register Values
ALU Result
Memory Data
Register Write
Memory Write
```

Simulation output and waveforms can be used to analyze the instruction execution and debug the processor datapath.

## 📁 Repository Structure

```text
RISC-V/
│
├── RTL/
│   ├── risc_v.v
│   ├── alu.v
│   ├── alu_control.v
│   ├── control_unit.v
│   ├── reg_file.v
│   ├── instr_mem.v
│   ├── data_mem.v
│   ├── imm_ext.v
│   ├── pc.v
│   ├── mux.v
│   ├── adder.v
│   └── clk_div.v
│
├── Testbench/
│   ├── risc_v_tb.v
└── README.md
```

##  Tools & Technologies

* **Verilog HDL**
* **Questa/ModelSim**
* **RTL Simulation**
* **RISC-V ISA**

##  Future Improvements

* Complete RV32I instruction support
* Improved memory and branch handling
* Automated verification
* 5-stage pipelined implementation
* Hazard detection and data forwarding
* FPGA implementation

**Status:** RTL implementation and directed verification of a basic 32-bit RISC-V single-cycle processor.
