# Reference implementations and provenance register

References are for **study and comparison**. A link is not a license grant.

| Source | Relevance | Required action before copying |
| --- | --- | --- |
| [rusEFI firmware](https://github.com/rusefi/rusefi) | Core engine control and board support | Pin exact revision; comply with source licenses |
| [fw-custom-example](https://github.com/rusefi/fw-custom-example) | Custom firmware target skeleton | Review source license and compatibility |
| [Proteus hardware](https://github.com/mck1117/proteus) | Full-feature ECU architecture | Verify explicit PCB/schematic license and revision |
| [microRusEFI hardware](https://github.com/rusefi/hw_microRusEfi) | KiCad blocks and manufacturing approach | Verify licensing of all copied design files |
| [Frankenso hardware](https://github.com/rusefi/rusefi-hardware) | Legacy MCU, injection and input concepts | Confirm legal rights; treat as legacy reference |
| [SCG-ECU 2.0](https://github.com/dvjcodec/SCG-ECU-2.0-STM32F407-8x8) | STM32F407 8x8 topology | Commercial derivative use requires separate permission if NC-licensed |

Before incorporating third-party assets, document source repository, commit/tag, file path, SPDX/license, modifications and required attribution in an engineering decision record. Do not import a reference PCB just because it is downloadable.
