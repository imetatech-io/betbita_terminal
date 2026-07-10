# BetBita Terminal — Printing, Calibration & Lag Troubleshooting

This guide outlines the exact workflow required to install, test, and calibrate the **Betbita Lucky6 Terminal** application to resolve printing/barcode alignment issues, plus what to do if the app itself feels slow or laggy.

---

## 📋 Pre-Test: Clean Installation

> [!WARNING]
> To prevent old configuration states or cached settings from corrupting your test, you **must** clean up previous directories before installing the new version. Old configuration files or cached data left behind from a previous install can cause printing glitches or slowdowns even after installing a fresh copy — deleting the folder ensures the new install starts from a truly blank state.

1. **Uninstall** the existing BetBita Terminal application.
   - Windows: **Settings → Apps** (or **Control Panel → Programs and Features**), find **Betbita Lucky6 Terminal**, and uninstall it.
2. Open File Explorer or press `Win + R` (Run).
3. Type `%appdata%` and press Enter.
4. Locate the folder named **`Betbita Lucky6 Terminal`** or **`terminal`** (under Roaming) and **delete** them entirely.
5. Download and install the latest version from:
   🔗 **Download here:** [BetBita Terminal GitHub Releases](https://github.com/imetatech-io/betbita_terminal/releases)
   - Open the link, find the latest release at the top of the page, and download the installer listed under **Assets**.
   - Run the installer and follow the on-screen setup steps.

---

## 🖨️ Step 1: Printer Calibration & Safe Mode

1. On the first launch, the application will take you to the **Printer Setup** screen.
2. Select your thermal printer from the list of **Detected Printers**.
3. Toggle/enable the **Safe Mode** option.
4. Click **Test Print** and observe the output receipt margin alignment.

### Common Printing Issues

| Symptom | Likely Cause | Fix |
|---|---|---|
| Text/receipt cut off on the **left** edge | Left trim set too low | Increase **Left Trim** by `0.5mm` increments, then Test Print again |
| Text/receipt cut off on the **right** edge | Right trim set too low | Increase **Right Trim** by `0.5mm` increments, then Test Print again |
| Barcode looks squished/scaled horizontally | Printer DPI/scaling mismatch or wrong paper width selected | Re-check paper width setting in Printer Setup, redo Test Print |
| Barcode fails to scan even though it looks fine | Print head dirty, low thermal print quality | Clean the print head, try a fresh roll of thermal paper |
| Printer not appearing in Detected Printers | Driver not installed / cable or Bluetooth not connected | Reconnect cable/Bluetooth, reinstall printer driver, restart terminal app |

> [!TIP]
> Keep adjusting and clicking **Test Print** until the full boundary box and text print cleanly without cutting off on either side.

5. Click **Continue** to save these settings.

---

## 🎟️ Step 2: Live Ticket Printing Test

1. Log in to the terminal application.
2. Place a few bets (include both standard 6-number bets and **system bets of 7+ numbers** to test wrapping).
3. Print the ticket.
4. **Scan Test:** Use a hardware barcode scanner to scan the printed barcode.
   * Check if it reads successfully on the first try.
   * If it fails to scan, verify if the barcode lines look crisp or if they look horizontally squished/scaled.

---

## 🔄 Step 3: Recalibration (If Margins Fail Later)

If you change the physical printer or if margin alignment issues start again:
1. Open the bottom-left menu and click **Settings** ⚙.
2. Click **Change Printer** 🖨.
3. Repeat **Step 1** calibration adjustments.

---

## 🐢 Step 4: If the App Feels Slow or Laggy

Separate from printing issues — if the terminal app itself feels slow (screens taking long to load, buttons slow to respond, delays placing bets), here's the full troubleshooting flow.

### Types of Lag to Look Out For

| Type | Description |
|---|---|
| **UI Lag** | Screens freeze, buttons respond slowly, menus stutter when opening |
| **Network Lag** | Delays fetching odds, confirming bets, or syncing after login |
| **Print Lag** | Noticeable delay between clicking Print and the ticket coming out |
| **Startup Lag** | The app itself takes a long time to open or reach a usable screen |

### Things to Try (in order)

1. **Restart the app** — close it completely and reopen it.
2. **Check your network connection** — switch between Wi-Fi and a wired connection to see if it improves.
3. **Restart the device/machine** running the terminal — clears up memory and background processes.
4. **Update the app** — confirm you're on the latest version from the [releases page](https://github.com/imetatech-io/betbita_terminal/releases).
5. **Try again in a few minutes** — brief lag during busy periods (e.g. high ticket volume) often clears up on its own.
6. **Check the physical printer connection** — a loose USB cable or weak Bluetooth signal can look like app lag when it's actually a print-queue backup.
7. **Full clean reinstall** — if lag continues after all the above, repeat the **Pre-Test: Clean Installation** steps at the top of this guide (uninstall, delete the `%appdata%` folder, reinstall from the releases page).

### After Trying the Above

- **If the app now runs smoothly** — no further action needed.
- **If the lag is still there** — share the log files with us (see Step 5), along with:
  - **When it happened** — approximate time (e.g. "around 3:15 PM").
  - **What you were doing** — e.g. logging in, placing a bet, printing a ticket.
  - **What device/printer was involved.**
  - **Whether you already tried the reinstall above** — so we know which steps are already ruled out.

---

## 📄 Step 5: Collecting Logs

If printing, scanning, or lag issues persist, please retrieve and share the log files:

* **Log File Location:**
  * `%appdata%\Betbita Lucky6 Terminal\electron.log` OR
  * `%appdata%\terminal\electron.log`
  *(You can paste either path into Windows Run `Win + R` or the File Explorer address bar to find the folder directly.)*
* Also grab **`next-server.log`** from the same folder if present — it can contain additional detail not captured in `electron.log`.

No need to open or read the files yourself — just attach them (along with the details from Step 4) in your message to us.

---

## Quick Reference Checklist

- [ ] Clean install done (old app + `%appdata%` folder removed before reinstall)
- [ ] Correct printer selected in Printer Setup, Safe Mode enabled
- [ ] Left/Right trim adjusted until no cutoff on Test Print
- [ ] Standard + system (7+) bets tested, barcode scans on first try
- [ ] If lag reported: type of lag identified (UI / network / print / startup)
- [ ] Restart app / check connection / restart device / update app / check printer cable tried
- [ ] If lag persists: full clean reinstall done and re-tested
- [ ] If issues remain: `electron.log` and `next-server.log` collected and shared with details (time, action, device/printer, reinstall already tried)
