# Desktop LSO™

**Offline-first laser safety software for macOS and Windows.**

Desktop LSO™ is a professional laser safety calculation suite that runs entirely on your machine — no internet required after installation. It is part of the LaserSafetyNet platform, included with a single subscription alongside Pocket LSO™ (iOS & Android) and the web-based analysis tools.

---

## Features

- **Classification Engine** — IEC 60825-1 / ANSI Z136.1 laser classification with detailed tabular output
- **NOHD & Irradiance Plots** — Nominal Ocular Hazard Distance calculations with distance vs. irradiance charts
- **Broadband / LED Safety Analysis** — Weighted irradiance analysis for non-laser extended sources
- **Non-Beam Hazard Assessment** — Fire, electrical, and chemical hazard screening
- **SOP Report Generator** — Auto-populated Standard Operating Procedure documents
- **FMEA & Fault Tree Analysis** — Failure mode and fault tree tools for interlocked systems
- **AI Safety Agent** — Integrated AI assistant for laser safety queries

---

## System Requirements

| Platform | Minimum |
|----------|---------|
| macOS | Apple Silicon (M1 or later), macOS 12 Monterey or later |
| Windows | Windows 10 / 11, x86-64 |

> Intel Mac builds are not currently provided. Contact support if this is a requirement.

---

## Download

Go to the [Releases](https://github.com/lazsaf/desktop-lso-releases/releases) page and download the installer for your platform:

| Platform | File |
|----------|------|
| macOS (Apple Silicon) | `Desktop.LSO_x.x.x_aarch64.dmg` |
| Windows | `Desktop.LSO_x.x.x_x64-setup.exe` or `.msi` |

---

## Installation

### macOS

1. Download the `.dmg` file from the Releases page.
2. Open the `.dmg` and drag **Desktop LSO** into your Applications folder.
3. On first launch, right-click the app → **Open** if macOS shows an "unidentified developer" warning (only needed once).
4. Sign in with your LaserSafetyNet account.

### Windows

1. Download the `-setup.exe` (recommended) or `.msi` installer from the Releases page.
2. Run the installer — Windows SmartScreen may show a warning; click **More info → Run anyway**.
3. Follow the installer prompts.
4. Launch **Desktop LSO** from the Start menu and sign in with your LaserSafetyNet account.

---

## Subscription

Desktop LSO™ requires an active LaserSafetyNet subscription. All three platforms — Desktop LSO™, Pocket LSO™, and the web analysis tools — are included under a single subscription.

Sign up or manage your account at [lasersafetynet.com](https://lasersafetynet.com).

---

## Support and Training

- In-app: use the AI Safety Agent for immediate laser safety questions
- Email: support@lasersafetynet.com
- Training and product compliance support also available — contact us for details

---

## Publishing a New Release (maintainer notes)

Releases are built and published automatically via GitHub Actions in the private `LaserSafe-Net` repository. To cut a new release:

1. Make sure all changes are committed and pushed to `main` on `LaserSafe-Net`.
2. Create and push a version tag from your terminal:

```bash
git tag desktop-v0.2.0
git push origin desktop-v0.2.0
```

3. The workflow will:
   - Build the macOS (Apple Silicon) and Windows installers
   - Create a **draft** GitHub Release on `LaserSafe-Net` with the binaries attached
   - Mirror the `.dmg`, `.msi`, and `-setup.exe` files to this repo (`desktop-lso-releases`) as a published release

4. Review and publish the draft release on `LaserSafe-Net` if needed, then verify the release appeared here.

### Required secrets on `LaserSafe-Net`

| Secret | Purpose |
|--------|---------|
| `APPLE_CERTIFICATE_BASE64` | Apple Developer ID Application cert (base64-encoded .p12) |
| `APPLE_CERTIFICATE_PASSWORD` | Password for the .p12 |
| `APPLE_SIGNING_IDENTITY` | e.g. `Developer ID Application: Your Name (TEAMID)` |
| `APPLE_TEAM_ID` | 10-character Apple team ID |
| `APPLE_ID` | Apple ID used for notarization |
| `APPLE_ID_PASSWORD` | App-specific password for notarization |
| `VITE_SUPABASE_URL` | Supabase project URL |
| `VITE_SUPABASE_ANON_KEY` | Supabase anon/public key |
| `VITE_API_BASE_URL` | Backend API base URL |
| `VITE_API_PORT` | Backend API port |
| `RELEASES_PAT` | Fine-grained PAT with `contents: write` on `desktop-lso-releases` |

---

*Desktop LSO™ is developed by LaserSafetyNet. All rights reserved.*
