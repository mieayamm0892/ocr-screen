
# ocr-screen

A lightweight OCR screenshot utility for Wayland compositors.

`ocr-screen` lets you select any area of your screen, preprocess the image for better OCR accuracy, extract text using Tesseract, and automatically copy the result to the Wayland clipboard.

Unlike many GUI OCR applications, it does **not** open an additional window or steal focus, making it ideal for fullscreen applications and uninterrupted workflows.

## Features

- Select a screen area using `slurp`
- Capture screenshots with `grim`
- Preprocess images using ImageMagick
- Extract text using Tesseract OCR
- Automatically copy extracted text to the Wayland clipboard
- Lightweight Bash script
- Fast startup
- Works well with fullscreen applications

## Why?

Most OCR applications open an additional window or steal focus after capturing the screen.

`ocr-screen` keeps your workflow uninterrupted by copying the extracted text directly to the clipboard without opening any extra windows.

## Requirements

- Wayland
- `grim`
- `slurp`
- `imagemagick`
- `tesseract`
- `wl-clipboard`

## Installation

### Arch-based distributions

Install the required packages:

```bash
sudo pacman -S grim slurp imagemagick tesseract wl-clipboard
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

Install it system-wide:

```bash
sudo install -Dm755 ocr-screen /usr/local/bin/ocr-screen
```

Run:

```bash
ocr-screen
```

> **Note**
>
> The default OCR languages are English (`eng`) and Indonesian (`ind`).
> Install additional Tesseract language packs if needed.

## Hyprland Keybind

Example:

```ini
bind = ALT, A, exec, ocr-screen
```

Reload Hyprland after editing your configuration:

```bash
hyprctl reload
```

> **Note**
>
> The location of your keybind configuration depends on your Hyprland setup.
>
> Common locations include:
>
> - `~/.config/hypr/hyprland.conf`
> - `~/.config/hypr/UserConfigs/UserKeybinds.conf`
> - Any custom configuration file included by your Hyprland configuration.

## Usage

1. Press your configured keybind (e.g. **Alt + A**).
2. Select the area you want to extract text from.
3. Wait for OCR processing to finish.
4. Paste the copied text anywhere using **Ctrl + V**.

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

1. Select a region with **slurp**.
2. Capture the selected region using **grim**.
3. Preprocess the image using **ImageMagick**.
4. Extract text using **Tesseract OCR**.
5. Copy the extracted text directly to the Wayland clipboard.

## Notes

- Wayland only.
- Designed for Hyprland but compatible with other Wayland compositors that support `grim` and `slurp`.
- No additional GUI windows.
- No focus stealing.
- Fullscreen-friendly.
- Default OCR languages: English (`eng`) and Indonesian (`ind`).
````
