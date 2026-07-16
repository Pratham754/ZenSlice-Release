# 🌿 ZenSlice

<p align="center">
  <img src="https://github.com/Pratham754/ZenSlice/blob/main/banner.png?raw=true"/>
</p>

<p align="center">
  <strong>Track. Reflect. Balance.</strong><br/>
  A privacy-first desktop app that helps you understand how you spend time on your computer.<br/>
  No cloud. No accounts. No telemetry. Everything stays on your machine.
</p>

<p align="center">
    <img src="https://img.shields.io/github/downloads/Pratham754/ZenSlice-Release/total?style=for-the-badge&color=64B5F6&logo=github" alt="Total GitHub Downloads" />
  <img src="https://img.shields.io/github/v/release/Pratham754/ZenSlice-Release?style=for-the-badge&color=81C784" alt="Latest Release Version" />
  <img src="https://img.shields.io/badge/License-Apache_2.0-brightgreen?style=for-the-badge" alt="Apache License" />
</p>

---

## What is ZenSlice?

ZenSlice runs silently in your system tray and tracks which applications are in the foreground — building an accurate picture of how your day actually goes. Open the dashboard whenever you want to review your habits: weekly charts, daily breakdowns, per-app usage, category summaries, focus timers, and more.

---

## Features

<br/>

<table>
  <tr>
    <td width="50%" valign="top">

### ⏱ Screen Time Tracking
Real-time foreground window monitoring, polling every second. System processes and background services are excluded automatically. Usage commits to a local SQLite database every 10 seconds via WAL mode.

</td>
    <td width="50%" valign="top">

### 📊 Weekly & Daily Dashboard
Mon–Sun bar chart for any past week. Click any bar to drill into that day. Navigate all the way back to your first day of use — partial first weeks are handled correctly.

</td>
  </tr>
  <tr>
    <td width="50%" valign="top">

### 📋 Per-App Breakdown
Scrollable list of every app used that day, sorted by time, with progress bars showing each app's share of total screen time. App icons are loaded natively via Electron and cached to disk using MD5-hashed filenames.

</td>
    <td width="50%" valign="top">

### 🏷️ App Categorization
Manually assign one of **11 categories** to any app: Work, Learning, Gaming, Social, Browsing, System, Music, Utilities, Entertainment, Productivity, Other<br>
Once set, every future entry for that app is automatically tagged. The distribution chart toggles between per-app and per-category views.

</td>
  </tr>
  <tr>
    <td width="50%" valign="top">

### 🔍 App Details Dialog
Click any app row to open a detail card with the app name, today's usage, assigned category (editable), daily limit (editable), and full executable path — all in one place.

</td>
    <td width="50%" valign="top">

### ⏰ App Time Limits
Set a daily cap from **5 minutes to 8 hours** on any app. Get a Windows notification 5 minutes before the limit and again when you hit it. Progress bars turn **amber at 80%** and **red when over**.

</td>
  </tr>
  <tr>
    <td width="50%" valign="top">

### 🎯 Focus Mode
Start a timed focus session from **5 minutes to 4 hours**. A live countdown timer and progress bar sit in Settings. Mark apps as distractions — you'll get a nudge if you open them mid-session. Sessions survive renderer reloads.

</td>
    <td width="50%" valign="top">

### 📁 Excel Export
Export your full history to a structured `.xlsx` file with three sheets: **Summary** (totals + most-used app), **Usage Data** (per-app per-day), and **Screen Time** (daily totals). Opens a native save dialog.

</td>
  </tr>
  <tr>
    <td width="50%" valign="top">

### 🎨 4 Built-in Themes
**Autumn Glow** · **Peach Ice & Aqua Mist** · **Soft Sage & Deep Olive** · **Pearl & Charcoal**

Each theme ships with its own MUI palette and 12 chart colors. Selection persists to localStorage and applies instantly — no restart needed.

</td>
    <td width="50%" valign="top">

### 🔄 Auto-Update
Checks for new releases on every startup. Download and install from inside the app with a live progress indicator. Works with both signed and unsigned builds via a manual installer fallback.

</td>
  </tr>
</table>

<br/>

---

## Screenshots

<table>
  <tr>
    <td width="50%" valign="top" align="center">

**Dashboard — Weekly Overview**<br>
*Weekly screen time at a glance with daily averages and more.*

<img src="https://github.com/Pratham754/ZenSlice-Release/blob/main/images/Dashboard.png?raw=true" width="100%"/>

</td>
    <td width="50%" valign="top" align="center">

**App Usage Breakdown**<br>
*Every app sorted by time, with category tags and limit indicators.*

<img src="https://github.com/Pratham754/ZenSlice-Release/blob/main/images/App%20Usage%20Breakdown.png?raw=true" width="100%"/>

</td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center">

**App Distribution — Category View**<br>
*Toggle between per-app and per-category views.*

<img src="https://github.com/Pratham754/ZenSlice-Release/blob/main/images/App%20Distribution%20Category.png?raw=true" width="100%"/>

</td>
    <td width="50%" valign="top" align="center">

**App Details Dialog**<br>
*Usage, category, limit, and executable path — all in one place.*

<img src="https://github.com/Pratham754/ZenSlice-Release/blob/main/images/App%20Details.png?raw=true" width="100%"/>

</td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center">

**Settings — Limits, Focus Mode & Themes**<br>
*App limits, focus timer, theme picker, and data export in one scroll.*

<img src="https://github.com/Pratham754/ZenSlice-Release/blob/main/images/App%20Limit%20Focus%20Mode%20Settings.png?raw=true" width="100%"/>

</td>
    <td width="50%" valign="top" align="center">

**Multiple Themes**<br>
*Four carefully designed themes — pick the one that fits your style.*

<img src="https://github.com/Pratham754/ZenSlice-Release/blob/main/images/Themes.png?raw=true" width="100%"/>

</td>
  </tr>
</table>

---

## Installation

```
1. Download ZenSlice-1.1.0-x64.exe from the Releases page
2. Run the installer — no admin rights required, installs per-user
3. ZenSlice starts automatically and sits in the system tray
4. Click the tray icon to open the dashboard
```

<p align="center">
  <a href="https://github.com/Pratham754/ZenSlice-Release/releases/latest">
    <img src="https://img.shields.io/badge/Get_the_Installer-0078D4?style=for-the-badge&logo=windows&logoColor=white" />
  </a>
</p>

---

## How it Works

```
Active window polling  (every 1s, via active-win)
          ↓
In-memory accumulation  (Map per app per session)
          ↓
SQLite commit  (every 10s, WAL mode, upsert on conflict)
          ↓
IPC event → React renderer  (live dashboard updates)
```

System processes, Explorer, and anything in your temp directory are excluded. The database lives at:

```
%APPDATA%\ZenSlice\usage_data.db
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Desktop runtime | Electron 28 |
| UI framework | React 18 + MUI v5 |
| Database | SQLite — better-sqlite3 (WAL mode) |
| Charts | Recharts |
| Excel export | ExcelJS |
| Auto-update | electron-updater |
| Packaging | electron-builder (NSIS) |

---

## Privacy & Security

| | |
|---|---|
| 🚫 No telemetry | Zero usage data sent anywhere |
| 🚫 No cloud | Everything stored locally in `%APPDATA%\ZenSlice\` |
| 🚫 No accounts | No sign-up, no login, no profile |
| 🔒 Context isolation | `contextIsolation: true`, `nodeIntegration: false` |
| 🔒 No DevTools | Disabled in production builds |

---

## Roadmap

- [ ] Productivity score — ratio of productive vs distraction time
- [ ] Long-term trend view — monthly and all-time charts
- [ ] Cross-platform support — macOS & Linux

---

## Contributing

1. Fork the repo
2. Create a feature branch
3. Submit a pull request

Bug reports and feature suggestions go in [Issues](https://github.com/Pratham754/ZenSlice/issues).

---

## License

Distributed under the **Apache License 2.0** — see [LICENSE](./LICENSE) for details.

---

<p align="center">
  Made by <strong>Pratham Choudhary</strong>
</p>
