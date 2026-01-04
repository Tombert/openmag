## Whitelist Reference

Complete list of supported model names from DSMC firmware.

### REDMAGs (Internal Modules)

**Copy these EXACTLY - spacing and capitalization matter!**

#### Smallest Capacities

```
RED 16GB REV B
RED 32GB REV A1
RED 64GB REV A1
RED 55GB V1
RED 55GB V2
```

#### 64GB Models (Note: TWO spaces before "64")

```
RED  64GB Rev T1
RED  64GB Rev T2
RED  64GB Rev T3
```

#### 128GB Models

```
RED 128GB Rev T1
RED 128GB Rev T2
RED 128GB Rev T3
```

#### 256GB Models (Recommended)

```
RED 256GB Rev T1
RED 256GB Rev T2
RED 256GB Rev T3
```

#### 512GB Models (Maximum Capacity)

```
RED 512GB V1
RED 512GB V2
RED 512GB V3
RED 512GB V4
```

### SSDs (SSD Designation)

**Note: These have "SSD" suffix and different spacing**

```
RED 55GB SSD 
RED 64GB SSD 
RED 128GB SSD 
RED 256GB SSD 
RED 512GB SSD 
```

**Note:** Some have trailing space after "SSD" - include it!

### CompactFlash Cards

```
RED 16GB CF
RED 32GB CF
RED 64GB CF
LEXAR ATA FLASH CARD
```

**Note:** CF cards are obsolete format, not recommended for new projects

### Other Supported Formats

```
RedRAM
RedRAID
External Disk 0
```

**Note:** External Disk requires special serial format: `CP-5723_########_X_F`

### Recommended Models for DIY

**Best choices for generic SSD conversion:**

**For 256GB drive:**
```
RED 256GB Rev T3    ← Newest revision
RED 256GB Rev T2
RED 256GB Rev T1
RED 256GB SSD       ← SSD variant
```

**For 512GB drive (maximum):**
```
RED 512GB V4        ← Newest version
RED 512GB V3
RED 512GB V2
RED 512GB V1
RED 512GB SSD       ← SSD variant
```

**For 128GB drive:**
```
RED 128GB Rev T3    ← Newest revision
RED 128GB Rev T2
RED 128GB Rev T1
RED 128GB SSD       ← SSD variant
```

### Spacing Reference

**CRITICAL:** Some models have unusual spacing!

**64GB models (TWO spaces):**
```
RED  64GB Rev T1
RED  64GB Rev T2
RED  64GB Rev T3
    ↑↑ TWO spaces between RED and 64
```

**All other capacities (ONE space):**
```
RED 128GB Rev T1
RED 256GB Rev T1
RED 512GB V1
    ↑ ONE space between RED and capacity
```

**To verify your spacing:**
```
Wrong: RED 64GB Rev T1   (one space - will fail!)
Right: RED  64GB Rev T1  (two spaces - will work!)
```

### Quick Selection Guide

**By Budget:**

| Budget | Capacity | Recommended Model |
|--------|----------|-------------------|
| ~$25 | 128GB | RED 128GB Rev T3 |
| ~$35 | 256GB | RED 256GB Rev T3 |
| ~$60 | 512GB | RED 512GB V4 |

**By Use Case:**

| Use Case | Capacity | Model |
|----------|----------|-------|
| Short projects, testing | 128GB | RED 128GB Rev T3 |
| General shooting, events | 256GB | RED 256GB Rev T3 |
| Long-form, documentaries | 512GB | RED 512GB V4 |
| Maximum supported | 512GB | RED 512GB V4 |

### How to Copy Model Names

**To avoid typos:**

1. Copy directly from this guide
2. Paste into MP Tool configuration
3. Don't manually type
4. Verify character-by-character before flashing

**Verification tip:**
Count the spaces between "RED" and the capacity number:
- 64GB models: Count 2 spaces
- All others: Count 1 space

---
