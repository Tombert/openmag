<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# End-to-End Workflow (bench → camera → verify)

This workflow is designed to be safe, repeatable, and beginner-friendly.
It focuses on **verification and isolation**, not shortcuts.

## Phase A: Establish a known-good baseline
1. With a known-good REDMAG:
   - confirm the camera detects media reliably
   - format in-camera (optional)
   - record a short clip
   - record a longer clip (stress test)
   - offload and verify

Record:
- camera model
- camera firmware version
- media model string shown in-camera
- any warnings shown

## Phase B: Bench inspection (read-only)
Before involving the camera, connect your candidate SSD to a computer and collect identity/health information (read-only):
- model, firmware, capacity
- SMART summary
- temperature under light load (if available)

If the SSD is unstable on a computer, it will not be stable in a camera.

## Phase C: Build a stable test bench
Goal: reduce variables.

- Use a short, known-good data path.
- Avoid stacked adapters.
- Use correct power for the SSD (3.3V vs 5V).
- Ensure a shared ground if using external power.

## Phase D: Camera validation sequence (repeat after each change)
Use the same sequence every time you change anything:

1. Insert media and confirm detection
2. Format in-camera
3. Record a short clip (sanity test)
4. Record a longer clip (stress test)
5. Offload clips to a computer
6. Verify integrity (hash/checksum if possible)
7. Reboot the camera and repeat (consistency test)

## Phase E: Document results for the community
For a report to be useful, include:
- exact SSD model + photos of PCB/chips if possible
- connector type and adapters used
- power setup details
- camera model/firmware
- which tests passed/failed (with timestamps)



---

[← Recording restrictions](04-recording-restrictions.md) | **Safe workflow** | [MP tools concepts →](06-mp-tools-overview.md)
