# Lightshot We Deserve

A clean, open-source screenshot tool for Windows, macOS, and Linux. It lives
in the system tray and gives you global hotkeys for area and full-screen
capture — then lets you annotate, copy, or save in one move. No accounts, no
upload servers, no clutter.

Built by the team at **[keepsimple.io](https://keepsimple.io)**.

## Download

Grab the latest build from the [Releases page](https://github.com/Mr-Don-Leo/lightshot-we-deserve/releases/latest):

### Windows

- **Portable** — `lightshot-we-deserve.exe` · run it directly, no install.
- **Installer** — `Lightshot.We.Deserve_..._x64-setup.exe` · sets up the app and optional autostart.

### macOS

- **`Lightshot.We.Deserve_..._universal.dmg`** — one image for both Apple Silicon and Intel Macs.
- The app is not code-signed, so on first launch macOS may report it as damaged.
  Clear the quarantine flag once after copying it to Applications:
  `xattr -cr "/Applications/Lightshot We Deserve.app"`
- macOS will ask for **Screen Recording** permission on first capture
  (System Settings → Privacy & Security → Screen Recording).
- Video recording needs `ffmpeg` (e.g. `brew install ffmpeg`); screenshots work without it.

### Linux

- **`.AppImage`** — portable, works on most distros: `chmod +x` it and run.
- **`.deb`** (Debian/Ubuntu) and **`.rpm`** (Fedora/openSUSE) packages.
- The tray icon needs an AppIndicator-capable tray (GNOME users: install the
  AppIndicator extension).
- Global hotkeys work on X11; on Wayland they depend on the compositor and may
  be unavailable — the tray menu always works.
- Video recording needs `ffmpeg` from your package manager; screenshots work without it.

## Features

- Area and full-screen capture via global hotkeys
- Record a selected area to an MP4 video, with the mouse pointer shown and a low/high quality choice
- High-contrast crosshair that stays visible on light and dark backgrounds
- Annotate: pen, line, arrow, rectangle, marker, text, and blur
- Adjustable tool size and color
- Copy to clipboard, save, or "Save as…" with a custom name
- Drag the selection frame to reposition it before capturing
- Saves to your chosen folder (Desktop by default)
- Quietly runs from the tray, optional launch on startup

## Default hotkeys

| Action | Shortcut |
| --- | --- |
| Capture area | `Ctrl + Shift + 4` |
| Capture full screen | `Ctrl + Shift + 3` |

Hotkeys and save folder can be changed in the app settings.

## Build from source

Built with [Tauri](https://tauri.app). With the Rust toolchain and Node
installed:

```
npm install
npm run tauri build
```

Bundles land under `src-tauri/target/release/bundle/` (NSIS installer on
Windows, dmg on macOS, deb/rpm/AppImage on Linux). On Linux you need the
usual Tauri build deps plus pipewire and clang headers — see the
`Install Linux system deps` step in `.github/workflows/build.yml` for the
exact package list.

## License

[MIT](LICENSE) © keepsimple.io
