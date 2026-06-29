# HamQSO — User Guide

A quick, friendly guide to logging contacts with HamQSO on your M5Stack Cardputer ADV. No prior setup knowledge needed.

---

## 1. The basics

When you power on, you'll see the **HamQSO** splash for a moment, then the app opens.

HamQSO has **three screens** ("sections"), and you move between them with **one key — the backtick `` ` ``** (top‑left, above Tab). The little label at the top shows where you are:

```
QSO · LOG · SET
```

- **QSO** — log a contact
- **LOG** — look back at the contacts you've logged
- **SET** — settings (your callsign, Wi‑Fi, clock)

Press **`` ` ``** to step through them: QSO → LOG → SET → back to QSO.

**A few keys to know:**

| Key | What it does |
|-----|--------------|
| `` ` `` (backtick) | Switch section (QSO / LOG / SET) |
| `Tab` | Move to the next field (in the QSO screen) |
| Arrow keys (`;` `,` `.` `/`) | Pick / nudge / scroll — used **bare**, no Fn |
| `Enter` | Log a contact / open / save |
| `Fn` + `` ` `` | "Esc" — go back or cancel |

You don't need the **Fn** key for normal use — just for that one "Esc" combo.

---

## 2. One‑time setup (SET)

Press **`` ` ``** until the top shows **SET**. Use `↑/↓` to move between rows and `Enter` to open one.

Set these up first:

1. **My callsign** — your callsign (e.g. `HJ3DAG`). Type it, press `Enter`.
2. **Grid locator** — your Maidenhead grid (e.g. `FJ29`).
3. **WiFi network** / **WiFi password** — your 2.4 GHz Wi‑Fi (the device can't use 5 GHz).
4. **Date & time** — open it, then:
   - **Auto‑sync via WiFi** — turn this **ON** and the clock will set itself over the internet each time you power on. Choose **Sync now** to do it immediately.
   - **UTC offset** — set your hours from UTC with `←/→` (e.g. `UTC‑5`). This keeps an evening's contacts together in one day's file.
   - **Set manually** — no internet? Pick the date/time by digit: `←/→` moves between the numbers, `▲▼` changes one, `Enter` saves.

> ⏰ **The clock must be set before you can log.** If the QSO screen shows **`CLK?`**, go set the time. (With auto‑sync on and Wi‑Fi configured, this usually happens by itself at boot.)

There's also an **About** row that shows the app version.

> 💡 Tip: you can pre‑fill all of this on a computer — edit `/HamQSO/config/hamqso.config` on the SD card, then put it back in the device.

---

## 3. Logging a contact (QSO)

Press **`` ` ``** until the top shows **QSO**. Across the top is the **field strip**:

```
CALL · FREQ · MODE · SNT · RCV · NOTE
```

The highlighted one is the field you're editing. Press **`Tab`** to move to the next field.

- **CALL** — type the other station's callsign. A little **country chip** appears (e.g. `JP  Japan`) as soon as it's recognized.
- **FREQ** — type the frequency in **kHz** (e.g. `14074`). No decimal point needed — it shows the MHz and the **band** (e.g. `20m`) for you.
- **MODE** — press **`←/→`** to choose SSB, CW, FM, AM, FT8, or RTTY.
- **SNT / RCV** — the signal reports (default `59`). Type them, or nudge with **`▲▼`**.
- **NOTE** — anything you want to remember.

When you're done, press **`Enter`**. You'll see a green **"✓ LOGGED"** confirmation, and the contact is saved to the SD card right away.

Then just type the next callsign — **frequency and mode stay put** (they even survive a power‑off), so on a run you only type calls.

> ⚠️ If you press `Enter` with **no frequency**, it won't log — you'll see **"set frequency"**, and your callsign stays so you can add it.

---

## 4. Reviewing & fixing contacts (LOG)

Press **`` ` ``** until the top shows **LOG**. You'll see the day's contacts:

```
time   MHz       flag callsign   mode   report
```

- **`↑/↓`** — move through the contacts.
- **`←/→`** — switch to another **day** (older or newer log files). The header shows the date and, e.g., `2/3` when you have several days.
- **`Enter`** — open a contact to **edit** it.

In the editor: **`Tab`** moves between fields, type to change a value (date shows as `2026‑06‑29`, time as `22:08`), **`Enter`** saves. To remove a contact, go to **Delete contact** and press `Enter` — you'll be asked **"Delete?"** to confirm (press `Enter` again to delete, or `Esc` to back out).

---

## 5. Where your contacts live

Everything is saved on the microSD card as standard **ADIF** files — one per day:

```
/HamQSO/logs/2026-06-29.adi
```

These import directly into LoTW, N1MM, Log4OM, and other logging software. The files are named by **your local date** (using the UTC offset you set), but the times inside are stored in **UTC**, as ham logging expects.

---

## Quick reference

| Where | Keys |
|-------|------|
| Anywhere | `` ` `` switch section · `Fn`+`` ` `` = Esc/back |
| QSO | `Tab` next field · type CALL/FREQ/NOTE · `←/→` mode · `▲▼` report · `Enter` log |
| LOG | `↑/↓` contact · `←/→` day · `Enter` edit |
| Edit | `Tab` field · type · `Enter` save · Delete row → `Enter` → confirm |
| SET | `↑/↓` row · `Enter` open · `Fn`+`` ` `` back |

73 on the air — and enjoy the log! 📻
