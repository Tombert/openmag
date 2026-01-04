<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# Known Gotchas and Troubleshooting

## Symptom: camera freezes when media is inserted
Likely causes:
- adapter signal integrity problems
- power sag during enumeration
- short/ground issue

Isolation steps:
- test SSD on a computer using the same adapter/cable
- switch to a cleaner power source
- reduce adapters and cable length

## Symptom: format fails or hangs
Likely causes:
- unstable SATA link
- power instability
- SSD firmware behavior under heavy metadata ops

Isolation steps:
- cold reboot and retry
- swap cable/adapter
- check SMART health on a computer

## Symptom: records short clips but fails under sustained load
Likely causes:
- sustained write collapse when cache is exhausted
- thermal throttling
- DRAM-less behavior

Isolation steps:
- run sustained-write tests on a computer (outside the camera)
- monitor temperature
- prefer DRAM-based SSDs with better sustained behavior

## Symptom: offloaded clips are corrupted
Likely causes:
- intermittent disconnects during record
- power instability
- adapter instability

Isolation steps:
- improve strain relief and connectors
- verify integrity with checksums
- do not treat “it played once” as proof of integrity

## Golden rule
Change **one variable at a time** and document results.



---

[← Adapters + power](07-adapters-and-power.md) | **Troubleshooting** | &nbsp;
