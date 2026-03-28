# Diagrams

This folder contains all visual materials for the Evil Twin research project.

## Mermaid Diagrams (render automatically on GitHub)

| File | Description |
|---|---|
| [`attack-flow.md`](attack-flow.md) | 5-stage Evil Twin attack chain with tool annotations |
| [`lab-architecture.md`](lab-architecture.md) | Isolated VirtualBox lab setup — network isolation proof |
| [`defense-layers.md`](defense-layers.md) | 3-layer defense model with decision flow |

## Screenshots (from lab experiment)

Folder: [`screenshots/`](screenshots/)

| File | What to put there |
|---|---|
| `01-monitor-mode.png` | airgeddon interface selection + monitor mode activation |
| `02-evil-twin-menu.png` | Evil Twin option selected in airgeddon menu |
| `03-fake-ap-running.png` | Rogue AP deployed, SSID visible |
| `04-captive-portal.png` | Phishing login page (captive portal) |
| `05-credentials-captured.png` | Terminal showing "Credentials captured!" |
| `infographic.png` | Timeline infographic from research presentation |

## How to Export Screenshots from pres.pptx

1. Open `pres.pptx` in PowerPoint
2. Select the slide you want
3. **File → Export → Export to PNG** (or right-click slide → Save as Image)
4. Save each screenshot with the filename from the table above
5. Place all files in the `screenshots/` subfolder
