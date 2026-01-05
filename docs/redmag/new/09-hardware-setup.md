## Hardware Setup

Now that you have the SSD and MP Tool, let's set up the hardware.

### Required Connections

You need to connect your SSD to your Windows computer via USB. This requires the right adapter.

### Choosing an Adapter

Not all adapters work with MP Tools. The adapter must allow "pass-through" access to the controller.

#### What to Look For

✅ **Good adapter features:**
- UASP support (USB Attached SCSI Protocol)
- "Tool-free" design
- JMicron or ASMedia bridge chips
- Recent manufacture date (2020+)

❌ **Bad adapter features:**
- Realtek chips (often block access)
- Very cheap (<$5)
- "Smart" features (auto-sleep, encryption)

#### Recommended Adapters by Form Factor

**For mSATA:**
```
Product: "Sabrent mSATA to USB 3.0"
Bridge Chip: ASMedia ASM1153E
Price: ~$15
Note: Verified to work with SMI controllers
```

**For M.2 SATA:**
```
Product: "StarTech M.2 SATA to USB 3.0"
Bridge Chip: JMicron JMS578
Price: ~$20
Note: Good pass-through, works with most MP Tools
```

**For 2.5" SATA:**
```
Product: "Sabrent USB 3.0 to SATA Adapter"
Bridge Chip: ASMedia ASM1153E
Price: ~$10
Note: Simple cable adapter, good access
```

### Step-by-Step Hardware Setup

#### Step 1: Connect the Adapter

1. Plug USB adapter into your computer
2. Wait for Windows to install drivers
3. Check Device Manager → Disk Drives
4. Should see a generic drive appear

#### Step 2: Connect the SSD

**For mSATA/M.2:**
1. Slide SSD into adapter slot
2. Secure with screw (if provided)
3. Close enclosure

**For 2.5" SATA:**
1. Connect SATA data cable to drive
2. Connect SATA power cable to drive
3. Both cables connect to adapter

#### Step 3: Verify Connection

Open **Disk Management** (Windows):
1. Press Win+X
2. Select "Disk Management"
3. Look for your drive
4. Note: May show as "Not initialized" - this is OK

**Expected:** Drive appears as a disk (Disk 1, Disk 2, etc.)
**Problem:** If no drive appears, try different USB port or adapter

### Troubleshooting Connection Issues

#### Problem: Drive Not Detected

**Solutions to try:**
1. Different USB port (try USB 3.0 AND 2.0)
2. Restart computer with drive connected
3. Try different adapter
4. Check if drive has power LED (should light up)

#### Problem: Drive Detected by Windows but Not MP Tool

**This means:**
- Adapter works for data access
- But blocks controller-level access

**Solution:**
- Need a different adapter with better pass-through
- Try adapters with JMicron or ASMedia chips

#### Problem: MP Tool Shows "No Device Found"

**Check:**
1. Is drive detected in Disk Management?
2. Are you running MP Tool as Administrator?
3. Did you use the correct MP Tool version?
4. Try closing MP Tool and reconnecting drive

#### Problem: Multiple Drives Confuse MP Tool

**Solution:**
- Disconnect other external drives
- Leave only the target SSD connected
- Some tools get confused with multiple devices

### Safety Tips

⚠️ **Important:**

1. **Don't use your system drive**
   - MP Tool should ONLY see your target SSD
   - Never point it at C: drive!

2. **Disconnect other external storage**
   - USB flash drives
   - External hard drives
   - Other SSDs

3. **Use fresh adapter**
   - Don't use adapter that has important data on other drives
   - Could accidentally format

4. **Work on non-carpeted surface**
   - Avoid static discharge
   - Use anti-static wrist strap if available

### Verifying Everything Is Ready

Before proceeding to flashing, confirm:

- [ ] SSD is connected via USB adapter
- [ ] Drive appears in Windows Disk Management
- [ ] MP Tool detects the drive (don't flash yet!)
- [ ] No other external drives connected
- [ ] Computer is plugged in (not on battery)
- [ ] You have backup of any data on the drive

**Screenshot recommended:** Take a photo of the MP Tool showing your drive detected.

---
