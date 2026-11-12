# Product requirements (draft)

Status: **Draft — not approved or verified**. Primary intended prototype: **AVTOSTAR ECU-8**, STM32F407VG, rusEFI.

## Functional requirements

| ID | Planned requirement | Verification |
| --- | --- | --- |
| FR-01 | Independently control up to 8 high-impedance injector channels | Bench timing, current and fault tests |
| FR-02 | Provide up to 8 logic-level ignition control channels | Timing, dwell and load testing |
| FR-03 | Support crank and cam synchronisation through protected VR/Hall inputs | Pattern generator, sync loss/recovery tests |
| FR-04 | Read MAP, TPS, CLT, IAT, battery voltage and configurable auxiliaries | ADC linearity, open/short tests |
| FR-05 | Provide one CAN interface, USB/service connection and SWD | Communication/diagnostic tests |
| FR-06 | Provide protected fuel pump/relay and general-purpose PWM outputs | Load and fault tests |
| FR-07 | Expose engine tuning and diagnostics through a compatible rusEFI tuning stack | Verified firmware and tuning session |
| FR-08 | Keep ECU-4, ECU-6 and ECU-8 on one source/architecture baseline | Pin/variant review and build matrix |

## Options pending feasibility

Electronic throttle (DBW), dual CAN, SD logging, wideband oxygen sensor front end, EGT type-K input, knock processing, VVT, boost control, wireless diagnostics and on-board ignition drivers. **Do not treat these as implemented.**

## Assumptions to resolve

- Injector impedance/current and suitable low-side driver/short-circuit protection.
- Which coils are driven: smart coils with integrated igniters or separate ignition power stages.
- Target supply voltage, cranking minimum, load dump/transients and EMC compliance profile.
- Number of VR/Hall input channels and sensor voltage ranges.
- Thermistor curves, analog scaling and protection.
- CAN isolation/non-isolation, transceiver and connector design.
- Waterproofing, case, service access, mounting and thermal dissipation.

## First engine

ZMZ-5234 V8 is the intended validation target, *not* proof of compatibility. See [engine notes](zmz-5234.md).
