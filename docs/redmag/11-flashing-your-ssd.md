## Flashing Your SSD

**⚠️ FINAL WARNING:**

You are about to permanently modify your SSD. If something goes wrong:
- The drive may become permanently bricked
- All data will be erased
- There is no undo
- The drive will be unusable trash

**Only proceed if:**
- You've verified all settings twice
- You're willing to lose this drive
- You understand the risks

### Pre-Flash Checklist

Go through this one more time:

- [ ] Correct MP Tool version for your controller
- [ ] Drive detected in MP Tool
- [ ] Configuration unlocked (password entered)
- [ ] Model name: Exact match from whitelist
- [ ] Capacity: IDEMA mode, matches model number
- [ ] No other external drives connected
- [ ] Computer on stable power (not battery)
- [ ] You've saved your configuration (screenshot)
- [ ] You're mentally prepared to potentially lose $30-80

**All checkboxes must be checked!**

### The Flashing Process

#### Step 1: Final Verification

Look at the MP Tool one more time:

**Device section:**
```
[√] USB Mass Storage Device
    Model: [Current model, probably gibberish]
    Size: [Current size]
```

**Configuration section:**
```
Model Name:    RED 256GB Rev T3
Capacity:      256GB (IDEMA)
Serial Number: X256T3000001
```

**Everything correct?** → Proceed to Step 2
**Something wrong?** → Go back and fix

#### Step 2: Save Configuration

Some tools require explicit saving:

1. Look for "Save Config" or "Apply" button
2. Click it
3. Tool may show "Configuration saved"

#### Step 3: Start the Flash

**The point of no return:**

1. Find the "Start" or "Flash" or "START" button
2. Take a deep breath
3. Click it

**What happens:**
```
[Starting...]
[Erasing...]
[Writing...]
[Verifying...]
[Done - PASS] or [FAIL]
```

**Duration:** Usually 10-30 seconds

**What you'll see:**
- Progress bar moving
- Status messages changing
- Maybe percentage counter

**What to do:**
- ❌ Don't touch anything
- ❌ Don't disconnect drive
- ❌ Don't close MP Tool
- ❌ Don't turn off computer
- ✅ Just wait patiently

#### Step 4: Check Result

Tool will show one of three results:

**Result 1: PASS** ✅
```
[PASS] 
Device programmed successfully
```
This is good! Move to Step 5.

**Result 2: FAIL** ❌
```
[FAIL]
Programming error
```
Drive is likely bricked. See troubleshooting.

**Result 3: Unknown/Frozen** ⚠️
Tool hangs or shows no result.
Wait 2 minutes. If still frozen, see troubleshooting.

#### Step 5: Disconnect and Reconnect

After seeing "PASS":

1. Close the MP Tool
2. Unplug the USB adapter (with SSD)
3. Wait 5 seconds
4. Plug it back in
5. Wait for Windows to recognize it

**Check in Disk Management:**
- Drive should appear
- May show new size
- May be "uninitialized" (this is OK)

#### Step 6: Verify with CrystalDiskInfo

1. Open CrystalDiskInfo
2. Select your drive
3. Check:
   - Model: Should show "RED 256GB Rev T3" (or your model)
   - Disk Size: Should show the capacity you set

**If correct:** Success! Move to testing section.
**If wrong:** Something failed. See troubleshooting.

### Success Indicators

You succeeded if:
- ✅ MP Tool showed "PASS"
- ✅ Drive reconnects after unplug/replug
- ✅ CrystalDiskInfo shows new model name
- ✅ Capacity matches what you set
- ✅ Drive is accessible in Windows

### What to Do After Success

**Don't format yet!** 

1. Take screenshot of CrystalDiskInfo showing new identity
2. Record all settings in a notebook
3. Test in camera first (next section)
4. Only format after confirming camera recognizes it

### If It Failed

#### Symptom: "FAIL" Message

**Possible causes:**
- Wrong MP Tool version
- Incompatible NAND
- Bad USB connection
- Drive defect

**What to try:**
1. Reconnect drive
2. Try again (sometimes works on second attempt)
3. Try different MP Tool version
4. Check if drive still appears in Device Manager

**If drive is gone:** It's bricked. Buy another drive and try again with different tool.

#### Symptom: Drive Not Detected After Flash

**What to check:**
1. Device Manager → Any "Unknown Device"?
2. Disk Management → Any unallocated disk?
3. Different USB port?
4. Different computer?

**If nothing works:** Drive is bricked.

#### Symptom: Wrong Model/Capacity Showing

**This means:**
- Flash "succeeded" but wrote wrong data
- Configuration wasn't saved before flashing
- Tool used cached values

**What to do:**
- Flash again with correct settings
- Make sure to click "Save Config" before "Start"

### Recovering from Common Issues

#### Issue: Drive Shows in Device Manager but Not Disk Management

**Solution:**
1. Open Command Prompt as Admin
2. Type: `diskpart`
3. Type: `list disk`
4. Find your disk number
5. Type: `select disk [number]`
6. Type: `clean`
7. Type: `exit`
8. Check Disk Management again

#### Issue: MP Tool Won't Detect Drive After Failed Flash

**Solution:**
- Try different USB port
- Restart computer with drive connected
- Try different adapter
- Use different MP Tool version (might reset)

#### Issue: Drive Becomes Read-Only

**Solution:**
Some failed flashes cause write protection:
1. Try formatting in Windows
2. If that fails, try Linux: `dd if=/dev/zero of=/dev/sdX bs=1M count=100`
3. If that fails, drive is bricked

### When to Give Up on a Drive

Drive is likely permanently bricked if:
- Not detected by any computer
- Not detected by any adapter
- Not detected by any MP Tool
- Shows 0 MB capacity
- No activity LED when connected
- Computer freezes when drive is connected

**What to do:**
- Try one more time on different computer
- If still nothing, drive is dead
- Order a new drive
- Try different MP Tool version with new drive

### Learning from Failures

If you bricked a drive:

**What to document:**
- Exact MP Tool version used
- Configuration settings
- Error message (if any)
- What adapter was used

**What to try differently:**
- Different MP Tool version
- Different drive model
- Ask forum for help before trying again

### Success Rate

**Typical success rates:**
- First attempt: 50-70%
- Second attempt (after learning): 80-90%
- With correct tool and setup: 95%+

**Common reasons for failure:**
- Wrong MP Tool version (40%)
- Bad adapter not passing commands (30%)
- User error in configuration (20%)
- Defective drive (10%)

### Moving Forward After Success

Once you've successfully flashed:

1. **Don't immediately format**
2. Test in camera first (next section)
3. Only format after camera confirmation
4. Keep notes on what worked
5. If you need more drives, buy identical model
6. Use exact same MP Tool and settings

### Multiple Drives

If you're creating several:

**Best practice:**
1. Flash one drive successfully
2. Test in camera
3. Document exact process
4. Buy more of the SAME drive model
5. Use SAME MP Tool version
6. Use SAME configuration

**Batch process:**
- Flash one at a time
- Don't try to flash multiple simultaneously
- Verify each one before moving to next

---
