## Frequently Asked Questions

### General Questions

#### Q: Is this legal?

**A:** Yes. You own the SSD and camera. Modifying firmware on hardware you own is legal in most jurisdictions. However:
- May void SSD warranty
- May violate RED's terms of service
- For personal use only

#### Q: Will RED sue me?

**A:** Unlikely. This is for personal use, not commercial distribution of modified drives. Thousands of users have done this over the years without issue.

#### Q: Does this work on other RED cameras?

**A:** This guide is specific to DSMC. Other cameras (Epic, Scarlet, Dragon, etc.) may have different authentication:
- DSMC: Model name + capacity check (simple)
- Newer REDs: May use additional checks
- MiniMAG (newer systems): Uses SMART 0x90/0x91 authentication

#### Q: How much money will I save?

**A:** Significant savings:
- RED 256GB module: $500-800 (if you can find)
- Generic 256GB SSD: $30-40
- **Savings: ~$500 per drive**

For multiple drives:
- 3x RED 256GB = $1,500+
- 3x Generic = $120
- **Total savings: ~$1,400**

#### Q: Is it worth the risk?

**A:** Depends on your situation:
- **Yes if:** You shoot frequently, need multiple drives, comfortable with tech
- **No if:** You rarely shoot, have budget for official media, risk-averse

#### Q: What if I brick a drive?

**A:** It becomes unusable:
- Can't be recovered
- Not warrantied
- Lost investment (~$30-80)
- Buy another and try again

**Mitigation:** Practice on cheap 128GB first

### Technical Questions

#### Q: Why does capacity need to match model name?

**A:** The camera firmware:
1. Parses the capacity number from model name ("256GB")
2. Reads actual drive capacity
3. Compares the two
4. Rejects if they don't match

This is the camera's only authentication mechanism.

#### Q: Do I really need to match spacing exactly?

**A:** YES! The firmware does a **string comparison**:
```
"RED 64GB Rev T1"  ≠ "RED  64GB Rev T1"
     ↑ one space       ↑↑ two spaces
```
They are different strings. Must match exactly.

#### Q: What about serial number and firmware version?

**A:** They **don't matter** for DSMC authentication:
- Serial: Can be anything (12 chars recommended)
- Firmware: Can be anything (8 chars typical)
- Camera doesn't check these fields

#### Q: Can I use NVMe drives?

**A:** No. DSMC uses SATA interface only:
- ✅ mSATA
- ✅ M.2 SATA
- ✅ 2.5" SATA
- ❌ M.2 NVMe (different protocol)

#### Q: Will SATA III drives work?

**A:** Yes! Despite DSMC being from 2007:
- SATA III is backward compatible
- Camera will negotiate SATA II speeds
- No issues with newer drives

#### Q: What about SMART attribute 0xA9?

**A:** Not required for DSMC:
- DSMC only checks model name + capacity
- SMART 0xA9 varies even on authentic RED drives
- MiniMAG (newer systems) does use SMART authentication
- But that's a different system (guide coming soon)

### MP Tool Questions

#### Q: Where do I download MP Tools safely?

**A:** Trusted sources:
1. USBDEV forum (Russian)
2. HDDGuru forum (English)
3. MyDigitalLife forums
4. Links shared on Reddit by established users

**Avoid:**
- Random download sites
- Direct downloads from search results
- Sites asking for payment
- Anything that seems sketchy

#### Q: Why are there so many MP Tool versions?

**A:** Different versions for:
- Different controller models (SM2258XT vs SM2259XT)
- Different NAND types (Micron vs Samsung)
- Different firmware generations
- Bug fixes and improvements

You need the right combination for your specific drive.

#### Q: What if I can't find the MP Tool?

**A:** Options:
1. Post on forums asking for help
2. Buy a different drive with better support (TEAMGROUP MS30)
3. Try similar controller model tools
4. Consider buying used RED module instead

#### Q: Can I use Linux/Mac?

**A:** No. MP Tools are Windows-only:
- Mac: Need Windows VM (Parallels, VMware)
- Linux: Need Windows VM (VirtualBox, QEMU)
- Or use a Windows computer

### Drive Selection Questions

#### Q: Which drive should I buy?

**A:** Recommended for beginners:
1. **TEAMGROUP MS30** (M.2 SATA) - Best support, widely available
2. **Dogfish mSATA** - Good for mSATA form factor
3. Any SMI controller drive (check reviews/forums first)

#### Q: Can I use Samsung/SanDisk/WD SSDs?

**A:** Generally no:
- These brands use proprietary controllers
- No MP Tools available
- Exception: Some OEM models use third-party controllers

#### Q: What capacity should I get?

**A:** Recommendation:
- **Testing:** 128GB (~$25)
- **General use:** 256GB (~$35)
- **Professional:** 512GB (~$60)

Consider recording time:
- 256GB ≈ 30-45 min of 4K
- 512GB ≈ 60-90 min of 4K

#### Q: Used vs. new drives?

**A:** Always buy new:
- Used may have been previously modified
- Unknown wear level
- May fail during flash
- Not worth the small savings

### Safety Questions

#### Q: Can I damage my camera?

**A:** Very unlikely:
- Camera reads drive data passively
- Wrong identity won't harm camera
- Physical damage only from bad adapter/short

**To be safe:**
- Test drives outside camera first
- Use proper adapters
- Check for shorts before connecting

#### Q: What if I mess up the flash?

**A:** Worst case:
- Drive is bricked (becomes unusable)
- Lost $30-80 on that drive
- Camera is fine
- Buy another drive and try again

**Can't be recovered:**
- No software fix
- Manufacturer won't help (warranty void)
- Need new drive

#### Q: Is there any way to practice safely?

**A:** Yes:
1. Buy cheap 128GB drive first
2. Flash it with settings
3. Test in camera
4. If successful, buy larger drives
5. Use same process

**Cost of practice:** ~$25 for 128GB drive

### Usage Questions

#### Q: Will these drives perform as well as RED modules?

**A:** Performance is comparable:
- Both use SATA II interface
- Camera is the bottleneck, not drive
- Similar read/write speeds
- Same recording times

**Difference:**
- RED modules may have better quality control
- Generic SSDs have been tested and work well

#### Q: How long will these drives last?

**A:** Similar to any SSD:
- Write endurance depends on NAND type
- Typical: 500+ hours of recording
- Monitor SMART health
- Replace when showing errors

#### Q: Can I use multiple modified drives?

**A:** Yes!
- Flash each drive separately
- Use same model name for all (or different)
- Camera treats each identically
- Good to have multiple for shoots

#### Q: Do I need to reformat between camera and computer?

**A:** No:
- Camera formats as RED proprietary format
- Reformat in camera before use
- To use on computer, reformat as exFAT
- Back and forth is fine

### Troubleshooting Questions

#### Q: My drive shows "Not Authorized" - what did I do wrong?

**A:** Most common causes:
1. Model name doesn't match whitelist exactly
2. Capacity doesn't match model number
3. Spacing is wrong (64GB needs two spaces)
4. Typo in model name

**Solution:** Reflash with correct settings

#### Q: Camera doesn't detect drive at all - now what?

**A:** Check:
1. Drive appears in Windows? (CrystalDiskInfo)
2. Adapter working? (try different one)
3. Power connected? (external power for testing)
4. Physical connection secure?

#### Q: Drive was working, now shows "Not Authorized" - why?

**A:** Unusual, but possible:
- Drive may have been reformatted incorrectly
- Corruption in drive firmware
- Physical damage

**Solution:** Reflash the drive

#### Q: MP Tool won't detect my drive - any other options?

**A:** Try:
1. Different MP Tool version
2. Different USB adapter
3. Different USB port
4. Different computer
5. Ask forums for help
6. Consider different drive model

### Cost Questions

#### Q: Total cost for DIY setup?

**A:** Breakdown:
- Generic SSD (256GB): $35
- USB adapter: $15
- RED shell (dead module): $75
- Total: ~$125

**vs. Official:**
- RED 256GB module: $500-800 (if available)
- Savings: ~$400-700

#### Q: Is it worth it for just one drive?

**A:** Marginal:
- DIY cost: ~$125
- Official used: ~$200-300
- Savings: ~$100

**More worthwhile for:**
- Multiple drives (2-3+)
- Frequent shooting
- Learning experience
- Budget constraints

#### Q: What if I brick multiple drives?

**A:** Each brick costs ~$30-40:
- 1st attempt: $35
- 2nd attempt: $35
- 3rd success: $35
- Total: $105

**Still cheaper than official!**

But emotionally draining. Practice helps.

### Future/Advanced Questions

#### Q: Will this work on RED Dragon/Epic/Scarlet?

**A:** Different authentication:
- This guide is DSMC specific
- Newer cameras use more complex checks
- MiniMAG system uses SMART 0x90/0x91
- Separate guide needed for newer systems

#### Q: Can I make 1TB drives work?

**A:** No:
- Maximum in whitelist is 512GB
- Camera firmware hardcoded
- Can't add new capacities without firmware mod
- 512GB is the limit

#### Q: What about future camera firmware updates?

**A:** Unlikely RED will update DSMC firmware:
- Camera is 15+ years old
- No longer in production
- Last update was years ago
- Whitelist probably won't change

#### Q: Can I sell modified drives?

**A:** Legal issues:
- May violate RED's trademarks
- Could be considered counterfeiting
- Personal use is fine
- Commercial sale is risky

**Better:** Share the knowledge, not sell drives

#### Q: Will RED close this loophole?

**A:** For DSMC: Unlikely
- Would require firmware update
- Camera is too old
- Community is small
- Not worth their effort

**For newer cameras:** Possibly
- They may add more authentication
- SMART checks, crypto keys
- But DIY community is persistent!

---
