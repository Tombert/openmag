<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# Storage Hardware Deep Dive (SATA, connectors, voltage, NAND, DRAM)

Most REDMAG “it freezes” or “it records then fails” problems come down to one of these categories:
- protocol mismatch (SATA vs NVMe)
- connector/form-factor mismatch (microSATA vs mSATA vs M.2 SATA vs 2.5" SATA)
- voltage mismatch (3.3V vs 5V)
- signal integrity / adapter quality
- SSD design choices (NAND type, DRAM cache, thermals, power-loss behavior)

## SATA protocol (what the camera speaks)
REDMAG uses **SATA**. SATA has link-speed generations (1.5/3/6 Gb/s). In practice:
- A newer SATA SSD usually negotiates down to the host’s supported speed.
- Marginal cables/adapters can cause link negotiation instability.

**NVMe is not SATA.** NVMe uses PCIe, even though it may share an M.2 connector form factor.

## Form factors and connectors (what “fits” vs what “works”)

### microSATA
- Protocol: SATA
- Typical power: **3.3V**
- Reality: many microSATA modules are discontinued; availability is limited.
- Practical note: microSATA-to-something adapters are common failure points.

### mSATA (recommended starting point)
- Protocol: SATA
- Typical power: **3.3V**
- Benefits: still available; mechanically stable; often easier to bench-test.
- This is the most approachable path for new builders.

### M.2 SATA (not NVMe)
- Protocol: SATA (must be explicitly “M.2 SATA”)
- Typical power: **3.3V**
- Warning: many M.2 drives are NVMe. **Do not assume** M.2 implies SATA.

### 2.5" SATA SSD
- Protocol: SATA
- Typical power: **5V**
- Works electrically as SATA, but **not** power-compatible with 3.3V media power.
- If you use 2.5" SATA, you must supply stable external 5V power.

## Voltage matters (3.3V vs 5V)
Camera-side REDMAG power is **3.3V**. Many SATA devices expect 5V.

Common power-mismatch symptoms:
- camera freezes during media detect or format
- intermittent disconnects during recording
- corrupted clips on offload
- “works on a computer, fails in camera”

Practical rules:
- provide the correct voltage for your SSD form factor
- use a stable, clean supply (avoid noisy converters and weak USB ports)
- ensure a **shared ground** between camera/data path and external power when bench testing

> Placeholder: add measurements for a few SSD current draws (idle vs sustained write).

## Signal integrity (why cheap adapters can lock up cameras)
SATA is high-speed signaling. Issues arise from:
- poor impedance control in adapters
- stacked adapters (more connectors, more discontinuities)
- loose connectors / strain on cables
- power noise coupling into the data path

If you must use adapters:
- keep the data path short
- avoid stacking adapters
- test with a known-good SATA cable before involving the camera

## SSD components that affect cinema recording

### Controller
The controller manages NAND, wear leveling, mapping tables, and identity reporting.
From a reliability standpoint, what matters most for cinema use is **stable sustained write behavior** and consistent latency.

### NAND types (why sustained write matters)
Cinema workloads are dominated by sustained sequential writes with occasional bursts.
NAND types:
- **SLC**: rare/expensive; excellent endurance and consistency
- **MLC**: generally excellent for sustained writes (often ideal)
- **TLC**: can work well; quality varies by firmware and cache design
- **QLC**: typically poor sustained writes; **not recommended** for recording media

### DRAM cache (strongly recommended)
DRAM helps the SSD maintain mapping tables and stable latency.
DRAM-less SATA SSDs may:
- benchmark fine in short bursts
- suffer sharp sustained-write drops when cache is exhausted
- show inconsistent write latency (risk for dropped frames)

Recommendation: prefer SSDs with **onboard DRAM** for REDMAG replacement media.

### Thermals and throttling
Small form factors (mSATA/M.2) can heat-soak under sustained writes.
Thermal throttling can appear as:
- recording that starts fine then fails later
- sudden performance collapse mid-take

Mitigations:
- airflow
- thermal pads to the carrier (if safe)
- use SSDs known for stable sustained writes

### Power-loss behavior (PLP)
Enterprise SSDs may include power-loss protection (capacitors) that help protect mapping data.
Consumer drives typically do not.
For camera media, PLP is beneficial but not required; stable power and safe handling matter most.



---

[← What is REDMAG?](01-what-is-redmag.md) | **Storage hardware deep dive** | [Validation model + whitelist →](03-redmag-validation-model.md)
