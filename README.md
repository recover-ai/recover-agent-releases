# Recover Agent — Downloads

Official Windows installer releases for the **Recover Agent** — the privacy-first
local agent that finds forgotten quotes, overdue invoices, dormant customers and
missed leads on your own machine. Raw data never leaves your device; only
redacted summaries sync, and only with your approval.

> Source code is developed in the private `recover-ai/recover` repository.
> This public repo hosts **release binaries and notes only**.

## Choose your channel

| Channel | Tag pattern | Stability | Audience |
|---|---|---|---|
| **Stable** | `vX.Y.Z` | Production-ready | All customers |
| **Beta** | `vX.Y.Z-beta.N` | Pilot-tested | Pilot customers |
| **Alpha** | `vX.Y.Z-alpha.N` | Experimental | Internal |

Pick the newest **stable** release unless Recover support asked you to join a
beta. Alpha/beta releases are marked *pre-release*.

## Install

1. Download `Recover-Agent-Setup-<version>.exe` from the release assets.
2. Ask a Recover admin for a one-time **enrollment code** (Console → Agent →
   "Generate enrollment code"; looks like `7K2Q-M9XD-4TPA`, works once,
   expires after 24 hours).
3. Run the installer (admin rights). It shows the EULA, then asks for your
   **API URL** and the **enrollment code** — no tenant field. Upgrading an
   already-enrolled device? Leave the code empty.
4. Leave "Accept the EULA and enroll this device" ticked on the Finish page.
   If enrollment fails, generate a NEW code and run in an admin terminal:
   `"C:\Program Files\Recover Agent\recover-agent.exe" enroll --code YOUR-CODE`

## Verify your download

Each release notes include the installer's **SHA256**. Check it in PowerShell:

```powershell
(Get-FileHash .\Recover-Agent-Setup-<version>.exe -Algorithm SHA256).Hash
```

## Requirements

- Windows 10/11, 64-bit
- Admin rights for installation
- Internet access to your Recover Cloud deployment (for enroll/sync; optional —
  the agent also works fully offline in private mode)
