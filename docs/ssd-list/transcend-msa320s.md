### Hardware Platform
Silicon Motion SM2258H Controller

### Applicable Capacities
64GB, 128GB, 256GB, 512GB

## 1. Hardware Specifications

The Transcend 230S series is an mSATA SSD that utilizes the **SM2258H** controller. Unlike "XT" (DRAM-less) variants, the 230S features a **DDR3 DRAM cache**, which is essential for maintaining sustained performance in heavy workloads.

| **Capacity** | **Model Number** | **DRAM Cache** | **Sustained Write** |
| ------------ | ---------------- | -------------- | ------------------- |
| **128GB**    | TS128GMSA230S    | 128MB DDR3     | 400 MB/s            |
| **256GB**    | TS256GMSA230S    | 256MB DDR3     | 400 MB/s            |
| **512GB**    | TS512GMSA230S    | 512MB DDR3     | 500 MB/s            |

|**Component**|**Specification**|**Notes for your Paper**|
|---|---|---|
|**Controller**|**Silicon Motion SM2258**|A mature, high-performance controller with extensive public documentation.|
|**NAND Type**|**3D TLC (Micron B16A or B27A)**|Early units typically use 64-layer (**B16A**); newer 512GB units often use 96-layer (**B27A**).|
|**DRAM Cache**|**Yes (DDR3L)**|Essential for keeping the "mapping table" in fast memory to prevent frame drops.|
|**Form Factor**|**mSATA**|Standard MO-300 form factor used internally in many proprietary cinema mags.|
|**Encryption**|**SATA Security / Hardware AES**|Supports standard security commands; may require **ROM Mode** for deep firmware access.|

---

## 2. MP Tool & Firmware Mapping

Success with the SM2258 controller depends on matching the firmware to the **NAND Flash ID**. Transcend has used different generations of 3D NAND over this product's lifecycle.

### Recommended Tool Folders

- **Micron 64-Layer (B16A) NAND:** Use folder **`SM2258_B16A_FWQ0713C_MPQ0717A`**. This is common in the 128GB and 256GB variants.
    
- **Micron 96-Layer (B27A) NAND:** Use folder **`SM2258_BiCS3_MPQ0719A_FWQ0823B`** (or a dedicated B27 version). This is typical for newer 512GB models.
    
- **Intel 3D NAND:** If the Flash ID shows Intel memory, specific **Intel-mapped** tools for the SM2258 are required.

### MP Tool Link

https://www.usbdev.ru/files/smi/sm2258mptool/

---

## 3. Implementation Steps

### Phase 1: Hardware Recognition (ROM Mode)

To perform a factory-level reflash, the controller must be in a state that accepts new instructions. If the drive is not detected:

1. **Locate ROM Jumpers:** On the Transcend 230S PCB, look for two unpopulated pads (often near the controller or NAND).
    
2. **Short the Pads:** Use tweezers to short these pads while connecting the drive to your host computer.
    
3. **Verify:** The MP Tool should report the drive as **"SMI ROM MODE"** or similar.
    

### Phase 2: Configuration (Parameter Tab)

- **Drive Identity:** You can customize the **Model Name** and **Serial Number** strings. This is where you would apply your specialized labeling for identification.
    
- **DRAM Enable:** Ensure the **"DRAM External"** option is checked. The tool should auto-detect the size (e.g., 256MB or 512MB).
    
- **Storage Optimization:** You can use the tool to set a specific **Over-Provisioning** percentage, which reserves a portion of the NAND to improve endurance and write stability.