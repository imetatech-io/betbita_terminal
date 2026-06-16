# BetBita Terminal Printing & Calibration Testing Steps

This guide outlines the exact workflow required to install, test, and calibrate the Betbita Terminal application to resolve the printing and barcode alignment issues.

---

## 📋 Pre-Test: Clean Installation

> [!WARNING]
> To prevent old configuration states or cached settings from corrupting your test, you **must** clean up previous directories before installing the new version.

1. **Uninstall** the existing BetBita Terminal application.
2. Open the File Explorer or press `Win + R` (Run).
3. Type `%appdata%` and press Enter.
4. Locate the folder named **`Betbita Lucky6 Terminal`** or **`terminal`** (under Roaming) and **delete** them entirely (also delete the **`presentation`** folder if the presentation screen was installed).
5. Download and install the pre-release version from:
   🔗 [BetBita Terminal GitHub Releases](https://github.com/imetatech-io/betbita_terminal/releases)

---

## 🖨️ Step 1: Printer Calibration & Safe Mode

1. On the first launch, the application will take you to the **Printer Setup** screen.
2. Select your thermal printer from the list of **Detected Printers**.
3. Toggle/enable the **Safe Mode** option.
4. Click **Test Print** and observe the output receipt margin alignment:

### Calibration Rules:
* **Left-Side Trimming:** If the text/receipt is being cut off (trimmed) on the **left** edge, **increase the Left Trim** setting by `0.5mm` increments.
* **Right-Side Trimming:** If the text/receipt is being cut off (trimmed) on the **right** edge, **increase the Right Trim** setting by `0.5mm` increments.

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

## 🔄 Step 3: Recalibration (If margins fail later)

If you change the physical printer or if margins start alignment issues again:
1. Open the bottom-left menu and click **Settings** ⚙.
2. Click **Change Printer** 🖨.
3. Repeat **Step 1** calibration adjustments.

---

## 📄 Step 4: Collecting Logs

If printing or scanning fails during your test, please retrieve and share the log file:

* **Log File Location:** 
  * `%appdata%\Betbita Lucky6 Terminal\electron.log` OR
  * `%appdata%\terminal\electron.log`
  *(You can paste either path into Windows Run `Win + R` or the File Explorer address bar to find the file directly).*
