# Token Radar — pre-token DeFi protocols ranked by implied value

A deterministic, data-driven token radar: every snapshot of the protocol universe in, a ranked board out. Reads a sealed snapshot of the DefiLlama protocol index once, scores every pre-token protocol with one published model, and writes a static dashboard (board.json + data.js + HTML/CSS/JS) that works offline (no network).

[Token Radar on make.fun](https://make.fun/c/token-radar-01) · [Competition](https://make.fun/c/token-radar-01)

[![Token Radar on make.fun](https://img.shields.io/badge/make.fun-Token%20Radar-blue?logo=github)](https://make.fun/c/token-radar-01)

## What it does

The radar covers the snapshot's watchlist of pre-token protocols (the floor — every protocol with at least the watchlist's TVL and no token on record) and adds an early radar of pre-token protocols below that floor, ranked by one shared implied-value model. Live-token protocols are set aside and shown with their market caps as facts, never mixed into the ranking.

Implied value is computed from the snapshot's own figures only: TVL × base multiple × growth multiplier × maturity multiplier, with growth clamped to the snapshot, a maturity curve from the protocol's age, and the constants stated in the dashboard and changeable in the model sandbox.

## Running it locally

Needs Node 22.18 or later. The program reads the sealed snapshot from `/input/snapshot.json` (or `--input <file|dir>`) and writes the dashboard to `/output` (or `--output <dir>` / `MAKEFUN_OUTPUT_DIR`).

```bash
mkdir -p out
MAKEFUN_OUTPUT_DIR=out node main.ts --input ../input/snapshot.json
# → board.json, data.js, dashboard (3 files), screenshots (3 images), dossier.json
```

## Dashboard

Open `dashboard/index.html` from the output directory — it reads `data.js` beside it and renders the ranked board, a filterable table, a per-protocol detail drawer with the model's own inputs and the protocol's farm plan. No framework, no network.

The `screenshots/` directory holds three captures of the dashboard: the board, a detail view, and a filtered view.

## Model

`lib/model.ts` holds the single shared scoring function and the model constants. Every protocol is scored by the same function — no name is special-cased, no row is hand-picked. The dashboard recomputes each row from the snapshot figures and checks it against `board.json`, so the page's code and the board's data are visibly the same arithmetic.

## License

MIT — see `LICENSE`.
