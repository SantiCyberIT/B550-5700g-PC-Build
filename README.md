# Custom PC Build | Ryzen 7 5700G + ASUS TUF B550

**Hands-on hardware deployment, troubleshooting, firmware configuration, and operating system installation**

**Project type:** Independent home project  
**Outcome:** Successfully assembled, powered on, and installed an operating system on a custom desktop  
**Current use:** Windows 11 host for a VirtualBox-based IT and cybersecurity home lab

## Project overview

I built this desktop from individual components to strengthen my practical understanding of PC hardware beyond certification study. The goal was not only to assemble a functioning computer, but to understand how its components connect, identify and resolve setup issues, verify hardware detection in UEFI/BIOS, and establish a reliable workstation for further technical learning.

The finished PC became the host for my [Home IT & Cybersecurity Lab](https://github.com/SantiCyberIT/Home-IT-Lab), where I practice Windows Server, Active Directory, DNS, Windows client administration, networking, and security investigations. This build is the **hardware foundation**, not a claim of professional infrastructure-engineering experience.

## Hardware

| Component | Model / configuration |
| --- | --- |
| Processor | AMD Ryzen 7 5700G (integrated graphics) |
| Motherboard | ASUS TUF Gaming B550-PLUS WiFi II |
| CPU cooling | AMD Wraith cooler with Arctic MX-6 thermal paste |
| Memory | 32 GB Apacer DDR4 (2 × 16 GB, A2/B2 slots) |
| Storage | WD Blue SN5000 1 TB NVMe SSD |
| Power supply | Corsair RM850x, 850 W, fully modular |
| Case | Montech Air 903 Max |
| Case cooling | Three front fans, one rear fan, integrated fan/ARGB hub |
| Operating system | Windows 10 Pro initially installed; subsequently Windows 11 |

## What I implemented

1. **Prepared the work area:** Used an anti-static mat and wrist strap while handling components.
2. **Installed core hardware:** Seated the AM4 CPU, mounted the cooler, installed dual-channel RAM, and secured the NVMe drive under the M.2 heatsink.
3. **Performed a bench test:** Powered the motherboard outside the case with essential components connected to isolate hardware issues before case installation.
4. **Completed the case build:** Mounted the PSU and motherboard, checked standoff placement, routed power leads, and connected front-panel, fan, and addressable RGB headers.
5. **Validated firmware detection:** Reached the UEFI/BIOS setup screen, checked CPU, RAM, and SSD recognition, and enabled DOCP Profile 1 for the memory.
6. **Installed the OS:** Booted a Windows 10 Pro USB installer, selected the NVMe drive, and completed first-time setup.

Read the full step-by-step [build log and troubleshooting record](build-log.md).

## Verification and results

| Check | Observed result |
| --- | --- |
| External bench power-on | CPU fan spun; motherboard powered on; entered BIOS |
| Firmware hardware detection | Ryzen 7 5700G, 32 GB RAM, and NVMe SSD detected |
| Power-on after case installation | System completed POST and entered BIOS |
| Case cooling and lighting | Case fans and connected lighting powered on |
| Firmware temperature | CPU reading around the low 40s °C in BIOS |
| Memory configuration | DOCP Profile 1 enabled |
| Windows installation | Windows 10 Pro installed and initial setup completed |
| Ongoing usefulness | Desktop now supports Windows 11 and the home virtual lab |

These are **checks actually recorded during the build**, not a claim that formal benchmarks, long-duration stress tests, or exhaustive hardware validation were completed.

## Problems encountered and how I approached them

- **CPU would not seat:** Stopped rather than forcing the processor, rechecked the AM4 triangle markers, and corrected the orientation. It then seated without pressure.
- **Cooler spring screws resisted:** Applied controlled downward pressure and tightened the mounting screws gradually in an alternating pattern.
- **Mounting and header layout were unfamiliar:** Verified standoff alignment and identified the correct connectors before fastening the motherboard or powering the fan/ARGB hub.
- **Avoiding unnecessary rework:** Tested the CPU, memory, storage, and basic firmware startup on the motherboard box before installing everything into the case.

These experiences helped reinforce a repeatable habit: **verify assumptions, isolate variables, and test before moving to the next stage**.

## Skills practiced

PC component identification and installation · ESD-aware handling · AM4 CPU/cooler installation · Dual-channel RAM installation · NVMe installation · ATX power and front-panel cabling · 5 V ARGB versus 12 V RGB distinctions · UEFI/BIOS navigation · POST verification · Bootable USB installation · Basic hardware troubleshooting · Technical documentation

## Documentation and next steps

- [Detailed chronological build log](build-log.md) — assembly steps, decisions, troubleshooting, and outcomes
- [Build photos folder](Photos/) — photo evidence will be organized and integrated alongside the relevant build steps
- [Home IT & Cybersecurity Lab](https://github.com/SantiCyberIT/Home-IT-Lab) — the technical lab hosted on this PC

**Documentation scope:** This is a personal, independently completed project. Only observed steps and results are presented as completed. Future photo additions and any new diagnostic tests will be documented separately.
