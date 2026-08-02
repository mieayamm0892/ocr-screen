
# ocr-screen

Simple OCR screenshot tool for Wayland/Hyprland.

`ocr-screen` lets you select any area of your screen, preprocess the image for better OCR accuracy, extract text using Tesseract, and automatically copy the result to the Wayland clipboard.

Unlike many GUI OCR applications, it does **not** open an additional window or steal focus, making it ideal for fullscreen applications and fast workflows.

## Features

- Select a screen area using `slurp`
- Capture screenshots with `grim`
- Preprocess images using ImageMagick
- Extract text with Tesseract OCR
- Automatically copy extracted text to the Wayland clipboard
- Lightweight and script-based
- Works well with fullscreen applications

## Dependencies

### Arch-based distributions

```bash
sudo pacman -S grim slurp tesseract imagemagick wl-clipboard
```

> **Note**
>
> The default OCR languages are English (`eng`) and Indonesian (`ind`).
> Install additional Tesseract language packs if needed.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/mieayamm0892/ocr-screen.git
cd ocr-screen
```

Make the script executable:

```bash
chmod +x ocr-screen
```

Install system-wide:

```bash
sudo install -Dm755 ocr-screen /usr/local/bin/ocr-screen
```

Verify the installation:

```bash
ocr-screen
```

---

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

---

## Usage

1. Press your configured keybind (e.g. **Alt + A**).
2. Select the area you want to extract text from.
3. Wait for OCR processing to finish.
4. Paste the copied text anywhere using **Ctrl + V**.

---

## How It Works

```
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
```

1. Select a region with **slurp**.
2. Capture the selected region using **grim**.
3. Preprocess the image with **ImageMagick**.
4. Extract text using **Tesseract OCR**.
5. Copy the extracted text directly to the Wayland clipboard.

---

## Notes

- Wayland only.
- Designed for Hyprland but should work with other Wayland compositors that support `grim` and `slurp`.
- No additional GUI is opened during OCR.
- Does not interrupt fullscreen applications.

---

## License

MIT License.
````
