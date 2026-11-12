# Validation and release gates

| Gate | Objective | Required evidence | Current status |
| --- | --- | --- | --- |
| G0 | Architecture and licensing | Requirements, design review, third-party license matrix | Open |
| G1 | Pin assignment and schematic | STM32 peripheral cross-check, ERC, design review | Open |
| G2 | Layout and BOM | DRC, thermal/current review, provenance, manufacturer DFM | Open |
| G3 | Board bring-up | Rails, clock, SWD, USB, CAN, brownout, watchdog | Open |
| G4 | Simulated engine bench | CKP/CMP sync, injectors/ignition timing, loads, fault injection | Open |
| G5 | Engine/dyno validation | Start, idle, transition, warm-up, temperatures and logs | Open |
| G6 | Product qualification | Environmental, EMC, applicable regulatory/legal evidence | Open |

## Minimum bench scenarios

- Reverse battery / supply transients / cranking simulation within a defined safe test plan.
- No accidental injector or ignition activation at power-on, reset, debugger attach or watchdog trip.
- Injectors: pulse width and sequence across rpm/load range; shorted/disconnected channel diagnostics.
- Ignition: dwell and firing timing; verify no unintended pulses.
- Crank/cam missing teeth, sensor dropout, swapped polarity, noise and recovery.
- Stuck or implausible TPS/temperature/pressure sensor signals.
- CAN disconnect/reconnect, USB session loss, invalid configuration, interrupted flash.
- DBW option: pedal mismatch, throttle sensor mismatch, motor fault and hardware shutdown.
- Heat soak, vibration, enclosure sealing and electrical noise before field release.

Document test rig, equipment, raw logs, firmware SHA, PCB revision, result and engineer sign-off in [tests/](../tests/).
