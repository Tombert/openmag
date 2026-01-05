# REDMAG Validations Overview

**Educational & Research Documentation**

> ⚠️ **Disclaimer**  
> This documentation is provided strictly for educational and research purposes.  
> Modifying SSD firmware, identity strings, or production parameters using manufacturer “MP Tools” is inherently risky and can permanently damage hardware.  
> You assume all responsibility for any outcome, including data loss, device failure, or equipment damage.  
>  
> This project is not affiliated with or endorsed by RED Digital Cinema.


---

## What validation means

In this context, “validation” is the camera’s decision-making process for whether a media device is:
- recognized,
- allowed to format,
- allowed to record without warnings.

Different media families can have different validation depth. REDMAG is observed to be simpler than MINIMAG.

---

## REDMAG validation model (observed)

Observed inputs:
1. **Model Number** (ATA Identify “Model” string)
2. **Reported capacity** (sector count × sector size)

Observed logic:
- Parse the capacity encoded in the model string (e.g., “256GB”).
- Compare to the SSD’s reported capacity.
- Require exact match (practically: no mismatch tolerated).

If the model string is not recognized (whitelist mismatch), or capacity doesn’t match expectations, the camera warns or rejects the media.

---

## What to document during validation research

For every test run, capture:

### Identity
- Exact model string **including spaces**
- Firmware version reported by the drive
- Serial number (optional, for tracking, not for authenticity claims)

### Capacity
- Total LBAs / sectors
- Logical sector size
- Reported “user capacity” in bytes (from a tool)
- Any adapter-specific reporting behavior

### Camera behavior
- Warning messages verbatim
- Ability to format
- Recording stability under longest clip you tested

---

## This section’s subpages

- [Whitelist Overview](whitelist-overview.md)
- [Capacity Overview](capacity-overview.md)
---

⬅️ Prev: [Hardware Guide](hardware-guide.md)  
➡️ Next: [Whitelist Overview](whitelist-overview.md)

