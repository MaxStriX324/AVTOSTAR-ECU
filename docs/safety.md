# Safety and regulatory engineering

**No board or firmware in this repository is currently fit for use on a running engine.**

An ECU can cause unintended throttle movement, uncontrolled injection, ignition sparks, engine damage or hazardous operation. Design and validate protections at both hardware and software levels.

## Required considerations

- Automotive input transient protection, reverse polarity, overvoltage, undervoltage and supply interruption.
- Default-OFF actuator outputs on power-up/reset/failure, independent watchdog and controlled restart.
- Current limiting and short/open-circuit behavior of injector, coil and relay drivers.
- Crank/cam loss of synchronisation, illegal sensor plausibility, ADC open/short and corrupted tune.
- Separate safety assessment for electronic throttle, including independent pedal/throttle plausibility and safe shutdown.
- Output enable and diagnostic state that remain safe if the MCU is absent, reset or firmware crashes.
- Thermal management, vibration, environmental ingress, connector retention, EMC/ESD and maintenance.
- Fuses and vehicle-specific wiring documentation.
- Safe test loads and emergency stop during bench and engine testing.

## Product claims

A functional bench test does not establish road legality. Evaluate country/market requirements for EMC, vehicle modifications, safety and emissions prior to marketing or installation. Do not claim homologation or certification without documentation.

Safety tests belong in [validation-plan.md](validation-plan.md) and must be repeated when hardware/firmware revisions change.
