# Roadmap

Project stage: **initial architecture**. Items below are plans, not completed milestones.

## Phase 0 — Platform definition

- [ ] Freeze model/option naming and electrical scope.
- [ ] Select injector type/driver and ignition interface.
- [ ] Select target microcontroller/production package.
- [ ] Review reference designs and license compatibility.
- [ ] Produce validated GPIO/peripheral pin plan.

## Phase 1 — ECU-8 reference design

- [ ] KiCad common blocks: supply, MCU, sensor supply, CAN/USB, input conditioning.
- [ ] Eight protected injector channels and eight ignition outputs.
- [ ] Connector pinout, assembly variants, BOM, enclosure constraints.
- [ ] ERC/DRC + independent schematic review.

## Phase 2 — Firmware / laboratory validation

- [ ] Pin rusEFI upstream revision, add custom target and build.
- [ ] ST-Link/SWD bring-up; USB/CAN connectivity and diagnostics.
- [ ] Bench CKP/CMP simulation, injector/ignition/actuator loads.
- [ ] Safety, fail-safe and regression testing.

## Phase 3 — ZMZ-5234 evaluation

- [ ] Record actual sensors, triggering, injectors, coil topology and wiring.
- [ ] Initial mechanical throttle and conservative injection control.
- [ ] Bench / supervised engine tests and calibrations with wideband lambda.
- [ ] Document logs, revisions and issues. No road-use claims.

## Phase 4 — Family and options

- [ ] Prove ECU-4 and ECU-6 BOM assembly variants.
- [ ] Optional DBW/knock/EGT/WBO/logging modules and their own tests.
- [ ] Compact layouts only when core design and tests are stable.

## Phase 5 — Commercial readiness

- [ ] License compliance, manufacturing process, test fixtures, product traceability.
- [ ] Electrical/environmental/EMC qualification and market-specific legal review.
- [ ] Release notes, service documentation, update and warranty policies.
