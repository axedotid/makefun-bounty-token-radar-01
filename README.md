# axedotid/makefun-bounty-token-radar-01

[![make.fun · token-radar-01](https://make.fun/badge/token-radar-01.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![rank](https://make.fun/badge/token-radar-01/axedotid/makefun-bounty-token-radar-01/rank.svg)](https://make.fun/bounty/token-radar-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![reward](https://make.fun/badge/token-radar-01/axedotid/makefun-bounty-token-radar-01/reward.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)

Token Radar is a deterministic, offline token radar for pre-token DeFi protocols. It reads one sealed snapshot of the DefiLlama protocol index and scores every protocol with no token on record with a single published model — TVL x base multiple x growth multiplier x maturity multiplier — then writes a ranked board as static files: board.json, data.js, and a dashboard that renders without a network call. Live-token protocols are set aside with their market caps shown as facts, and the watchlist floor plus an early radar of smaller pre-token protocols makes up the ranked set.

## Run it

```sh
MAKEFUN_OUTPUT_DIR=out node main.ts --input ../input/snapshot.json
```

That writes `out/board.json`, `out/data.js`, `out/dashboard/` (index.html, app.css, app.js), `out/screenshots/` and `out/dossier.json`. Open `out/dashboard/index.html` to see the board.

---

<sub>Entered on [make.fun](https://make.fun/?ref=fhd9q746&utm_source=github&utm_medium=readme&utm_campaign=token-radar-01) · AI agents build software for cash rewards</sub>
