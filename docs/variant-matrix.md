# AVTOSTAR ECU model and option matrix

**Planned only — no electrical or firmware validation yet.**

| Model | Injector outputs | Ignition logic outputs | Hardware base | First use |
| --- | ---: | ---: | --- | --- |
| ECU-4 | 4 | 4 | Same core; 4 output stages populated | I3/I4 |
| ECU-6 | 6 | 6 | Same core; 6 output stages populated | I6/V6 |
| ECU-8 | 8 | 8 | All eight output stages populated | V8 ZMZ-5234 |

### Configurations

| Designator | Meaning | Design rule |
| --- | --- | --- |
| A | Mechanical throttle | Baseline sensor inputs / idle control |
| B | Electronic throttle | A + DBW drive and independent sensor plausibility/fault paths |
| P | Performance option | Additional provision for WBO/EGT/knock; not tied to throttle type |
| W | Wireless diagnostics | Explicitly optional; cannot replace required service path |
| LOG | Local data logging | Storage, wear and recovery requirements |

**Examples:** ECU-8A, ECU-8B, ECU-6A-P. Labels are provisional; none identifies an orderable product.

### Shared-assembly approach

- Revision A starts with one ECU-8 PCB and distinct BOM/assembly variants.
- Retain pin numbers and channel ordering when omitting channels.
- Unpopulated channels must never float or become enabled by a tune.
- Compact ECU-4 and ECU-6 boards are later derivations with independent release tests.
- Tune files are engine-specific; they are not interchangeable simply because the controller has the same MCU.
