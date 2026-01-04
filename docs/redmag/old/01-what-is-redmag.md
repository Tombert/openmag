<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# What is REDMAG? (10,000 ft + why it matters)

A REDMAG is SSD-based recording media used with certain RED camera generations. Physically, a REDMAG is typically:
- a standard **SATA SSD module** (commonly **microSATA** or **mSATA**)
- connected through a **RED-designed pass-through PCB**
- inside a carrier/enclosure that mates with the camera

From the camera’s perspective, the media appears as a **SATA storage device**. That has two major implications:

## 1) Compatibility is SATA-first
Only devices that speak **SATA** can work.

- ✅ microSATA / mSATA / M.2 **SATA** / 2.5" SATA (with correct power)
- ❌ NVMe (PCIe) — not SATA, even if it uses an M.2 connector

## 2) The camera enforces a “media identity + capacity” policy
The camera firmware checks whether the inserted SATA device **claims** to be an approved REDMAG model and whether the **reported capacity** matches what that model name implies.

If the checks fail, the camera may still detect the drive but can restrict recording behavior (see the next pages).

## Why this project exists
Original REDMAG SSDs are aging. Many owners want to keep otherwise functional cameras in service by replacing failing media with modern SATA SSD hardware, while **documenting the technical constraints** so the community can make safe, repeatable choices.



---

[← REDMAG Index](README.md) | **What is REDMAG?** | [Storage hardware deep dive →](02-redmag-storage-hardware.md)
