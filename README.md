# ANARC × Vicharak — Introduction to Microcontrollers
## AAYAM XI | Shrike Lite Workshop Kit

This repository contains the workshop website, instructor runbook, participant guide, Arduino sketches, and slide deck for a **single-board, demonstration-led** introduction to microcontrollers using the Vicharak Shrike Lite.

> Hardware scope: Vicharak **Shrike Lite** (RP2040 + Renesas FPGA). Do not substitute instructions for Shrike (RP2350) or Shrike-fi (ESP32-S3).

## Quick links
- Workshop site source: `docs/`
- Instructor runbook: `docs/instructor-runbook.md`
- Participant guide: `docs/participant-guide.md`
- Example firmware: `examples/`
- Slides: `ANARC_ShrikeLite_Workshop_Slides.pptx` (in the ZIP root)

## Publish as GitHub Pages (MkDocs)
1. Create a new public GitHub repository, for example `ANARC-ShrikeLite-Workshop`.
2. Upload the contents of this folder to the repository root.
3. In GitHub, open **Settings → Pages** and set the source to **GitHub Actions**.
4. Push to the `main` branch. The included workflow builds the MkDocs site and deploys it.
5. The site URL will be `https://<your-github-username>.github.io/<repository-name>/`.

The included workflow expects Python, MkDocs and the Material theme. GitHub Actions installs these from `requirements.txt`.

## Workshop day: safest operating approach
- Use one instructor laptop, one known-good USB data cable, and the Shrike Lite board.
- Pre-install and test Arduino IDE and the RP2040 core before participants arrive.
- Project the IDE and board serial/LED behaviour.
- Participants predict, explain, and modify code verbally or on their own laptops; only the instructor flashes the physical board.
- Keep the FPGA programming flow out of the mandatory beginner exercise.

## Important technical notes
- Shrike Lite MCU: RP2040.
- MCU user LED: GPIO 4, active-high.
- FPGA user LED: FPGA GPIO 16; it is **not** the RP2040 MCU LED pin.
- Board GPIO is 3.3 V compatible. Never apply 5 V to an MCU GPIO.
- Do not use USB power and the board's 5 V header simultaneously.
- The RP2040 pins used by the FPGA interface include GPIO 0, 1, 2, 3, 12, 13, 14 and 15. Avoid using these for the external input demo.
- Follow the official Shrike Lite pinout and setup docs, not generic Pico assumptions.

## Official references
- https://vicharak-in.github.io/shrike/
- https://vicharak-in.github.io/shrike/hardware_overview.html
- https://vicharak-in.github.io/shrike/getting_started.html
- https://vicharak-in.github.io/shrike/shrike_pinouts.html
- https://github.com/vicharak-in/shrike

## Accuracy note
The official Getting Started page describes Arduino board-package installation and a LittleFS workflow for the Shrike family. Because setup details and IDE/core versions can change, rehearse the complete upload procedure on the exact Shrike Lite board before the workshop. Do not first install or troubleshoot it in front of participants.
