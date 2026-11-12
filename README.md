# Seraph for Windows

Seraph is your voice for AI interviews and calls. It hears the conversation, answers, and speaks the answer into your meeting app through its own microphone, the **Seraph mic**. Speech recognition and the voice run locally on your PC.

This repository hosts the Windows releases of Seraph. The source code is not published here.

## Download

**[Download the latest Seraph-Setup.exe](https://github.com/movup-ai/seraph-release/releases/latest/download/Seraph-Setup.exe)**

To see every version and its release notes, open [Releases](https://github.com/movup-ai/seraph-release/releases).

## Requirements

- Windows 10 version 2004 (build 19041) or newer, or Windows 11, 64-bit
- About 1 GB of free disk space: the program, plus about 580 MB of voice and speech models
- An internet connection to install and to sign in

## Install

1. Run `Seraph-Setup.exe`.
2. Leave **Download the voice and speech models now** ticked, then click **Install**.
3. If Windows asks for permission to install the **Seraph mic**, click **Yes**. It's the only step that needs your OK, and it happens only once per PC.
4. Seraph opens when Setup finishes. Sign in with your Seraph account.

Setup installs Seraph for your Windows account only, and it doesn't need an administrator account. The program goes to `%LOCALAPPDATA%\Programs\Seraph`, and your settings, models and logs go to `%LOCALAPPDATA%\Seraph`.

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

In Zoom, Teams, Google Meet or any other call app, pick **Seraph Output (Seraph Virtual Cable)** as your microphone. The meeting then hears Seraph's voice.

## Updates

Seraph checks this repository for new versions and offers to update when one is out. You can also download the latest setup and run it over your current version. Your settings, sign-in and models are kept.

## Uninstall

Go to **Settings → Apps → Installed apps**, find **Seraph**, and click **Uninstall**. Setup asks whether to delete your data folder too.

The Seraph mic (the VB-Audio Virtual Cable driver) stays installed, because other apps may use it. To remove it, uninstall **VB-Audio Virtual Cable** from the same list.

## Credits

- The Seraph mic is [VB-Audio Virtual Cable](https://vb-audio.com/Cable/), redistributed with VB-Audio's permission.
- The full list of third-party credits and licences is in Seraph under **About**.

## Support and issues

To report a problem, [open an issue](https://github.com/movup-ai/seraph-release/issues). Include your Seraph version (shown in **About**) and your Windows version.
