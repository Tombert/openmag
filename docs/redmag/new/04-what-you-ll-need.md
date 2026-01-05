## What You'll Need

### Hardware Requirements

#### 1. A Compatible SSD

**Form Factors:**
- mSATA (most common for RED)
- M.2 SATA (NOT NVMe - must be SATA)
- 2.5" SATA SSD (with adapter)

**Capacity:**
Choose based on your budget and needs:
- **256GB** - Most cost-effective, plenty for most shoots
- **512GB** - Maximum supported capacity
- **128GB** - Budget option
- **64GB** - Minimum practical size

**Controller:**
Must have a controller with available MP Tool:
- ✅ **Silicon Motion (SMI)** - SM2258XT, SM2259XT, SM2263XT (best support)
- ✅ Phison - Various models
- ✅ JMicron - Various models
- ❌ Avoid: Samsung, SanDisk, WD (proprietary, no MP Tools)

**Recommended Drives (Known Working):**
- TEAMGROUP MS30 M.2 SATA (SMI SM2258XT controller)
- Dogfish mSATA (SMI SM2258XT controller)
- *Note: Controller models may vary by batch - always verify before ordering*

#### 2. USB Adapter

You need an adapter to connect your SSD to a computer:

**For mSATA drives:**
- mSATA to USB 3.0 adapter
- Example: "Sabrent mSATA to USB 3.0" (~$15)

**For M.2 SATA drives:**
- M.2 SATA to USB 3.0 adapter (NOT NVMe!)
- Example: "StarTech M.2 SATA Enclosure" (~$20)

**For 2.5" SATA drives:**
- SATA to USB 3.0 adapter
- Example: "Sabrent USB 3.0 to SATA Adapter" (~$10)

⚠️ **Important:** Not all adapters work with MP Tools. Some block low-level access. You may need to try 2-3 different adapters to find one that works. Look for adapters that support "UASP" (USB Attached SCSI Protocol).

#### 3. Windows Computer

**Requirements:**
- Windows 7, 8, 10, or 11
- USB 3.0 port (USB 2.0 may work but is slower)
- Administrator access
- Internet connection (to download tools)

**Note:** MP Tools are Windows-only. Linux/Mac users will need a Windows VM or dual-boot.

#### 4. RED Camera Adapter (for testing)

To test your modified SSD in the camera:

**Option A: Use existing RED adapter**
- Disassemble a dead/cheap RED SSD module
- Remove the adapter PCB
- Connect your modified SSD to it

**Option B: DIY solution**
- SATA data cable connected to RED's proprietary connector
- External SATA power adapter (wall outlet)
- Temporary setup for testing

**Option C: 3D printed enclosure** (future solution)
- Custom shell that fits RED's SSD slot
- Includes proper adapter circuitry
- Not yet available but in development

### Software Requirements

#### 1. MP Tool (Mass Production Tool)

The specific tool depends on your SSD controller. You'll find and download this later in the guide.

**Common MP Tools:**
- SMI Mass Production Tool (for Silicon Motion controllers)
- Phison MP Tool (for Phison controllers)
- JMicron MP Tool (for JMicron controllers)

#### 2. Drive Information Tools

To identify your SSD's controller and NAND:

**Option 1: Flash_INFO (Recommended)**
- Download: Search "Flash_INFO tool download"
- Free utility that identifies controller and NAND
- Works on most drives

**Option 2: CrystalDiskInfo**
- Download: https://crystalmark.info/
- Free, shows detailed drive information
- May not always show controller model

**Option 3: HDDGuru**
- Website: http://hddguru.com
- Community forum with drive databases
- Search for your drive model to find controller info

**Option 4: USB Device View (USBDEV)**
- Shows USB device information
- Helps identify controller when drive is connected

### Optional But Helpful

- **Backup drive** for practice runs
- **Notepad** for recording settings
- **Digital camera/phone** for taking photos of settings
- **Multi-meter** (if testing hardware connections)

---
