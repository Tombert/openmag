## Configuring the MP Tool

Now comes the actual configuration. **Read this entire section before touching anything!**

### Understanding the Interface

MP Tools vary by manufacturer, but generally have:

**Main Window:**
- Device list (shows detected drives)
- Configuration panel (where you enter settings)
- Flash button (starts the process)
- Status indicators

**Common Layout:**
```
┌─────────────────────────────────────┐
│ Device List:                        │
│ [√] USB Mass Storage Device         │
│     SM2258XT - 256GB                │
├─────────────────────────────────────┤
│ Configuration:                      │
│ Model Name:    [________________]   │
│ Serial Number: [________________]   │
│ Firmware:      [________________]   │
│ Capacity:      [Dropdown ▼]         │
├─────────────────────────────────────┤
│         [START] [STOP] [EXIT]       │
└─────────────────────────────────────┘
```

### Opening the Configuration

Most MP Tools are password-protected to prevent accidents.

#### For Silicon Motion (SMI) Tools:

**Password:** Usually **two spaces** (press spacebar twice)

**How to enter:**
1. Run MP Tool as Administrator
2. Wait for drive to be detected
3. Look for "Config" or "Settings" button
4. Click it
5. Password dialog appears
6. Press spacebar twice
7. Click OK

**Alternative passwords to try:**
- Two spaces (most common)
- "320" (some versions)
- "523" (some versions)
- Blank (just press Enter)

#### For Phison Tools:

Usually no password, but more complex interface with multiple sub-tools.

#### For JMicron Tools:

May have password or be open, varies by version.

### Critical Settings to Configure

You only need to change **TWO** settings:

#### 1. Model Name

**Where:** Usually labeled "Model Name" or "Device Model"

**What to enter:** Exact name from whitelist

**Examples:**
```
RED 256GB Rev T3    ← Use this for 256GB capacity
RED 512GB V4        ← Use this for 512GB capacity
RED 128GB Rev T3    ← Use this for 128GB capacity
```

**CRITICAL:**
- Capitalization MUST match exactly
- Spacing MUST match exactly (some have two spaces!)
- No extra characters
- Max length usually 40 characters

**Spacing reference:**
```
RED  64GB Rev T1    ← TWO spaces between RED and 64
RED 128GB Rev T1    ← ONE space
RED 256GB Rev T1    ← ONE space
```

**How to verify:**
Copy the exact string from the whitelist in this guide and paste it into the field.

#### 2. Disk Capacity

**Where:** Usually a dropdown menu labeled "Capacity" or "Disk Size"

**What to select:** The dropdown may have options like:
- Default
- IDEMA ← **SELECT THIS**
- Manual LBA
- Custom

**Selecting IDEMA:**
1. Click the Capacity dropdown
2. Select "IDEMA"
3. A new dropdown appears with size options
4. Select the size that **matches your model name**

**Examples:**
```
Model: RED 256GB Rev T3  →  Select: 256GB
Model: RED 512GB V4      →  Select: 512GB
Model: RED 128GB Rev T3  →  Select: 128GB
```

**Why IDEMA?**
- Sets exact decimal capacity (256GB = 256,000,000,000 bytes)
- This matches what RED expects
- Other options may not set precise capacity

**What if IDEMA not available?**
Some tools use different terminology:
- "Standard Capacity"
- "Decimal GB"
- "Marketing Size"

Choose the option that gives you exact GB (not GiB).

### Optional Settings (Can Leave Default)

These settings DON'T matter for RED authentication:

#### Serial Number

**Default:** Usually auto-generated
**Can change to:** Any 12-character alphanumeric string
**Examples:**
```
X256REV03001
CUSTOM000001
ANYTHING1234
```

**Recommendation:** Leave default or use something memorable

#### Firmware Version

**Default:** Usually auto-generated
**Can change to:** Any 8-character string
**Examples:**
```
AGYA0201  ← From real RED
CUSTOM01
FW123456
```

**Recommendation:** Leave default or match real RED firmware from whitelist

#### Other Advanced Settings

**Leave these alone unless you know what you're doing:**
- Performance settings
- Cache size
- Over-provisioning
- Bad block management
- TRIM settings

Changing these could brick the drive or reduce performance.

### Example Configuration (SMI MP Tool)

**Step-by-step:**

1. Run `SMI_MPTool.exe` as Administrator
2. Wait 5 seconds for drive detection
3. Click "Config" button
4. Enter password: [Press spacebar twice]
5. Click OK

**Configuration window opens:**

6. Find "Model Name" field
7. Type exactly: `RED 256GB Rev T3`
8. Find "Disk Capacity" dropdown
9. Select: `IDEMA`
10. New dropdown appears
11. Select: `256GB`
12. Find "Serial Number" field (optional)
13. Type: `X256T3000001` (or leave default)
14. Click "Save" or "Apply"

**Verify your settings:**
- Model: RED 256GB Rev T3
- Capacity: 256GB (IDEMA)
- Serial: X256T3000001

**Double-check before flashing:**
- Model name matches whitelist EXACTLY
- Capacity matches the number in model name
- No typos!

### Taking Screenshots

Before you flash:

1. Take screenshot of configuration
2. Save it as "SSD_config_backup.png"
3. Write down settings on paper
4. Take photo with phone as extra backup

**Why:** If something goes wrong, you'll know exact settings you used.

### What NOT to Do

❌ **Don't:**
- Change model to anything not on whitelist
- Mix capacities (don't use 256GB capacity with 512GB model)
- Use special characters in model name
- Change model while drive is flashing
- Disconnect drive during configuration save

### Common Mistakes to Avoid

**Mistake #1: Wrong spacing**
```
Wrong: RED 64GB Rev T1   (one space)
Right: RED  64GB Rev T1  (two spaces)
```

**Mistake #2: Capacity mismatch**
```
Wrong: Model "RED 256GB Rev T3" + Capacity 128GB
Right: Model "RED 256GB Rev T3" + Capacity 256GB
```

**Mistake #3: Extra characters**
```
Wrong: RED 256GB Rev T3_
Wrong: RED 256GB Rev T3.
Right: RED 256GB Rev T3
```

**Mistake #4: Different revision**
```
Available: RED 256GB Rev T3
Using:     RED 256GB Rev T2  ← Not in your whitelist
```

### Verification Checklist

Before clicking "Start" or "Flash", verify:

- [ ] Model name is EXACTLY from whitelist
- [ ] Capacity MATCHES the GB number in model name
- [ ] IDEMA mode selected (if available)
- [ ] Serial number format is reasonable (optional)
- [ ] No other drives are connected
- [ ] Screenshot/backup of settings taken
- [ ] Computer is plugged into power
- [ ] You've read the next section on flashing

**If any checkbox is unchecked, stop and fix it!**

---
