# rusEFI integration strategy

This repository contains **no rusEFI firmware copy, build scripts or bootable image** yet.

## Upstream links

- Main firmware: https://github.com/rusefi/rusefi
- Custom firmware example: https://github.com/rusefi/fw-custom-example
- Documentation: https://wiki.rusefi.com/

## Integration plan

1. Pick an exact upstream rusEFI revision, inspect its supported STM32F407 targets and the configuration API at that revision.
2. Establish a custom board target using the official custom firmware example; retain upstream version reference.
3. Map **verified** KiCad nets to rusEFI GPIO names and check all timer/peripheral conflicts.
4. Configure sensor signal conditioning, injector and ignition electrical polarities, fail-safe output behavior and allowed pin functions.
5. Produce a repeatable build and compare its board/firmware identity with a supported tuning client.
6. Bench test with simulated crank/cam signals and dummy actuator loads **before** connecting to an engine.
7. Publish source, notices, exact build instructions and validated binaries for any firmware distributed in a product, consistent with licenses.

## Critical distinction

The example boards and public binaries of other manufacturers are **reference material only**. Their firmware is not suitable for flashing onto an untested custom AVTOSTAR ECU PCB.

## Repository strategy

Keep board-adaptation source and reproducibility metadata here initially. If firmware grows, split its redistributable source into a dedicated public repo while documenting the pinned rusEFI upstream version.
