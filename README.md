# <img src="https://github.com/Manmayarama/ShadowPDF/blob/main/icons/document.png" alt="Logo" width="32" style="vertical-align: middle;"/> ShadowPDF

A lightweight Chrome/Chromium (and Microsoft Edge) extension that applies a dark-mode effect to PDFs by overlaying a full-screen layer using `mix-blend-mode: difference`.

## Features

- One-click toggle on PDF tabs
- Keyboard shortcut: `Ctrl+Shift+S` (macOS: `Command+Shift+S`)
- Tint strength slider: lighter ↔ darker
- Optional “Automatically turn on dark mode” preference (saved)

## Install (Developer Mode)

1. Open `chrome://extensions/` (or `edge://extensions/`).
2. Enable **Developer mode**.
3. Click **Load unpacked**.
4. Select the `ShadowPDF` folder.

## Use

### On web PDFs

1. Open a PDF URL that ends with `.pdf`.
2. Click the extension icon (or press `Ctrl+Shift+S`).

If the current tab URL doesn’t end with `.pdf`, the popup shows an ✕ badge.

### Keyboard shortcut setup (if `Ctrl+Shift+S` doesn’t work)

Chrome/Edge may not automatically assign the shortcut if it conflicts with another extension or a browser/OS shortcut.

1. Open `chrome://extensions/shortcuts` (or `edge://extensions/shortcuts`).
2. Find **ShadowPDF**.
3. Set **Apply dark mode to the current page** to `Ctrl+Shift+S` (macOS: `Command+Shift+S`).

Note: The shortcut currently applies only when the active tab URL ends with `.pdf`.

### On local PDFs (`file://`)

1. Go to `chrome://extensions/` → **ShadowPDF** → **Details**.
2. Enable **Allow access to file URLs**.
3. Open a local PDF and toggle as usual.

## Settings (Popup)

- **Automatically turn on dark mode**: stored in sync storage.
- **Tint slider**: stored in sync storage.

Note: In the current implementation, these settings are saved, but auto-apply behavior may depend on the page/viewer and how the toggle is triggered.

## Troubleshooting

- **Nothing happens**: Confirm the tab URL ends with `.pdf` and try reloading the PDF.
- **Shortcut not working**: Set it manually in `chrome://extensions/shortcuts` (or `edge://extensions/shortcuts`).
- **Local PDFs don’t work**: Enable **Allow access to file URLs** for the extension.
- **Some PDFs look odd**: The effect uses color-difference blending, so images/diagrams can invert in unexpected ways.

## Compatibility notes

- Some sites use custom PDF viewers/embeds; behavior can vary.
- The extension UI is built in `popup.html`, and the PDF effect is applied via `scripts/toggle.js`.

---

Developed by [Manmaya Rama](https://github.com/Manmayarama)
