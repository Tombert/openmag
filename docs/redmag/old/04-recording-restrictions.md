<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# Recording Restrictions (what you’ll see when validation fails)

When REDMAG validation fails, you may see one of these outcomes:
- media not detected
- media detected but unstable (freezes, disconnects, format hangs)
- media detected but recording behavior is restricted

## Typical indicators
Depending on camera model/firmware, symptoms may include:
- “not authorized” or compatibility warnings
- shorter-than-expected record duration limits
- missing recording options (resolution/frame rate) relative to what the camera should support
- recording stopping unexpectedly under load
- clips that offload but show corruption

## What causes restrictions (most common)
- model string not in whitelist
- capacity mismatch between model name and reported capacity
- unstable SATA link (adapter/cable)
- power instability (especially 5V external rigs)
- SSD sustained-write collapse (cache exhaustion/thermals)

Next page provides a repeatable workflow to isolate these variables one at a time.



---

[← Validation model + whitelist](03-redmag-validation-model.md) | **Recording restrictions** | [Safe workflow →](05-high-level-process.md)
