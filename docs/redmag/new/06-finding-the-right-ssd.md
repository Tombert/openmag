## Finding the Right SSD

This is arguably the **most important step**. The wrong SSD will waste your money and time.

### Strategy 1: Buy Known Working Drives

These drives have been confirmed to work:

#### TEAMGROUP MS30 (M.2 SATA)

**Specifications:**
- Form factor: M.2 2280 SATA
- Controller: Silicon Motion SM2258XT
- Available capacities: 128GB, 256GB, 512GB, 1TB
- Price: ~$30-60 depending on capacity

**Why it works:**
- Common SMI controller with excellent MP Tool support
- Widely available on Amazon
- Consistent manufacturing (usually same NAND)

**Where to buy:**
- Amazon: Search "TEAMGROUP MS30 M.2 SATA"
- Newegg
- Direct from TEAMGROUP

⚠️ **Verify:** Check seller reviews mention "SM2258XT" to ensure current batches still use this controller.

#### Dogfish mSATA

**Specifications:**
- Form factor: mSATA (full size)
- Controller: Silicon Motion SM2258XT
- Available capacities: 128GB, 256GB, 512GB
- Price: ~$25-50

**Why it works:**
- Same SMI controller as TEAMGROUP
- mSATA form factor (closer to RED's original format)
- Budget-friendly

**Where to buy:**
- Amazon: Search "Dogfish mSATA"
- Product photos often show the controller chip

⚠️ **Verify:** Look at Amazon product photos - some reviewers post photos of the circuit board showing the SM2258XT chip.

### Strategy 2: Research Before Buying

If you want to choose your own drive:

#### Step 1: Find Drives with SMI Controllers

Silicon Motion controllers have the best MP Tool support. Look for:
- SM2258XT (most common, excellent support)
- SM2259XT (newer, good support)
- SM2263XT (newer, good support)

#### Step 2: Check Product Images

On Amazon/eBay:
1. Scroll through customer review photos
2. Look for photos of the circuit board
3. Find the large controller chip
4. Confirm it says "SMI" and the model number

**What you're looking for:**
![Example of SMI chip marking]
- Large square/rectangular chip
- Text: "Silicon Motion" or "SMI"
- Model number clearly visible

#### Step 3: Search Online Forums

Before buying, search:

**HDDGuru Forums:**
```
[Drive Model] + "controller"
[Drive Model] + "SM2258XT"
```

**Reddit r/DataHoarder:**
```
[Drive Model] + "teardown"
[Drive Model] + "controller chip"
```

**LCB Club Forums:**
- Chinese forum but has detailed SSD database
- Use Google Translate
- Search by drive model

#### Step 4: Verify MP Tool Availability

Before purchasing, make sure:
1. Controller is identified (e.g., SM2258XT)
2. MP Tool exists for that controller
3. Recent users have successfully used it

**Red flags:**
- ❌ "Controller: Unknown"
- ❌ No MP Tool found in searches
- ❌ All forum posts are 5+ years old
- ❌ Samsung, SanDisk, WD branded (proprietary)

### Strategy 3: Buy Cheap, Test, Buy More

The safest approach:

1. **Buy ONE** cheap 128GB drive with SMI controller
2. **Test** that you can find the MP Tool and it works
3. **Practice** flashing it with correct settings
4. **Verify** it works in the camera
5. **Buy more** of the exact same drive model

**Cost:** ~$20-30 for practice drive

**Benefit:** Learn the process risk-free before investing in 512GB drive

### Recommended Capacities

Based on cost-effectiveness:

#### 256GB (Recommended for most users)

**Pros:**
- Sweet spot for price/capacity
- ~30-45 minutes of 4K recording
- Plenty for typical shoots
- Widely available

**Cost:** ~$30-40

**Use case:** General shooting, b-roll, interviews

#### 512GB (Maximum capacity)

**Pros:**
- Maximum the camera supports
- ~60-90 minutes of 4K recording
- Best for long-form content
- Never worry about running out

**Cost:** ~$50-80

**Use case:** Documentaries, long events, less frequent offloading

#### 128GB (Budget option)

**Pros:**
- Cheapest option
- Good for practice/testing
- Fine for short projects

**Cost:** ~$20-30

**Use case:** Testing, backup drive, short shoots

**Cons:**
- Limited recording time (~15-30 min 4K)
- Need to offload frequently

### What to Avoid

#### ❌ NVMe Drives

**Not compatible!** DSMC uses SATA interface only.

M.2 drives come in two types:
- ✅ M.2 SATA (has notch in one position)
- ❌ M.2 NVMe (has notch in different position)

**How to tell:**
- Check product specs for "SATA" not "NVMe"
- Look for "M.2 2280 SATA" or "M.2 SATA III"
- NVMe is faster but incompatible with DSMC

#### ❌ Brand Name Proprietary Drives

These manufacturers don't release MP Tools:
- Samsung (EVO, QVO, PRO series)
- SanDisk
- Western Digital (WD Blue, WD Green)
- Crucial (some models)
- Kingston (some models)

**Exception:** Some Kingston and Crucial drives use third-party controllers (Phison, SMI) and DO have MP Tools. Check carefully.

#### ❌ Used/Refurbished Drives

**Problems:**
- Unknown wear level
- May have been previously modified
- Could fail during flashing
- No warranty

**Recommendation:** Buy new drives for this project.

#### ❌ "Too Good to be True" Deals

If you find a 1TB SSD for $15:
- It's probably fake capacity
- Likely poor quality NAND
- May brick during flashing

Stick to reputable brands and sellers.

### Quick Reference: Drive Selection Checklist

Before buying ANY drive, verify:

- [ ] Form factor: mSATA or M.2 SATA (NOT NVMe)
- [ ] Controller: Silicon Motion (SM2258XT preferred)
- [ ] Capacity: 128GB, 256GB, or 512GB
- [ ] MP Tool availability confirmed
- [ ] Recent users successfully used MP Tool
- [ ] Product photos show SMI controller chip
- [ ] Sold by reputable seller
- [ ] Price seems reasonable (~$0.10-0.20 per GB)
- [ ] Can return if wrong controller

---
