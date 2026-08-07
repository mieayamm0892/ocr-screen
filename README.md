# ocr-screen

A lightweight OCR screenshot tool for Wayland, optimized for visual novel dialogue text.

`ocr-screen` lets you select any area of your screen, preprocess the image for better OCR accuracy, extract text using Tesseract, and automatically copy the result to the Wayland clipboard.

Designed to stay out of your way — no extra windows, no focus stealing, just select, OCR, and paste.

---

## Demo

<video src="https://github.com/user-attachments/assets/564855c9-3fd7-4af2-a4a9-7d2662fbfb19" controls width="800"></video>

---

## Features

* Fast OCR workflow for Wayland
* Select screen area using `slurp`
* Capture screenshots with `grim`
* Image preprocessing using ImageMagick
* Text extraction using Tesseract OCR
* Automatically copy results to Wayland clipboard
* Desktop notification after OCR completion
* Optimized for small visual novel dialogue text
* Lightweight Bash script
* Fullscreen-friendly
* No additional GUI windows
* No focus stealing

---

## Requirements

* Wayland compositor
* `grim`
* `slurp`
* `imagemagick`
* `tesseract`
* `wl-clipboard`
* `libnotify`

---

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

---

## Notes

* Optimized for visual novel screenshots and dialogue boxes.
* Uses image preprocessing to improve OCR accuracy.
* Currently supports English (`eng`) and Indonesian (`ind`) OCR.
* Built for Wayland environments, especially Hyprland.
