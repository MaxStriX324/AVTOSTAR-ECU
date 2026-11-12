# STM32F407VG pin and peripheral allocation

**Unassigned worksheet.** Do **not** route KiCad or publish firmware until the mapping is reviewed. The STM32F407VG pin count and electrical limits must be checked against the precise package/datasheet.

| Block | Signals to allocate | Resource / constraints to verify |
| --- | --- | --- |
| Injection | INJ1–INJ8 | Engine timing, default-OFF, output stage interface |
| Ignition | IGN1–IGN8 | Accurate scheduling, buffer/driver interface, default-OFF |
| Engine position | CKP, CMP1, CMP2 (proposed) | Timer capture/EXTI, VR/Hall conditioning |
| Sensors | MAP, TPS, CLT, IAT, VBAT, AUX1–AUXn | ADC channels, sampling times, input divider/protection |
| DBW option | APS1/2, TPS1/2, motor drive/diagnostics | Redundant inputs, H-bridge, watchdog and faults |
| Actuators | FUEL_PUMP, FAN, IDLE, VVT1/2, AUX_PWM | Timers, frequencies, protected drivers |
| Network | CAN1, optional CAN2 | TX/RX AF pins, transceiver, termination |
| Service | USB FS, SWDIO, SWCLK, NRST, BOOT | Programming, boot recovery, ESD |
| Logging | SD / external memory (optional) | SPI/SDIO, bandwidth, collisions |
| Other | WBO, EGT, knock (optional) | Interfaces determined by actual IC selection |

## Mandatory pin allocation checks

1. Compare alternative functions with the STM32F407VG datasheet for the exact package.
2. Ensure no timer, ADC, SPI, USB, CAN or debug pin conflict in every variant.
3. Capture active voltage level and reset behavior for every output.
4. Define fault-safe pull-ups/pull-downs independent of firmware.
5. Build a cross-reference: **schematic net → STM32 pin → firmware GPIO → test point → connector pin**.
6. Freeze the mapping only after a small bench firmware build and I/O tests.

No GPIO assignments in this repository are certified or bench verified yet.
