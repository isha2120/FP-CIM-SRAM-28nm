# FP-CIM-SRAM-28nm
🗃️ Floating-Point SRAM Compute-in-Memory Macro (28 nm) | Cadence Virtuoso, Spectre
📌Prof. Joycee Mekie , IIT Gandhinagar 
🗓️ Oct’26-Nov'26

Replicated the exponent-normalization datapath of an FP-CIM SRAM macro (IEEE TVLSI 2026) at transistor level on a 28\,nm PDK
Designed a right-shiftable 9T SRAM bitcell with decoupled feedback and an 8-bit WEA/SESA row; verified contention-free write, 3-phase charge-transfer in-array shift, and self-restoring 8-cycle shift ring
Characterized the 9T cell at TT, 0.9V: HSNM 335.3 mV, WSNM 643.6 mV via butterfly-curve analysis}
Built the maximum exponent-sum search normalizer (bit-serial FA + carry DFF, ping-pong LIFO unit, bitwise comparator, OR tree); verified MSB-first candidate elimination on the paper's test vector}
Debugged a leakage failure on the comparator's dynamic node that falsely eliminated candidates; fixed it with a buffer and weak PMOS keeper (W=100\,nm, L=60\,nm)}
