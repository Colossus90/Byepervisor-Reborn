## Build notes
This payload is built using the [PS5-Payload-Dev SDK](https://github.com/ps5-payload-dev/sdk). Note also that the build for `break_hv_payload/` is slightly special, as it gets compiled to a flat binary of minimal size. The entirety of code in `break_hv_payload/` runs in supervisor/kernel mode.

The AP payload uses host-side x86-64 tools rather than the PS5 target compiler.
Override `HV_CC`, `HV_LD`, and `HV_OBJCOPY` if those tools are not available as
`gcc`, `ld`, and `objcopy`. Run `make audit-11.60` after building to check its
staging size, embedding count, privileged-opcode denylist, and guarded write
call sites.
