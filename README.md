# ProteanCNC

A low-cost, open-source toolchanger that turns a stock **Ender 3** into a multi-process machine, plus an AI supervisor that watches prints and catches failures.

By Vishnu Suhas Chinta and Tejas Singh. Reached **Stage 3 of the Vishwakarma Awards**.

## Why
Commercial toolchangers start around US$700 (Snapmaker U1) and go past US$4,000 (Prusa XL). ProteanCNC is meant to convert a printer people already own, for a fraction of that.

## What it will do
- Multi-colour printing without purging filament on every colour change
- Multi-material printing (e.g. PETG supports under a PLA part, which separate cleanly)
- Non-hotend tools on the same gantry: a spindle for milling PCBs, or a pick-and-place head for ICs and magnets

## Status
Early prototype. The Ender already drives a **pen-plotter tool** from G-code sent over serial. The carriage and swap mechanism are in active design.

## Files

### `cad/toolchanger/` (carriage and swap mechanism)
| File | What it is |
|---|---|
| `ToolChanger-Carriage-V2.stl` | Toolchanger carriage, V2 |
| `carriage-extender.stl` | Carriage extender |
| `TC-CE-holes.stl` | Carriage extender with mounting holes |
| `TC-CE-V2-Pin+Holes.stl` | Carriage extender V2 with locating pins and holes |
| `TCCE-V2.1-ServoCam.stl` | **Latest.** Carriage extender V2.1 with a servo-driven cam lock |

### `cad/tools/`
| File | What it is |
|---|---|
| `TC-PenPlotter-V1-BandLoaded.stl` | Pen-plotter tool, V1, band-loaded pen |

## AI-supervised printing (companion work)
A Telegram bot controls a Flashforge Adventurer 3 (start/pause/stop, axes, temperatures, live camera). A CNN on the camera feed is being trained to detect print failures and pause the print. The end goal is a closed loop that edits the remaining G-code mid-print.
