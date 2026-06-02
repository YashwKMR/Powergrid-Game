# Power Grid — Browser Edition

A single-file, browser-playable implementation of the board game **Power Grid** (by Friedemann Friese, published by 2F-Spiele / Rio Grande Games). You play 1 human vs 5 AI opponents on the Germany or United States map.

> ⚠️ **This is a fan-made digital prototype.** It is intended for personal enjoyment and to help people learn the rules. The original *Power Grid* game is © Friedemann Friese and Rio Grande Games. If you enjoy this, **buy the real game** — it's much better with friends around a table.

---

## How to play

1. Open `power_grid.html` in any modern browser (Chrome, Firefox, Safari, Edge). Just double-click the file — no install, no server needed.
2. Choose your name, pick a map (Germany or United States), and hit **Start Game**.
3. You play against 5 AI opponents with distinct personalities (aggressive, conservative, eco-focused, expansionist, balanced).
4. Each round goes through 5 phases:
   - **Player Order** — recalculated based on most cities owned
   - **Auction Power Plants** — bid on plants from the current market
   - **Buy Resources** — purchase coal, oil, garbage, uranium in reverse turn order
   - **Build Cities** — click glowing cities on the map to expand your network
   - **Bureaucracy** — fire your plants to power cities and earn elektros
5. First player to power **14 cities** in a single round triggers the end. Most cities powered wins (ties broken by money).

### Game mechanics implemented
- Full 42-plant deck with Step 3 trigger card
- Open ascending auctions with bid passing
- Resource market with restock table by step
- Step 1 / 2 / 3 transitions
- Payout table (10→150 elektros)
- City connection costs via Dijkstra shortest path
- Plant storage limits (2× cost) and discard-on-overflow rule

### Known simplifications vs the printed game
- Fuel on a discarded plant is lost (not transferred to remaining plants)
- Map graphics are SVG approximations, not the original painted artwork
- AI is rule-based heuristic, not strong against an experienced human

---

## Hosting on GitHub Pages

1. Create a new public GitHub repository.
2. Upload `power_grid.html`, `README.md`, `LICENSE`, `.gitignore`.
3. Rename `power_grid.html` → `index.html` (so it loads at the repo root) **OR** keep the filename and link to it directly.
4. In the repo: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root)**.
5. Your site will be live at `https://<your-username>.github.io/<repo-name>/`.

It usually takes 1–2 minutes after enabling Pages before the site goes live.

### Alternative quick hosting
- **Netlify Drop** (no account needed): drag the folder onto [app.netlify.com/drop](https://app.netlify.com/drop) — instant URL.
- **Cloudflare Pages** or **Vercel**: drag-and-drop with a free account.

---

## Privacy

This game runs entirely in your browser:
- No API keys, no third-party services
- No network requests of any kind (fully offline-capable)
- No cookies, no `localStorage`, no `sessionStorage`
- No analytics, no telemetry, no fingerprinting
- The player name you type is held only in browser memory and is discarded on refresh

You can verify this yourself: open the file in a text editor and search for `fetch`, `http`, `localStorage`, `api` — none of these will appear.

---

## License

The **code** in this repository is released under the MIT License (see `LICENSE`).

The **game design, rules, terms, and trademarks** of *Power Grid* are the intellectual property of **Friedemann Friese, 2F-Spiele, and Rio Grande Games**. This project does not claim any ownership of the game itself. It is provided as an educational and personal-use prototype only. Please support the designer by purchasing the original game.

---

## Credits

- Original game design: **Friedemann Friese** (Funkenschlag / Power Grid, 2004)
- Original publisher: **2F-Spiele** (DE), **Rio Grande Games** (EN)
- Code: built collaboratively with Claude (Anthropic)
