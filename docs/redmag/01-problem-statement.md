# Problem Statement

RED cinema cameras that use REDMAG media rely on firmware-level validation of SSD identity.
Generic SSDs are rejected even when performance characteristics are sufficient.

The firmware checks only:
- SSD Model Number
- Reported Capacity

These values **must match exactly**. No other checks (such as 0x90h / 0x91h) are used for REDMAG.

This guide documents a research-based workflow for preparing compatible SSDs.

---
⬅️ Prev: [Overview](README.md)  
➡️ Next: [Overview](02-overview.md)
