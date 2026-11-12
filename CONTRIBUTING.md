# Contributing to AVTOSTAR ECU

The repository is at architecture/scoping stage. Please propose technical changes in an issue or pull request with evidence; do not mark an untested design as production ready.

## Hardware contribution checklist

1. State target board model, hardware revision and intended supply conditions.
2. Provide schematic, footprint and BOM changes together.
3. Identify voltage/current ratings, tolerances, transient behavior and relevant component datasheets.
4. Report ERC/DRC status and tests actually executed (bench, simulation or vehicle).
5. Verify license/provenance of each third-party design asset.

## Firmware contribution checklist

1. State upstream rusEFI tag/commit and all changed board files.
2. Document MCU variant, pin mapping and enabled peripheral resources.
3. Supply a reproducible build path and test output before claiming a working image.
4. Keep any passwords, customer information and vehicle logs with personal data out of Git.

Read [docs/safety.md](docs/safety.md) before work involving energised actuators.
