# Althea OTP Authenticator - Installer Packages

## Package Contents

```
Althea OTP Authenticator/
├── Linux/
│   ├── authenticator_1.1.0_amd64.deb    # Install with: sudo dpkg -i authenticator_1.1.0_amd64.deb
│   └── authenticator                      # Standalone binary (optional)
├── Windows/
│   ├── olympus_authenticator.py          # Main Python application
│   ├── olympus-authenticator.png         # Application icon
│   ├── Althea OTP Authenticator.bat      # Batch launcher (run without installer)
│   ├── install_windows.iss               # Inno Setup script - compile on Windows
│   ├── launcher.cpp                      # C++ launcher source (compile with MinGW)
│   └── launcher.c                        # C launcher source (compile with MSVC/MinGW)
├── macOS/
│   ├── Althea OTP Authenticator.app/     # Complete .app bundle
│   ├── create_dmg.sh                     # Run on macOS to create .dmg installer
│   └── create_pkg.sh                     # Run on macOS to create .pkg installer
└── README.md                             # This file
```

## Installation Instructions

### Linux (Debian/Ubuntu/Mint)
```bash
sudo dpkg -i authenticator_1.1.0_amd64.deb
# Or run directly:
./authenticator gui
```
The .deb installs to `/usr/bin/authenticator` with desktop entry.

### Windows (64-bit)
**Option 1: Quick run (no installer)**
1. Install Python 3.8+ from https://python.org
2. Run `Althea OTP Authenticator.bat`

**Option 2: Full installer (recommended)**
1. On a Windows machine, install Inno Setup from https://jrsoftware.org/isinfo.php
2. Open `install_windows.iss` in Inno Setup Compiler
3. Press Ctrl+F9 to compile
4. Run `Althea_OTP_Authenticator_Setup_1.1.0.exe` - installs to `C:\Program Files\Althea OTP Authenticator\`

### macOS
**Option 1: Direct .app (fastest)**
```bash
# Copy to Applications
cp -R "Althea OTP Authenticator.app" /Applications/
```

**Option 2: Create .dmg installer (drag-to-Applications)**
```bash
# On macOS:
cd "/path/to/Althea OTP Authenticator/macOS"
./create_dmg.sh
# Creates Althea_OTP_Authenticator-1.1.0.dmg
# Open DMG → drag app to Applications
```

**Option 3: Create .pkg installer**
```bash
./create_pkg.sh
# Creates Althea_OTP_Authenticator-1.1.0.pkg
sudo installer -pkg Althea_OTP_Authenticator-1.1.0.pkg -target /
```

## Features
- ✅ Two-tab layout: Olympus (WHM) / Atlas (Tenant)
- ✅ Codes shown in plain text (no dots)
- ✅ QR code persists after enabling - scan on multiple devices
- ✅ Encrypted vault with master password
- ✅ Synced removal: disable on platform → get code → remove from app
- ✅ QR code visible in settings after enabling - add to multiple devices

## Adding Accounts on Multiple Devices
1. Enable 2FA on Olympus/Atlas Settings → scan QR code with Google Authenticator
2. Open Althea Authenticator on Linux/Windows/macOS → Add Account → scan same QR
3. All devices show identical codes simultaneously

## Uninstalling
- **Linux**: `sudo dpkg -r authenticator`
- **Windows**: Use Add/Remove Programs or run uninstaller
- **macOS**: Drag app to Trash, or `sudo installer -pkg Althea_OTP_Authenticator.pkg -target /` (for pkg)

## Support
Althea AI — admin@althea-ai.pro
