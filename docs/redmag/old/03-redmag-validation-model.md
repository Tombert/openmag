<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# Validation Model + Whitelist (REDMAG)

Based on firmware analysis and testing, REDMAG validation is primarily:

1. **Model string check** (exact match against a whitelist)
2. **Capacity check** (capacity implied by the model string must match the SSD’s reported capacity)

## Capacity limit
**512GB is the maximum supported REDMAG capacity** based on the highest known whitelist entry.

## Model string whitelist (exact match)
The SATA Identify “Model Number” field must match one of the following values **exactly**.

### 64GB
- RED 64GB Rev A1
- RED 64GB Rev T1
- RED 64GB Rev T2
- RED 64GB Rev T3

### 128GB
- RED 128GB Rev T1
- RED 128GB Rev T2
- RED 128GB Rev T3

### 256GB
- RED 256GB Rev T1
- RED 256GB Rev T2
- RED 256GB Rev T3

### 512GB (maximum)
- RED 512GB V1
- RED 512GB V2
- RED 512GB V3
- RED 512GB V4

Common practice is to use the latest revision (for example **RED 256GB Rev T3** or **RED 512GB V4**), but any whitelisted entry can work if the capacity check passes.

## Capacity validation (why “close enough” fails)
The camera parses the capacity from the model string (e.g., “256GB”) and compares it to the SSD’s reported capacity.
These must match **exactly**. Drives that report a slightly different usable capacity can fail validation even if marketed as the same size.

## Read-only identity collection (recommended baseline)
Before doing any experiments, collect and store:
- model string
- firmware revision string
- reported capacity (bytes, if possible)
- SMART health summary
- any controller/NAND identification you can obtain (photos + teardown reports help)

Suggested read-only tools:
- smartmontools (`smartctl`)
- Linux `hdparm -I` (identify summary)
- CrystalDiskInfo (Windows)

> Placeholder: paste example outputs and screenshots for each platform.



---

[← Storage hardware deep dive](02-redmag-storage-hardware.md) | **Validation model + whitelist** | [Recording restrictions →](04-recording-restrictions.md)
