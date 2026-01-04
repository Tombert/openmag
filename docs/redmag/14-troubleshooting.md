## Troubleshooting

Common issues and solutions:

### MP Tool Issues

#### MP Tool Won't Open

**Symptom:** Double-click, nothing happens

**Solutions:**
1. Run as Administrator (right-click → Run as administrator)
2. Check if blocked: Right-click → Properties → Unblock
3. Install .NET Framework (some tools require it)
4. Try on different Windows version
5. Check antivirus isn't blocking it

#### MP Tool Shows "No Device Found"

**Symptom:** Tool opens but doesn't see drive

**Causes & Solutions:**

**Cause 1: Wrong tool version**
- Solution: Try different MP Tool version
- Download 2-3 versions and test each

**Cause 2: Adapter blocking access**
- Solution: Try different USB adapter
- Look for adapters with JMicron or ASMedia chips

**Cause 3: Driver issue**
- Solution: Update USB drivers
- Try different USB port (2.0 vs 3.0)

**Cause 4: Drive not getting power**
- Solution: Check adapter has power LED
- Try powered USB hub

#### MP Tool Detects Wrong Drive

**Symptom:** Shows your system drive or other drives

**Solution:**
1. Close MP Tool
2. Disconnect ALL external drives
3. Leave only target SSD connected
4. Restart MP Tool
5. Verify drive letter/size matches your SSD

#### Can't Unlock Configuration

**Symptom:** Password doesn't work

**For SMI tools, try:**
- Two spaces (press spacebar twice)
- "320"
- "523"
- Blank (just press Enter)
- "admin"

**For Phison tools:**
- Usually no password
- Look for "Expert Mode" toggle

#### Flash Process Hangs

**Symptom:** Stuck at "Erasing..." or "Writing..."

**What to do:**
1. Wait 5 minutes (some are slow)
2. If no progress, close tool
3. Unplug/replug drive
4. Check if drive still works
5. Try flash again

**If repeatedly hangs:**
- Wrong tool version
- Bad adapter connection
- Defective drive

### Camera Issues

#### Camera Shows "Not Authorized"

**Already covered in Testing section, but quick recap:**

**Check:**
1. Model name exactly matches whitelist
2. Capacity matches model number
3. No typos in model name
4. Spacing is correct (64GB models need two spaces)

**Solution:** Reflash with correct settings

#### Camera Doesn't Detect Drive at All

**Possible causes:**

**1. Adapter incompatibility**
- Some adapters don't work with camera
- Try adapter from dead RED module

**2. No power to drive**
- Check power connections
- Use external SATA power supply

**3. Wrong interface**
- Ensure drive is SATA not NVMe
- Check connections are secure

#### Camera Freezes When Drive Inserted

**Cause:** Adapter incompatibility or short circuit

**Solution:**
1. Remove drive immediately
2. Power cycle camera
3. Try different adapter
4. Check for physical damage
5. Verify no pins are shorted

#### Limited Recording Options

**Symptom:** Camera works but limits resolution/frame rate

**This means:** Drive is seen but not authenticated properly

**Check:**
- Model name in camera menu
- Capacity display
- Compare to whitelist

**Solution:** Reflash with exact whitelist model name

### SSD Issues

#### Drive Not Detected After Flash

**Severity:** High (may be bricked)

**Try:**
1. Different USB port
2. Different computer
3. Different adapter
4. Device Manager check

**If nothing works:** Drive is bricked

#### Drive Shows Wrong Capacity

**Symptom:** CrystalDiskInfo shows different size than you set

**Cause:** IDEMA mode not used, or configuration not saved

**Solution:**
1. Reflash drive
2. Use IDEMA capacity mode
3. Click "Save Config" before flashing
4. Verify setting before starting flash

#### Drive Shows Wrong Model Name

**Symptom:** CrystalDiskInfo shows different model than you entered

**Cause:** Configuration not saved, or tool used cached values

**Solution:**
1. Reflash drive
2. Ensure password was entered (if required)
3. Click "Apply" or "Save Config"
4. Restart tool and verify settings before flashing

#### Drive Read-Only After Failed Flash

**Symptom:** Can't format or write to drive

**Solution:**
1. Try Windows Disk Management → Format
2. If that fails, use Diskpart:
   ```
   diskpart
   list disk
   select disk [number]
   attributes disk clear readonly
   clean
   exit
   ```
3. If still fails, drive may be bricked

#### Drive Extremely Slow

**Cause:** Failed flash corrupted performance settings

**Solution:**
- Try flash again with different tool version
- May need to accept reduced performance
- Consider buying new drive if critical

### General Issues

#### Can't Find MP Tool

**Already covered in Finding MP Tool section, but:**

**Quick resources:**
- USBDEV: http://www.usbdev.ru/files/
- HDDGuru: http://forum.hddguru.com
- Reddit r/DataHoarder: Search for your controller

**Post on forums with:**
- Controller model
- NAND type (if known)
- What you've tried

#### Adapter Compatibility

**Testing adapters:**

**Good signs:**
- Drive appears in Disk Management
- CrystalDiskInfo can read SMART data
- MP Tool detects drive

**Bad signs:**
- Drive disappears randomly
- Can't access in MP Tool
- Computer freezes when connected

**Solution:** Try 2-3 different adapters from different brands

#### Running Out of Money/Drives

**After bricking multiple drives:**

**Options:**
1. Post on forums for help (include all details)
2. Buy known-working drive (TEAMGROUP MS30)
3. Find someone local who's done it successfully
4. Consider buying used RED module instead

**Prevention:**
- Practice on cheap 128GB first
- Verify settings 3 times before flashing
- Ask forum for confirmation before flashing

### Getting Help

#### Where to Ask

**REDUser Forums:**
- URL: https://www.reduser.net
- Section: DSMC Support
- Users often help with SSD issues

**DVXuser:**
- URL: https://www.dvxuser.com
- Active RED community
- Search before posting

**Reddit:**
- r/cinematography
- r/DataHoarder
- Include "DSMC SSD" in title

#### What Information to Include

When asking for help:

```
Controller: SM2258XT
NAND: Unknown (couldn't identify)
MP Tool: SMI_MPTool_v2.8.2.1
Configuration: RED 256GB Rev T3, 256GB IDEMA
Problem: Drive shows "FAIL" after flash
Attempts: Tried 3 times, same result
Adapter: Sabrent mSATA to USB
```

**Include:**
- Screenshots of MP Tool
- CrystalDiskInfo before flash (if available)
- Exact model of SSD you bought
- What you've tried
- Error messages

**Don't include:**
- Rants about how expensive RED is
- "Please help!!!" without details
- Demands for someone to do it for you

#### Commercial Services

**If you can't do it yourself:**

Some camera service shops may offer SSD flashing:
- Call local RED service centers
- Ask on forums if anyone offers service
- Expect to pay $50-200 per drive

**Or just buy a used RED module:**
- Often cheaper than DIY after mistakes
- Guaranteed to work
- No risk of bricking

---
