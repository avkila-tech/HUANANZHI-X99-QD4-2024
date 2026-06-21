# Huananzhi X99-QD4 V0.169H Modded BIOS

**Developer:** Avkila  
**Status:** Tested / Working 20.06.2026

---

### 🛠 Changelog
* **Resizable BAR:** Injected RebarDxe driver.
* **Boot Optimization:** Memtest and slow diagnostic routines are killed, allowing the motherboard to boot way faster than before.
* **Overclocking:** Overclocking lock has been completely removed.
* **Memory Configuration:** Memory tuning lock/mod has been removed.
* **Power Limits:** VRM current ampere limit has been removed (turned off by default; users can manually enable this themselves in the BIOS if needed).
* **Logo Customization:** The default boot image has been swapped out with a custom purple burning heart splash screen.
* **Turbo Boost Unlock:** NO.
* **BCLK Fix:** Completely killed Intel Management Engine (ME) BCLK downspread. Your BCLK is fixed at 100MHz now instead of downspreading to 99.78MHz. *(Note: It may still show up as 99.98MHz. That is basic physics.)*

### ⚡ Power & Overclocking Guidance
* **Power Limit Safety:** Any CPU that is E5 26XX V3, V4, or E5 16XX V4 is safe to use. However, on overclockable chips such as the E5 1650V3, 1660V3, 1680V3 and their i7 counterparts, I recommend being extra careful with the VRM temperatures since overclocking on these boards is a bit tricky.
* **Stable Overclocking:** Unlock the power limit if you want to get rid of the "Power Current Limit" constantly slowing your CPU down. Doing so will significantly increase your VRM temperatures, so I highly recommend having a good directed airflow source on the VRM heatsink. Please add a reasonable manual power limit instead of setting it to infinite.

> [!CAUTION]
> **CSM MUST BE OFF:** You must disable CSM (Compatibility Support Module) in the BIOS. The RebarDxe driver will cause a boot failure/hang if CSM is enabled. Ensure your OS is on a **GPT** partition. If you absolutely need to boot on Legacy video, please reset your CMOS by removing the CR2032 battery from the motherboard. The ReBarDXE driver will not work if your date and time is set before 2024. If you do not want to use ReBAR but would like to boot on UEFI, do NOT enable Above 4G Decoding OR do NOT set a value from "rebarstate.exe"

---

### 💾 File Verification
**Avkila's Modded ROM (`avkila'smodified.rom`)**
* **SHA-256:** `32ea41e118010492dfff748b8ba759037cd16d7995a4e11344da6a4dfead3b7f`
* **MD5:** `73db1c792fe3320ea68a3a8329bda037`

**Stock Image (`QD4V10.bin`)**
* **SHA-256:** `69e976a4e2b13963c399a4fa887c6eb44bdb0be41783effc32eea78c9f7bd128`
* **MD5:** `ab99cc2cd00672f71672ed7d6418931c`

---

### 🤝 Credits
* **Stock ROM:** Huananzhi Official Website.
* **Modded by:** Avkila
* **Tested by:** ME :D I own the board!
* **Flashing Method:** FPTW64 from my `ALL-X99-BIOS-TOOLS` repo. Use command: `fptw64.exe -f avkila'smodified.rom`

**Disclaimer:** This firmware is provided as-is. I will not take any responsibility for bricking your motherboard, but I will happily help you recover it if you ask me nicely. Always have a CH341A programmer and a backup of your original ROM ready.

---

### ⚠️ Avkila's Personal OC Profiles
> [!WARNING]
> **DO NOT MIRROR WITHOUT TESTING.** These specific profiles work on my silicone layout but may not work on yours. Copying blindly may cause boot failures, instability, or permanent hardware damage to your VRMs or CPU.

#### Intel Xeon E5 1650 V3
* **Core:** 4.6GHz @ 1.45V
* **Cache:** 3.6GHz @ 1.35V
* **Power Limit:** 230W
* **Current Limit:** 256A (`iccmax 2048/8`)

#### Intel Xeon E5 1660 V3
* **Core:** 4.4GHz @ 1.42V
* **Cache:** 3.4GHz @ 1.315V
* **Power Limit:** 190W
* **Current Limit:** 256A (`iccmax 2048/8`)
