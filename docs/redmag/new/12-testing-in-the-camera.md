## Testing in the Camera

Now comes the moment of truth - will the camera accept your drive?

### Initial Testing Setup

**Don't install permanently yet!** Use a temporary test setup:

#### Option 1: Bench Test with Camera Adapter

**Materials:**
- Your flashed SSD
- RED SSD shell (from dead/cheap module)
- SATA data cable
- External SATA power supply (wall adapter)

**Setup:**
1. Connect SSD to RED adapter's data connector
2. Connect external power to SSD
3. Leave RED's power disconnected for now
4. Power on the camera
5. Insert the adapter

#### Option 2: Direct Connection (if possible)

Some DSMC cameras allow temporary direct connection for testing.

**Check your camera manual for test port locations.**

### First Power-On

**What to watch for:**

#### The Camera Menu

Power on camera and navigate to:
```
Menu → Media → Media Info
```

**What you should see:**
```
Active Media:     S-SSD
Model Number:     RED 256GB Rev T3
Serial Number:    X256T3000001
Firmware Version: AGYA0201
Size:            223.5 GiB
```

**Status indicators:**

✅ **Success:** Camera shows your model name exactly
✅ **Success:** Shows full size
✅ **Success:** No "not authorized" message

❌ **Failure:** "Not authorized" appears
❌ **Failure:** Limited resolution options
❌ **Failure:** Model shows as "Unknown"

### Verification Checklist

Go through each point:

#### 1. Media Recognition

- [ ] Camera detects the SSD (shows in Media menu)
- [ ] Model name displays correctly
- [ ] Capacity shows correctly (may be slightly less than nominal)

#### 2. No Restrictions

- [ ] No "not authorized" message appears
- [ ] Full resolution available in recording settings
- [ ] High frame rates available

#### 3. Recording Test

- [ ] Can arm the camera for recording
- [ ] Record button works
- [ ] Records for at least 10 seconds
- [ ] Can play back the clip
- [ ] No errors during recording

#### 4. Format Test

- [ ] Can format the SSD from camera menu
- [ ] Format completes successfully
- [ ] Can record after format

### If Camera Shows "Not Authorized"

**This means:**
- Camera detected the drive
- Model name or capacity doesn't match expectations

**Debug steps:**

#### Step 1: Check Model Name

In Camera Media Info:
- Does it show EXACTLY your programmed model?
- Or does it show something different?

**If different:** MP Tool flash didn't work correctly. Reflash.

#### Step 2: Check Capacity

In Camera Media Info:
- Does the size roughly match model name?
- Example: "RED 256GB" should show ~223-240 GiB

**If way off:** Capacity wasn't set correctly. Reflash with IDEMA mode.

#### Step 3: Check Spacing

Compare camera display to whitelist:
```
Camera shows: RED 64GB Rev T1   (one space)
Should be:    RED  64GB Rev T1  (two spaces)
```

**If spacing wrong:** Model name has typo. Reflash with correct spacing.

### If Camera Doesn't Detect Drive

**Possible causes:**

#### 1. Physical Connection

Check:
- Is adapter fully inserted?
- Is data cable connected properly?
- Is power connected?
- Try reseating everything

#### 2. Adapter Compatibility

The adapter you use for testing might not work with camera:
- Some USB adapters don't properly convert signals
- RED's native interface may be incompatible
- Try different adapter

#### 3. SSD Format

Camera might expect specific format:
- Try formatting in camera
- Try different file system

### Recording Tests

Once camera accepts the drive, test actual recording:

#### Test 1: Basic Recording

**Settings:**
- Resolution: 2K
- Frame rate: 24fps
- Compression: RED RAW 8:1

**Test:**
1. Arm camera (R key)
2. Record for 30 seconds
3. Stop recording
4. Play back clip

**Expected:** Clean recording, no errors

#### Test 2: High Resolution

**Settings:**
- Resolution: 4K (maximum available)
- Frame rate: 24fps
- Compression: RED RAW 8:1

**Test:**
1. Record for 60 seconds
2. Check for dropped frames
3. Verify playback

**Expected:** Camera doesn't limit resolution

#### Test 3: High Frame Rate

**Settings:**
- Resolution: 2K
- Frame rate: 120fps (maximum available)
- Compression: RED RAW 8:1

**Test:**
1. Record for 10 seconds
2. Check recording is smooth
3. Verify frame count

**Expected:** High frame rates available

### Performance Verification

Compare to RED's spec sheet:

**4K Recording:**
- Should sustain for full card duration
- No thermal throttling (for reasonable duration)
- Consistent write speeds

**2K Recording:**
- Should sustain longer durations
- Higher frame rates available
- Smooth playback

### What Success Looks Like

**Perfect success:**
```
✅ Camera shows: "RED 256GB Rev T3"
✅ Capacity: ~223-240 GiB
✅ Status: (No "not authorized" message)
✅ Resolution: 4K available
✅ Frame rate: Up to 120fps
✅ Recording: Smooth, no errors
✅ Playback: Perfect
```

### Troubleshooting Camera Detection

#### Symptom: Camera Freezes When Drive Inserted

**Cause:** Adapter incompatibility or power issue

**Solution:**
- Remove drive immediately
- Check power connections
- Try different adapter
- Some adapters cause camera lockups

#### Symptom: "Media Error" Message

**Cause:** File system issue or corrupted format

**Solution:**
1. Format drive in Windows (exFAT)
2. Reinsert in camera
3. Format again in camera menu
4. Try recording

#### Symptom: Works But Limited Resolution

**Cause:** Model name or capacity incorrect

**Solution:**
- Verify exact model name in camera menu
- Compare to whitelist
- Check capacity matches model number
- May need to reflash

### Final Verification

Before considering the project complete:

**Test session:**
1. Record 5 minutes of 4K footage
2. Remove and reinsert drive
3. Playback the footage
4. Record 5 more minutes
5. Offload to computer
6. Verify files are intact

**If all tests pass:** Your SSD is ready for production use!

---
