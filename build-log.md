# Build Log – Custom PC (Ryzen 7 5700G + ASUS TUF B550-PLUS WiFi II)

This file is a chronological log of building my PC from parts, including the small issues, confusion, and what I learned along the way.

---

## 1. Parts Overview

**Core components:**

- CPU: AMD Ryzen 7 5700G
- Cooler: AMD Wraith stock cooler + Arctic MX-6 thermal compound (4g)
- Motherboard: ASUS TUF Gaming B550-PLUS WiFi II
- RAM: 32 GB DDR4 (Apacer, 2x16 GB)
- Storage: WD Blue SN5000 NVMe SSD (1 TB)
- PSU: Corsair RM850x (850W, fully modular)
- Case: Montech Air 903 Max (3x front fans, 1x rear fan, fan/RGB hub)

---

## 2. Workspace & ESD Prep

- Used an anti-static mat on the desk.
- Wore an anti-static wrist strap and clipped it to a grounded part of the case/PSU.
- Initially placed components on their boxes and anti-static bags while working.

---

## 3. CPU Installation

1. Opened the AM4 socket lever on the ASUS TUF B550-PLUS WiFi II.
2. Identified the triangle on the CPU and the triangle marker on the socket.
3. Took extra time here because the orientation was confusing at first:
   - At one point it felt like the CPU would not “drop in” and it looked like the wrong size.
   - Eventually realized the triangle orientation and alignment were off.
4. Once aligned correctly:
   - CPU dropped into the socket with **no force**.
   - Lowered and locked the retention lever.

**Lesson:** If the CPU doesn’t drop in easily, stop and recheck the triangle orientation. Don’t push.

---

## 4. Thermal Paste & Cooler Mounting

1. Cleaned the pre-applied thermal paste off the Wraith cooler using:
   - Lint-free cloth / paper towel
   - 90%+ isopropyl alcohol
2. Applied fresh Arctic MX-6 thermal paste:
   - Used a small pea-sized dot in the center of the CPU.
3. Removed AMD’s plastic mounting brackets on the motherboard.
4. Aligned the cooler over the CPU and used the spring screws to secure it:
   - Tightened in an alternating pattern (a few turns per side).
   - Needed to apply some downward pressure to compress the springs and start the threads.
5. Connected the cooler’s fan cable to the **CPU_FAN** header.

**Lesson:** The cooler will fight you a bit with the springs. Tighten gradually and alternate sides.

---

## 5. RAM Installation

1. Located DIMM slots A1, A2, B1, B2.
2. Installed RAM in the recommended **A2 and B2** slots for dual-channel:
   - Opened the single moving latch side on each slot.
   - Aligned the notch in the RAM with the slot key.
   - Pressed firmly until the latch clicked.

**Lesson:** Some boards only have one side that clips – that’s normal.

---

## 6. NVMe SSD Installation

1. Identified the M.2 slot and its heatsink on the board.
2. Removed the M.2 heatsink cover.
3. Inserted the WD Blue SN5000 at a ~30° angle into the slot.
4. Pressed the drive down and secured it with the M.2 screw.
5. Reinstalled the heatsink over the SSD (making sure the thermal pad contacted the drive).

**Lesson:** The M.2 area can be confusing when there are multiple covers. Take time to confirm which one is the actual slot.

---

## 7. Breadboarding (Test Boot Outside the Case)

To avoid building everything in the case and then discovering a dead part, I did a breadboard test:

1. Placed the motherboard on top of the **motherboard box** (stable, non-conductive).
2. Connected:
   - 24-pin ATX power from PSU to motherboard
   - 8-pin CPU power
   - CPU cooler to CPU_FAN header
   - One RAM stick initially (then both)
3. Connected monitor to motherboard HDMI.
4. Used a screwdriver to briefly short the **PWR_SW** pins on the front panel header to power it on.
5. Result:
   - CPU fan spun up
   - Board powered on
   - Entered BIOS successfully
   - Verified:
     - CPU recognized (Ryzen 7 5700G)
     - RAM recognized (32 GB)
     - NVMe SSD detected

**Lesson:** Breadboarding first is worth it. It confirms the core components work before dealing with case wiring.

---

## 8. Case Prep & PSU Installation

1. Identified case orientation:
   - Front = 3x Montech fans
   - Top = power button, USB ports, audio jacks
   - Back = I/O cutout + PCIe slots
   - Bottom = PSU area with dust filter
2. Installed the Corsair RM850x PSU:
   - Fan facing **down** toward the bottom mesh/filter.
   - Secured PSU with 4 screws at the back.
3. Routed PSU cables through the back side (cable management side):
   - 24-pin ATX
   - 8-pin CPU power
   - SATA power cable (for fan/RGB hub)
   - Any extra PCIe/SATA cables were left available for future use.

---

## 9. Motherboard Installation in Case

1. Opened both side panels (glass and metal).
2. Verified that the case had **9 standoffs** and that they aligned perfectly with the **9 mounting holes** on the motherboard.
3. Installed the ASUS I/O shield from inside the case into the back cutout.
4. Carefully lowered the motherboard into the case:
   - Ensured rear I/O ports lined up with the shield.
   - Ensured screw holes sat correctly over the standoffs.
5. Installed the motherboard screws:
   - Started all screws loosely.
   - Then tightened them snugly (not over-torqued) in a cross pattern.

**Lesson:** Extra standoffs with no matching hole are a short risk. In this case, the standoffs matched perfectly, so no changes were needed.

---

## 10. Fan & RGB Hub Wiring

The case includes a pre-installed Montech fan/RGB hub behind the motherboard tray.

Steps:

1. Connected the hub’s **SATA power** cable to a SATA power lead from the PSU.
2. Verified all case fans were plugged into the hub.
3. Connected the hub’s **fan control cable** to a **CHA_FAN** header on the motherboard.
4. Connected the ARGB cable from the hub to a **+5V ADD_GEN2** (5V ARGB) header on the motherboard for lighting control.

**Lesson:**  
- Fan hubs typically need:
  - PSU → SATA power  
  - Motherboard → single fan header (CHA_FAN) for RPM/control  
- ARGB is **3-pin 5V**, not 4-pin 12V RGB.

---

## 11. Front Panel & I/O Connections

1. Connected **front panel headers** to the F_PANEL header:
   - POWER SW → PWR_SW pins
   - RESET SW → RESET pins
   - POWER LED + and – → PLED+/PLED- pins
2. Connected:
   - HD_AUDIO cable to the AAFP / HD_AUDIO header
   - USB 3.0 front panel connector to the USB3 header (if available)
   - USB-C or extra USB headers if supported by the motherboard
3. Double-checked that no cables were under the motherboard and that everything routed cleanly.

---

## 12. First Power-On in Case

1. Plugged in power cable and switched PSU to **I (on)**.
2. Pressed case power button.
3. Observed:
   - All case fans spinning
   - CPU fan spinning
   - RAM RGB lighting active
   - Case/RGB lighting active
4. System POSTed successfully and entered BIOS.

---

## 13. BIOS Configuration

1. Confirmed:
   - CPU: Ryzen 7 5700G detected
   - RAM: 32 GB detected
   - NVMe SSD: WD Blue SN5000 detected
   - Temps:
     - CPU ~ low 40s °C in BIOS (normal)
2. Enabled **DOCP Profile 1** to run RAM at its rated speed (instead of 2133 MHz).
3. Verified boot priority and UEFI mode for OS installation.

---

## 14. Windows 10 Pro Installation

1. Created a **Windows 10 USB installer** on a SanDisk flash drive.
2. Booted from USB using the boot menu (F8).
3. Chose **Windows 10 Pro**.
4. When prompted for a key:
   - Selected **“I don’t have a product key”** to continue without activation.
5. Selected **Custom: Install Windows only (Advanced)**.
6. Deleted any partitions on the NVMe until it showed:
   - **Drive 0 Unallocated Space**
7. Selected the unallocated space and clicked **Next**.
8. Let Windows copy files and reboot multiple times.
9. Completed Windows setup (region, keyboard, user account).

---

## 15. Post-Install Plans (To Do)

- Install latest chipset drivers from ASUS/AMD.
- Run Windows Updates.
- Install monitoring tools (HWInfo, CPU-Z, etc.) and stress-test the system.
- Set up:
  - Virtualization / lab environment
  - Security tools and network labs for cybersecurity practice.
- Optionally revisit BIOS to:
  - Confirm boot order
  - Enable Secure Boot after Windows is fully installed.

---

## 16. Summary

This build went from:
- Unboxing parts
- Confusion around CPU orientation, case layout, standoffs, and hub wiring
- Breadboard testing
- Full case install
- Successful BIOS POST and Windows 10 Pro install

to a fully functioning system I can now use for IT labs and daily work.

This repo serves as a **technical build log** and a reference for future builds and troubleshooting.
