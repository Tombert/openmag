## Hardware Platform
Silicon Motion SM2259 Controller

## Applicable Capacities
256GB, 512GB, 1024GB (1TB)

## 1. Hardware Specifications

The **KC600** series utilizes a high-performance **Silicon Motion SM2259** (4-channel) controller paired with a dedicated **DRAM cache**. Effective initialization via MP (Mass Production) Tools requires matching the specific NAND Flash ID found on the PCB.

|**Capacity**|**Model Number**|**DRAM Cache**|**TBW Rating**|
|---|---|---|---|
|**256GB**|SKC600MS/256G|256MB DDR3L|150TB|
|**512GB**|SKC600MS/512G|512MB DDR3L|300TB|
|**1024GB (1TB)**|SKC600MS/1024G|1024MB (1GB) DDR3L|600TB|


| **Component**   | **Specification**                | **Notes for your Paper**                                              |
| --------------- | -------------------------------- | --------------------------------------------------------------------- |
| **Controller**  | **Silicon Motion SM2259**        | Premium high-performance SATA controller.                             |
| **NAND Type**   | **3D TLC (Micron B27A or B47R)** | Most modern versions use 96-layer (**B27A**) or 176-layer (**B47R**). |
| **DRAM Cache**  | **Yes (DDR3L or DDR4)**          | Crucial for cinema recording to prevent "frame dropping."             |
| **Form Factor** | **mSATA**                        | Matches the internal hardware used in **RED MINI-MAG** media.         |
| **Encryption**  | **AES-256 / TCG Opal**           | May require "ROM Mode" shorting to bypass for a reflash.              |

---

## 2. MP Tool & Firmware Mapping

To successfully reflash or re-initialize the drive, you must select the MP Tool folder that contains the firmware binary for your specific NAND generation.

### Recommended Tool Versions

- **Micron 96-Layer (B27A) NAND:** Use folder **`SM2259AB_B27_MPT1127A`**. This is the most common hardware revision for the 512GB and 1TB models produced after 2020.
    
- **Micron 64-Layer (B16A) NAND:** Use folder **`SM2259_B16_MPT0506A`**. This is typically found in early-production units or the 256GB variants.
    
- **Micron 176-Layer (B47R) NAND:** High-density 1TB units may require the **`SM2259_B47R`** specific toolset if the B27 tools fail to recognize the Flash ID.

### MP Tool Link
https://www.usbdev.ru/files/smi/sm2259mptool/

---

## 3. Implementation Steps

### Phase 1: Hardware Recognition (ROM Mode)

Because the KC600 features **AES-256 hardware encryption**, the controller may "lock" the firmware interface if it detects a critical error. To bypass this for a clean re-initialization:

1. Locate the **ROM pads** (usually labeled **JP1/JP2** or two small gold vias) on the mSATA PCB.
    
2. Use a conductive tool (tweezers) to **short these pads** while connecting the drive to the host via a USB-to-mSATA adapter.
    
3. The drive should appear in the MP Tool as "SMI ROM MODE."
    

### Phase 2: Parameter Configuration

Once the tool identifies the drive, navigate to the **Parameter** tab:

- **Drive Branding:** You can manually set the "Model Name" and "Serial Number" strings.
    
- **DRAM Settings:** Ensure "DRAM External" is enabled. For the 1TB model, the size should be set to **1024MB**.
    
- **Over-Provisioning:** You can adjust the "Disk Size" to increase longevity or meet specific system requirements (e.g., setting the 512GB unit to a 480GB logical size).