# AHB Matrix Properties

This directory contains the SystemVerilog Assertions for the AHB-Lite matrix.

## Files

- [`ahb_matrix_props.sv`](ahb_matrix_props.sv) - Properties covering
  master-to-slave routing, signal forwarding, arbitration, and response
  behavior.

## Usage

Compile this property file with the crossbar RTL and bind or instantiate the
properties in a formal verification environment. The assertions reference
`Top_RISCV_Subsystem_AHB_Lite_AHB_Lite` as the design under verification.
