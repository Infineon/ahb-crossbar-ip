# AHB Crossbar RTL

This directory contains the SystemVerilog implementation of the AHB-Lite
crossbar.

## Top-level module

The integration module is
[`Top_RISCV_Subsystem_AHB_Lite_AHB_Lite.sv`](Top_RISCV_Subsystem_AHB_Lite_AHB_Lite.sv).
It connects three AHB-Lite master interfaces to six AHB-Lite slave interfaces
and exposes `clk`, `rst`, and `debug_ndmrst` control signals.

## RTL structure

- `Top_RISCV_Subsystem_AHB_Lite_AHB_Lite.sv` - Top-level crossbar assembly.
- `Top_RISCV_Subsystem_AddressDecoder.sv` - Address decoding.
- `Top_RISCV_Subsystem_ArbitrationUnit.sv` - Arbitration control.
- `Top_RISCV_Subsystem_MasterSelect.sv` - Master-side selection.
- `Top_RISCV_Subsystem_SlaveSelect.sv` - Slave-side selection.
- `Top_RISCV_Subsystem_AHB_Lite_AHB_Lite_*` - Per-interface input,
  selection, routing, and error-detection components.

The source files are generated RTL and are listed in the repository
[`Bender.yml`](../Bender.yml) manifest in dependency order.

## Usage

Include the files through [`../Bender.yml`](../Bender.yml), or compile the
listed SystemVerilog sources directly. Instantiate
`Top_RISCV_Subsystem_AHB_Lite_AHB_Lite` at the subsystem boundary and connect
matching AHB-Lite signal groups on the master and slave sides.
