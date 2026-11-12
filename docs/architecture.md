# System architecture — AVTOSTAR ECU

## Baseline design philosophy

Create a complete and electrically validated 8-channel hardware reference first. ECU-4 and ECU-6 become **reduced-assembly variants** before separate compact layouts are attempted. Do not create unrelated firmware forks for each model.

```text
                  +-----------------------------+
Battery / ignition -> Protection / power rails --+---> STM32F407VG
                  |                             |      | USB/SWD
Crank & cam ------+-- VR/Hall front-end --------+      | CAN 1 (+ optional CAN 2)
Analog sensors ---+-- ADC conditioning --------+      | Engine scheduler / diagnostics
                  |                                    |
                  +-- Injector drivers 1..8 <----------+
                  +-- Logic ignition buffers 1..8 <----+
                  +-- Relay/PWM protected drivers <----+
                  +-- Optional hardware modules <------+
                         DBW / WBO / EGT / knock / SD
```

## Hardware domains

| Block | Common to | Design notes |
| --- | --- | --- |
| Power supply/protection | All | Reverse battery, jump start, transient suppression, brownout, watchdog |
| STM32 core | All | STM32F407VG assumed for first revision; clock, reset, SWD, boot |
| Synchronisation | All | VR/Hall input conditioning, filtering, signal diagnosis |
| Sensors | All | Protected analog inputs, dedicated 5 V sensor supply |
| Injectors | Variable 4/6/8 | High-impedance injector baseline; power-stage design still open |
| Ignition | Variable 4/6/8 | Logic-level outputs to externally protected smart coils |
| Network | All | CAN1 required; CAN2 optional; USB service |
| DBW / EGT / knock / WBO | Optional | Independent schematics and functional safety plan |

**STM32F405VG is a candidate alternative**, not a drop-in firmware guarantee. Board variants must pass pin/peripheral and firmware tests.

## Configuration principle

A documented single GPIO numbering scheme maps 1–8 outputs in order. Hardware model controls populated channels and valid features; engine tune controls cylinder count and firing order. Model compatibility must be checked at build time and in production tests.

See [GPIO allocation](gpio-allocation.md), [variants](variant-matrix.md) and [rusEFI integration](rusefi-integration.md).
