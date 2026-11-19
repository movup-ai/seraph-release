# Seraph for Windows

Seraph is your voice for AI interviews and calls. It hears the conversation, answers, and speaks the answer into your meeting app through its own microphone, the **Seraph mic**. Speech recognition and the voice run locally on your PC.

This repository hosts the Windows releases of Seraph. The source code is not published here.

## Download

**[Download the latest Seraph-Setup.exe](https://github.com/movup-ai/seraph-release/releases/latest/download/Seraph-Setup.exe)**

To see every version and its release notes, open [Releases](https://github.com/movup-ai/seraph-release/releases).

## Requirements

- Windows 10 version 2004 (build 19041) or newer, or Windows 11, 64-bit
- An administrator's permission to install
- About 1 GB of free disk space: the program, plus about 580 MB of voice and speech models
- An internet connection to install and to sign in

## Install

1. Run `Seraph-Setup.exe`, and click **Yes** when Windows asks for permission.
2. Leave **Download the voice and speech models now** ticked. To install somewhere other than the default folder, click **Browse...**.
3. If the PC doesn't have the Seraph mic yet, leave **Install the Seraph mic for meetings** ticked. Windows asks for permission once more to install it.
4. Click **Install**. If the Seraph mic was installed, Setup offers to restart the PC: restart before your first meeting, so Windows lists the mic.
5. Seraph opens when Setup finishes. Sign in with your Seraph account.

Seraph is installed for every Windows user of the PC, in `C:\Program Files\Seraph` unless you chose another folder. The voice and speech models go in that folder's `models` folder and are shared by every user. Each user's settings, sign-in and logs go in their own `%LOCALAPPDATA%\Seraph`.

If you install in a folder outside Program Files, choose a new or empty folder: Setup refuses a folder that already holds other files, and locks the folder so that only administrators can change the program.

If the model download is interrupted, Setup still finishes, and Seraph downloads the missing models the next time it opens.

### "Windows protected your PC"

Microsoft Defender SmartScreen may warn about a new download it hasn't seen often. Click **More info**, then **Run anyway**. To be sure the file is the real one, check its SHA-256 first, as described below.

## Check the download

Each release's notes show the setup's SHA-256 hash. In PowerShell, in the folder that contains the setup, run:

```powershell
Get-FileHash .\Seraph-Setup.exe -Algorithm SHA256
```

The hash it prints must match the one in the release notes. If it doesn't, the download is incomplete or the file has been altered, so delete it and download it again.

## Use the Seraph mic in a meeting

In Zoom, Teams, Google Meet or any other call app, pick **Seraph Voice (Seraph Virtual Cable)** as your microphone. The meeting then hears Seraph's voice.

You can rename the mic in Seraph under **Settings → Meeting microphone**. The meeting then lists it by the name you chose.

## Updates

Seraph checks this repository for new versions. When one is out, a small window says so, and nothing is downloaded until you click **Install now**. Seraph then downloads the setup, checks it, closes and updates itself, and opens again. **Remind me later** hides the offer until Seraph next opens. You can also check from **About**.

An update never starts during a conversation. Your settings, sign-in and models are kept.

**Updating from 1.4:** version 1.4 can't install an update from inside the app. Download the latest setup and run it once over your current version; later versions update from inside the app.

## Uninstall

Go to **Settings → Apps → Installed apps**, find **Seraph**, and click **Uninstall**. Setup asks whether to delete your data folder too.

The Seraph mic (the VB-Audio Virtual Cable driver) stays installed, because other apps may use it. To remove it, uninstall **VB-Audio Virtual Cable** from the same list.

## Credits

- The Seraph mic is [VB-Audio Virtual Cable](https://vb-audio.com/Cable/), redistributed with VB-Audio's permission.
- The full list of third-party credits and licences is in Seraph under **About**.

## Support and issues

To report a problem, [open an issue](https://github.com/movup-ai/seraph-release/issues). Include your Seraph version (shown in **About**) and your Windows version. If an update didn't install, attach `%LOCALAPPDATA%\Seraph\logs\update-setup.log`.
