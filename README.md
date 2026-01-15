# nmea-visualizer
GPS NMEA parser and visualizer - https://gps.makotosan.com


A web app for parsing and visualizing live NMEA GPS data. It connects to GPS modules via the Web Serial API, plots position on a Leaflet map (OpenStreetMap by default, Google Maps optional), shows satellite signal strength, radar view, and recent NMEA sentences.

## What it does
- Connects to a GPS module over Web Serial (Chrome/Edge/Opera).
- Parses NMEA sentences (via Rust `nmea-visualizer` compiled to WebAssembly).
- Displays live position, fix, PDOP/HDOP/VDOP, speed, course, and geoid separation.
- Shows satellite signal strength (bar chart) and sky view (radar).
- Maps: OpenStreetMap default, optional Google Maps tiles; Map/Satellite toggle.
- PWA build with offline assets; system log for status/events.

## Prerequisites
- Rust (https://www.rust-lang.org/tools/install)
- wasm-pack (https://rustwasm.github.io/wasm-pack/installer/)
- Node.js 18+ (https://nodejs.org/) and pnpm 10+ (https://pnpm.io/installation)
- Chrome/Edge/Opera for Web Serial support

## Project layout
- `src/` (Rust): core parser compiled to WebAssembly
- `pkg/`: generated wasm + JS bindings (built by wasm-pack)
- `www/`: Vite + SolidJS frontend
- `tests/`, `www/src/components/`, `www/src/services/`: frontend logic
