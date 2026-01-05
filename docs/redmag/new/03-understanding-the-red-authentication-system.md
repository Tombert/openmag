## Understanding the RED Authentication System

### How RED Validates Storage

The DSMC camera firmware performs two simple checks:

#### Check #1: Model Name Whitelist

The camera has a hardcoded list of approved drive model names. When you insert storage, it reads the drive's model string and checks if it's in the list.

**Example approved names:**
```
RED 256GB Rev T3
RED 512GB V4
RED 128GB Rev T1
```

If the model name isn't on the list → Camera limits features

#### Check #2: Capacity Validation

The camera parses the capacity from the model name and compares it to the drive's reported capacity.

**Example:**
```
Model name: "RED 256GB Rev T3"
Camera extracts: "256GB"
Camera expects: ~256,000,000,000 bytes (exactly)
Camera reads actual drive capacity
If they match: ✅ Approved
If they don't match: ❌ Limited features
```

### What RED Does NOT Check

Surprisingly, RED does **NOT** check:
- ❌ Serial numbers (any format works)
- ❌ Firmware versions (any work)
- ❌ SMART attributes (no crypto keys)
- ❌ Physical pin voltages
- ❌ Hidden authentication chips
- ❌ SATA generation (SATA II vs III doesn't matter)

**This makes the modification relatively simple - just two values to change!**

### Camera Firmware Limitations

The whitelist is **hardcoded in the camera firmware**. This means:

- You cannot add new model names without a firmware update
- Maximum capacity is **512GB** (highest in whitelist)
- You must use an exact model name from the whitelist
- Spacing and capitalization must match exactly

---
