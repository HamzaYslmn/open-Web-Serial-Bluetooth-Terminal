# open Web Serial Bluetooth Terminal

A serial terminal for BLE UART devices, in the browser. One file, no build.

**Open it:** https://hamzayslmn.github.io/open-Web-Serial-Bluetooth-Terminal/

Needs Web Bluetooth: Chrome or Edge on desktop or Android, Bluefy on iOS. Firefox and Safari have none.

## Use

1. Press **Connect** and pick the device.
2. It finds the UART by itself: Nordic UART, HM-10 (`ffe0`), `fff0` modules, Microchip, u-blox, GARRY.
3. Type and press Enter. Up and down walk the history.

Everything else is in **Settings** (the sliders button), and the defaults work for most devices:

| Setting | What |
|---|---|
| Service UUID | Blank is auto. Set it (`ffe0` or a full UUID) for a device the list does not know |
| Line end | Added to every text line you send. LF by default |
| Prefix (hex) | Bytes put in front of every write. Blank is auto: `01` on a GARRY board, nothing elsewhere |
| Send as hex | The input is hex bytes, like `01 3f` |
| Show received as hex | Received bytes as hex instead of text |
| Timestamps | On screen and in the export |

**Copy all** puts the whole log on the clipboard, **Download .txt** saves it. Both keep every line,
even past the 5000 the screen shows.

## Run locally

Web Bluetooth needs https or localhost:

```bash
python -m http.server 8000
```

Then open http://localhost:8000.

## Pages

`.github/workflows/pages.yml` deploys the repo root on every push to `main`. Turn it on once:
repo **Settings > Pages > Source: GitHub Actions**.
