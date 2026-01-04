<p align="center">
  <img src="../../assets/logo.jpg" alt="openMAG logo" />
</p>

# MP Tools (what they are, why matching is hard, and how to reduce risk)

MP tools (Mass Production tools) are factory provisioning utilities used by SSD manufacturers.
They are not designed for end users and can permanently brick a drive if misused.

This page explains MP tools **at a conceptual and safety level** so you can understand the landscape and make informed decisions.

## What MP tools generally can change
Depending on controller family, MP tools may expose:
- factory-level formatting/provisioning
- internal NAND configuration and mapping parameters
- identity fields (e.g., model string) and capacity provisioning modes
- diagnostics and burn-in tests

## Why matching an MP tool is difficult
Tool compatibility is often tied to:
- controller family and exact revision
- firmware branch
- NAND vendor/process generation
- sometimes even specific board layouts

This is why two SSDs sold under the same retail name can behave differently across manufacturing batches.

## Risk model (realistic expectations)
- Wrong tool/version/config can brick the drive instantly.
- Some USB bridge adapters block low-level access.
- Malware risk exists when tools are obtained from unofficial archives.

Mitigations:
- practice on a cheap spare SSD first
- isolate the system (disconnect external drives)
- use a dedicated workstation or VM where possible
- keep logs/screenshots of every configuration state
- avoid “mystery” tools with no community confirmation

## Hardware identification (read-only strategies)
Engineers typically identify hardware via:
1. **Physical inspection** (controller marking + NAND markings)
2. **Teardown photos / known component databases**
3. **Read-only identify + SMART/log pages** (varies by platform)

## Tool selection criteria (conceptual checklist)
Before you trust any tool for your SSD family, look for:
- explicit support for your controller family and revision
- community reports confirming the same SSD revision and NAND
- the ability to verify device identification before any write action
- a way to revert to a known “factory default” profile (if supported)

> Placeholder: add community-maintained “known working SSD → evidence → notes” tables in a later doc.

## What openMAG will (and won’t) do
- ✅ document concepts, risks, and validation behaviors
- ✅ document compatibility evidence and reproducible results
- ✅ provide safe bench + camera test procedures
- ❌ provide step-by-step instructions for bypassing vendor restrictions or impersonating branded media



---

[← Safe workflow](05-high-level-process.md) | **MP tools concepts** | [Adapters + power →](07-adapters-and-power.md)
