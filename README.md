## Floating-Point SRAM Compute-in-Memory Macro (28 nm)
-🗃️ 9T/10T SRAM with in-array shifting (28 nm) | Cadence Virtuoso, Spectre
-📌Prof. Joycee Mekie , IIT Gandhinagar 
-🗓️ Oct’26-Nov'26

Transistor-level implementation of a BF16 floating-point compute-in-memory SRAM bank, based on
*"A 28-nm Floating-Point SRAM-CIM Macro With In-Array Shifting for Exponent Normalization and
Mantissa Alignment Based on Exponent Midrange"* (IEEE TVLSI 2026), on a 28 nm CMOS PDK.

- Implemented the complete datapath at transistor level: in-array exponent addition, maximum/midrange exponent search, mantissa alignment and accumulation, integrated into the full **5-step MAC flow**.
- Designed both left and right-shiftable **9T SRAM bitcell** and a left/right-shiftable **10T SRAM bitcell**; verified contention-free write, 3-phase charge-transfer in-array shifting and a self-restoring 8-cycle shift ring.
- Built the **exponent arrays** (WEA/SESA, 8 × 8, 9T) with bit-serial full adders and carry DFFs, streaming weight exponents in-array and writing the exponent sums back to the SESA.
- Built the **mantissa shift arrays** (MSA 10T, MSRA 9T) for bidirectional alignment of each product to the exponent midrange (E_max − 4), halving the alignment cycles compared with aligning to E_max.
- Designed the **maximum exponent-sum search** normalizer (ping-pong LIFO, bitwise comparator, OR tree), verifying MSB-first row elimination.
- Designed the **subtraction counter** for shift sequencing and the **adder tree** for accumulation.
- Characterized the bitcells using butterfly-curve analysis: **HSNM 335 mV** and **WSNM 644 mV** at TT, 0.9 V, and verified them across 5 process corners (TT, FF, SS, FS, SF) and temperature.
- Debugged a **leakage failure** on the comparator's dynamic node that falsely eliminated rows; fixed it with a buffer and a weak PMOS keeper (W = 100 nm, L = 60 nm).
