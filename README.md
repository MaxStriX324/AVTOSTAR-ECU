# AVTOSTAR ECU

**Modular STM32 engine management platform**  
**Powered by MaxStriX324**

> Status: concept / hardware and firmware integration planning. This repository does **not** yet contain a tested ECU, ready-to-flash firmware, or released KiCad production files.

AVTOSTAR ECU is a planned family of programmable engine control units for 4-, 6- and 8-cylinder engines. The initial target is an **8-channel reference controller** based on **STM32F407VG** and the [rusEFI](https://github.com/rusefi/rusefi) firmware ecosystem. The first intended test engine is the ZMZ-5234 V8.

## Product family

| Model | Injector channels (planned) | Ignition outputs (planned) | Intended use |
| --- | ---: | ---: | --- |
| **ECU-4** | 4 | 4 | 1–4 cylinders |
| **ECU-6** | 6 | 6 | up to 6 cylinders |
| **ECU-8** | 8 | 8 | up to 8 cylinders; first prototype |

Proposed equipment options: **A** (mechanical throttle), **B** (electronic throttle with independent safety measures), **P** (performance/EGT/knock/lambda-related hardware). These are product concepts, **not released SKUs or validated capabilities**. Variants are described in [docs/variant-matrix.md](docs/variant-matrix.md).

## Engineering approach

- Design **one electrically verified ECU-8 baseline**, then derive ECU-6 and ECU-4 from the same documented hardware/firmware architecture.
- Keep common subsystems reusable: regulated automotive power, STM32 core, VR/Hall inputs, analog inputs, injector/ignition outputs, CAN, USB/SWD and diagnostics.
- Develop the hardware in **KiCad**, with explicit revisions, pin allocation, BOM, test procedures and manufacturing outputs.
- Adapt rusEFI through a dedicated board configuration; **do not** assume that an upstream firmware image will run unchanged on a new PCB.
- Keep source-code licensing and schematic/PCB licensing separate and explicit.

## Repository map

| Directory | Purpose |
| --- | --- |
| [hardware/](hardware/) | KiCad design source layout and reusable circuit blocks |
| [firmware/](firmware/) | rusEFI board integration, model configuration and sample tune locations |
| [docs/](docs/) | Requirements, architecture, pin allocation, roadmap, validation |
| [tests/](tests/) | Test fixtures, acceptance criteria, results |
| [bom/](bom/) | Purchasing and BOM conventions |
| [manufacturing/](manufacturing/) | Assembly, fabrication and revision tracking |
| [mechanical/](mechanical/) | Enclosure, connector and environmental requirements |

Start with [requirements](docs/requirements.md), [architecture](docs/architecture.md), [GPIO planning](docs/gpio-allocation.md), and the [roadmap](docs/roadmap.md).

## Reference software & tools

- [rusEFI firmware](https://github.com/rusefi/rusefi)
- [rusEFI custom board firmware example](https://github.com/rusefi/fw-custom-example)
- [rusEFI documentation](https://wiki.rusefi.com/)
- [KiCad](https://www.kicad.org/)
- [TunerStudio](https://www.tunerstudio.com/) (independent third-party software; distribution rights must be checked separately)

## Safety and maturity

An ECU controls a running engine. No product should be installed on a road-going vehicle or represented as fit for sale until electrical protections, fault behavior, firmware integration, bench and engine tests, EMC and any applicable legal approvals have been assessed. See [docs/safety.md](docs/safety.md) and [docs/validation-plan.md](docs/validation-plan.md).

## Licensing

**rusEFI is a separate project:** complying with its GPL obligations for distributed firmware is required. Other reference designs may have different hardware licenses. No general hardware reuse license is granted by this repository at this stage. See [LICENSING.md](LICENSING.md).

**AVTOSTAR ECU — Powered by MaxStriX324.**
