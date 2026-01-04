<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# REDMAG Documentation

openMAG’s REDMAG docs are a **community-maintained, educational** guide to understanding REDMAG media and validating replacement SSD hardware **safely**.

This section focuses on:
- how REDMAG media is built (SATA SSD modules + pass-through PCB)
- what the camera validates for REDMAG (model-string whitelist + capacity match)
- practical, repeatable *read-only and in-camera* validation and troubleshooting
- choosing SSD hardware that behaves well for sustained cinema writing (NAND, DRAM, thermals, power)

> Note: REDMAG and MINIMAG are different systems. These docs apply to **REDMAG** only.

## Key constraints (read first)
- **Protocol:** SATA only (NVMe is not compatible)
- **Power:** camera-side is **3.3V** media power
- **Max capacity:** **512GB** (highest known whitelist entry)

## Start here
1. [What this is and why it matters](01-what-is-redmag.md)
2. [Storage hardware deep dive (connectors, voltage, NAND, DRAM)](02-redmag-storage-hardware.md)
3. [Validation model + whitelist reference](03-redmag-validation-model.md)
4. [Symptoms + recording restrictions](04-recording-restrictions.md)
5. [Safe end-to-end workflow (bench → camera → verify)](05-high-level-process.md)
6. [MP tools (concepts, selection criteria, safety)](06-mp-tools-overview.md)
7. [Adapters, power, and external test setups](07-adapters-and-power.md)
8. [Gotchas and troubleshooting](08-known-gotchas.md)



---

&nbsp; | **REDMAG Index** | [What is REDMAG? →](01-what-is-redmag.md)
