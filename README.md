# ocr-screen

A lightweight OCR screenshot utility for Wayland compositors.

`ocr-screen` lets you quickly capture any region of your screen, preprocess the image for improved OCR accuracy, extract text using Tesseract, and automatically copy the result to the Wayland clipboard.

Unlike many GUI OCR applications, it does **not** open additional windows or steal keyboard focus, making it ideal for fullscreen applications and uninterrupted workflows.

---

## 🎥 Demo

---

## Features

- Fast OCR workflow for Wayland
- Select a screen area using `slurp`
- Capture screenshots with `grim`
- Image preprocessing using ImageMagick
- Extract text using Tesseract OCR
- Automatically copy extracted text to the Wayland clipboard
- Desktop notification when OCR is complete
- Optimized for English (`eng`) and Indonesian (`ind`)
- Lightweight Bash script
- Fast startup
- Fullscreen-friendly
- No additional GUI windows
- No focus stealing

## Why?

Many OCR applications interrupt your workflow by opening additional windows or stealing keyboard focus.

`ocr-screen` is designed to stay out of your way.

```
Shortcut → Select Area → OCR → Clipboard
```

No dialogs.

No extra windows.

Just select, copy, and paste.

## Requirements

- Wayland
- `grim`
- `slurp`
- `imagemagick`
- `tesseract`
- `wl-clipboard`
- `libnotify`

## Installation

### Arch-based distributions

Install the required packages:

```bash
sudo pacman -S grim slurp imagemagick tesseract wl-clipboard libnotify
```

Clone the repository:

```bash
git clone https://github.com/skibidigyat223/ocr-screen.git
cd ocr-screen
```

Make the script executable:

```bash
chmod +x ocr-screen
```

Install it:

```bash
sudo install -Dm755 ocr-screen /usr/local/bin/ocr-screen
```

Run:

```bash
ocr-screen
```

> **Note**
>
> `ocr-screen` is optimized for English (`eng`) and Indonesian (`ind`) OCR.

## Hyprland Keybind

Example:

```ini
bind = ALT, A, exec, ocr-screen
```

Reload Hyprland:

```bash
hyprctl reload
```

> **Note**
>
> Depending on your configuration, your keybind file may be located in:
>
> - `~/.config/hypr/hyprland.conf`
> - `~/.config/hypr/UserConfigs/UserKeybinds.conf`
> - Any custom configuration file included by your Hyprland setup

## Usage

1. Press your configured shortcut.
2. Select the desired screen area.
3. Wait for OCR processing to finish.
4. A desktop notification will appear.
5. Paste the copied text anywhere using **Ctrl + V**.

## How It Works

```text
Select Area
     │
     ▼
   slurp
     │
     ▼
    grim
     │
     ▼
ImageMagick
     │
     ▼
 Tesseract
     │
     ▼
  wl-copy
     │
     ▼
 Clipboard
```

## Notes

- Wayland only.
- Optimized for Hyprland but compatible with other Wayland compositors that support `grim` and `slurp`.
- Optimized for English (`eng`) and Indonesian (`ind`) OCR.
- Lightweight and keyboard-driven.
- No additional GUI windows.
- No focus stealing.