# AHB Crossbar

This repository contains a fixed AHB-Lite crossbar that connects
3 bus Initiators to 6 bus Responders.

## Features of the AHB Crossbar

- Three AHB-Lite initiator interfaces
- Six AHB-Lite responders interfaces
- Address decoding and responder selection for each initiator interface
- Arbitration when multiple initiators request the same responder
- Reset and debug-reset support
- SystemVerilog RTL suitable for FPGA or ASIC integration

## Directory structure

- [`doc/`](doc/) - Documentation for the crossbar architecture and integration.
- [`fv/`](fv/) - SystemVerilog properties used to formally verify the matrix.
- [`ipcard/`](ipcard/) - IP metadata and the generated IP card PDF.
- [`src/`](src/) - SystemVerilog RTL source files.

The top-level RTL module is
[`src/Top_RISCV_Subsystem_AHB_Lite_AHB_Lite.sv`](src/Top_RISCV_Subsystem_AHB_Lite_AHB_Lite.sv).
The crossbar exposes three 32-bit AHB-Lite initiator-side interfaces and six
32-bit AHB-Lite responder-side interfaces, together with `clk`, `rst`, and
`debug_ndmrst` control signals.

## Usage

Use [`Bender.yml`](Bender.yml) to include the RTL sources in a hardware design.
Instantiate `Top_RISCV_Subsystem_AHB_Lite_AHB_Lite` and connect the AHB-Lite
initiator and responder interfaces to the surrounding subsystem. Refer to
[`doc/`](doc/) for integration documentation as it is added.

## Verification

The formal properties in [`fv/`](fv/) cover AHB-Lite matrix routing and
initiator-to-responder transfer behavior. Integrate the properties with the
applicable formal verification environment.
