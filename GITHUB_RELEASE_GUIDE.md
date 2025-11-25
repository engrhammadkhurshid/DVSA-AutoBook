# 🚀 GitHub Release Guide

## Step 1: Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `dvsa-autobook`
3. Description: `🚗 Intelligent Driving Test Booking Automation for UK DVSA`
4. **Public** (so people can see the README and download releases)
5. ✅ Do NOT initialize with README (we have our own)
6. Click **Create repository**

---

## Step 2: Initialize Git & Push README

Open Terminal and run:

```bash
cd "/Users/hammadkhurshidchughtaii/Downloads/DVSA AutoBook Release"

# Initialize git
git init

# Add files
git add .

# Commit
git commit -m "Initial release - DVSA AutoBook v1.0.0"

# Add remote (replace YOUR_USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/dvsa-autobook.git

# Push
git branch -M main
git push -u origin main
```

---

## Step 3: Add Screenshots to Assets

Before creating the release, add your screenshots:

1. Take screenshots of the app:
   - Login screen → save as `screenshot-login.png`
   - Dashboard/main window → save as `screenshot-dashboard.png`
   - Scanning in progress → save as `screenshot-scanning.png`
   - Slot found alert → save as `screenshot-found.png`
   - (Optional) Create a demo GIF → save as `demo.gif`

2. Copy them to the assets folder:
   ```bash
   cp ~/path/to/screenshot-login.png "/Users/hammadkhurshidchughtaii/Downloads/DVSA AutoBook Release/assets/"
   cp ~/path/to/screenshot-dashboard.png "/Users/hammadkhurshidchughtaii/Downloads/DVSA AutoBook Release/assets/"
   # ... etc
   ```

3. Commit and push:
   ```bash
   git add assets/
   git commit -m "Add screenshots"
   git push
   ```

---

## Step 4: Create the DMG (macOS)

If you haven't already:

```bash
cd "/Users/hammadkhurshidchughtaii/Downloads/DVSA AutoBook"
./create_dmg.sh
```

This creates: `dist/DVSA AutoBook 1.0.0.dmg`

---

## Step 5: Build Windows EXE

On a Windows machine:

1. Copy the project folder to Windows
2. Run `build.bat`
3. Zip the output: `dist\DVSA AutoBook` → `DVSA-AutoBook-Windows-v1.0.0.zip`

---

## Step 6: Create GitHub Release

### Option A: Using GitHub Web UI

1. Go to your repo: `https://github.com/YOUR_USERNAME/dvsa-autobook`
2. Click **Releases** (right sidebar)
3. Click **Create a new release**
4. Fill in:
   - **Tag:** `v1.0.0`
   - **Title:** `DVSA AutoBook v1.0.0`
   - **Description:** (copy from below)
5. **Attach binaries:**
   - Drag `DVSA AutoBook 1.0.0.dmg` (macOS)
   - Drag `DVSA-AutoBook-Windows-v1.0.0.zip` (Windows)
6. Click **Publish release**

### Release Description Template:

```markdown
# 🚗 DVSA AutoBook v1.0.0

The first official release of DVSA AutoBook - Intelligent Driving Test Booking Automation.

## 📥 Downloads

| Platform | File | Size |
|----------|------|------|
| 🍎 macOS | `DVSA AutoBook 1.0.0.dmg` | ~180 MB |
| 🪟 Windows | `DVSA-AutoBook-Windows-v1.0.0.zip` | ~170 MB |

## ✨ What's New

- 🎉 Initial release
- ✨ Human-like mouse movement with Bezier curves
- ✨ 12-step DVSA booking workflow
- ✨ Sound alerts for slots and CAPTCHAs
- ✨ 15-minute reservation timer
- ✨ Offline license validation

## 📋 Installation

See the [README](../../#installation) for detailed installation instructions.

## 🔐 License Required

This software requires a valid license to activate. 
See [Pricing](../../#pricing) for details.

---

**Questions?** Contact: hammad@example.com
```

### Option B: Using GitHub CLI

```bash
# Install GitHub CLI if needed
brew install gh

# Authenticate
gh auth login

# Create release
cd "/Users/hammadkhurshidchughtaii/Downloads/DVSA AutoBook Release"

gh release create v1.0.0 \
  "/Users/hammadkhurshidchughtaii/Downloads/DVSA AutoBook/dist/DVSA AutoBook 1.0.0.dmg" \
  "/path/to/DVSA-AutoBook-Windows-v1.0.0.zip" \
  --title "DVSA AutoBook v1.0.0" \
  --notes "Initial release of DVSA AutoBook"
```

---

## Step 7: Verify Everything

1. **Check README renders:** Go to your repo and verify the README looks good
2. **Check releases:** Go to Releases tab and verify downloads work
3. **Test download links:** Try downloading on another device

---

## 📁 Final Repository Structure

```
dvsa-autobook/
├── README.md              ← Beautiful landing page
├── .gitignore            ← Ignore build files
├── assets/
│   ├── logo.png          ← App logo
│   ├── demo.gif          ← Demo animation (optional)
│   ├── screenshot-login.png
│   ├── screenshot-dashboard.png
│   ├── screenshot-scanning.png
│   └── screenshot-found.png
└── [RELEASES]            ← Not in repo, attached to GitHub Release
    ├── DVSA AutoBook 1.0.0.dmg
    └── DVSA-AutoBook-Windows-v1.0.0.zip
```

---

## ✅ Checklist

- [ ] Created GitHub repository
- [ ] Pushed README and assets
- [ ] Added all screenshots
- [ ] Built macOS DMG
- [ ] Built Windows EXE (on Windows)
- [ ] Created GitHub Release with attached binaries
- [ ] Tested download links
- [ ] Updated contact email in README

---

## 🔒 Important: Keep Source Code Private!

Your source code repository (`DVSA AutoBook/`) should remain **LOCAL ONLY** or in a **PRIVATE** repository.

The public `dvsa-autobook` repo contains:
- ✅ README (marketing/documentation)
- ✅ Screenshots
- ✅ Releases (DMG/EXE binaries)
- ❌ NO source code!

---

Good luck with your release! 🎉
