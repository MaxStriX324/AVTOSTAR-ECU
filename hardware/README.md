# Hardware (KiCad)

No schematic or PCB has been published yet. The directories below reserve a **source layout**, not fake KiCad projects.

- [common](common/): MCU, power, sensor conditioning, USB/CAN, connector library and safety blocks.
- [modules](modules/): independently tested optional DBW, WBO, EGT, knock and logging modules.
- [ecu-8](ecu-8/): first production-intent reference design.
- [ecu-6](ecu-6/): 6-channel assembly and later compact PCB.
- [ecu-4](ecu-4/): 4-channel assembly and later compact PCB.

Prefer hierarchical sheets and consistent net naming. Once created, keep project files (e.g. `.kicad_pro`, `.kicad_sch`, `.kicad_pcb`) in their respective board directory with matching hardware revision. Do not check in generated Gerbers as if they are current design sources.
