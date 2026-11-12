# rusEFI target: avtostar-f407

**Design placeholder — not an operational build target.**

After GPIO freeze:
1. Pin rusEFI upstream commit and compare supported STM32F407 board configuration patterns.
2. Create verified board/firmware source here (or via a clearly documented submodule/fork).
3. Commit peripheral, GPIO, trigger, input-output and fail-safe configuration.
4. Document reproducible build, bootloader/DFU/SWD setup, tuning connection and firmware ID.
5. Attach tested release binaries to GitHub Releases, not to generic unverified folders.

Do not flash an upstream reference binary to AVTOSTAR hardware unless the pin and power mapping is independently confirmed.
