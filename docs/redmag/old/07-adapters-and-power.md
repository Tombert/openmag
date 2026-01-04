<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# Adapters, Power, and External Testing

Adapters and power are the #1 cause of “camera freezes” and “random dropouts.”
Treat the physical layer as part of the engineering problem, not an afterthought.

## Power realities
- mSATA / microSATA / M.2 SATA are typically **3.3V**
- 2.5" SATA is typically **5V**

If you supply the wrong voltage, you can cause:
- lockups during enumeration
- format hangs
- clip corruption
- SSD damage

## External test setups (why they help)
External power benches are useful because they let you:
- supply correct voltage/current for the SSD
- reduce strain on camera power rails
- iterate on adapters/cabling outside the camera

Key requirements:
- shared ground between power supply and camera/data path
- strain relief for data connectors
- short, known-good cables

> Placeholder: diagrams for common bench layouts (mSATA direct, M.2 SATA, 2.5" SATA w/ 5V).

## “Data only to camera” concept
Some builders explore connecting only the SATA data path to the camera while powering the SSD externally.
This can be a useful mental model when designing custom carriers, but it increases risk if grounding and cabling are poor.
Proceed cautiously and test methodically.



---

[← MP tools concepts](06-mp-tools-overview.md) | **Adapters + power** | [Troubleshooting →](08-known-gotchas.md)
