# AHB Matrix Properties

This directory contains the SystemVerilog Assertions for the AHB-Lite matrix.

## Files

- [`ahb_matrix_props.sv`](ahb_matrix_props.sv) - Properties covering
  master-to-slave routing, signal forwarding, arbitration, and response
  behavior. These properties are generated automatically using the [Universal Format Specification (USF) methodology](https://ieeexplore.ieee.org/document/10564551).
- [`doc/ahb_matrix_3x6_usf.pdf`](doc/ahb_matrix_3x6_usf.pdf) - Documentation of the AHB Crossbar's functional verification scope, and the actions that are verified via properties found in [`timer_functionality_props.sv`](timer_functionality_props.sv).

## Usage

Compile this property file with the crossbar RTL and bind or instantiate the
properties in a formal verification environment. The assertions reference
`Top_RISCV_Subsystem_AHB_Lite_AHB_Lite` as the design under verification.


# Formal

The [`doc/ahb_matrix_3x6_usf.pdf`](doc/ahb_matrix_3x6_usf.pdf) is also generated using a novel methodology developed as part of ISOLDE project. It combines USF descriptions together with and Large Language Models to generated detailed documentation of the verification scope. For more details, please see: [Enhancing LLM-Generated Hardware Documentation: Post-Processing and Prompt Engineering Techniques](https://doi.org/10.5281/zenodo.23045099).
