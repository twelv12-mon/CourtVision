# 🏀 Court Vision

> **Real-time NBA scores, stats, standings, and highlights — all in one sleek dashboard.**

![Status](https://img.shields.io/badge/status-live-brightgreen?style=flat-square)
![Version](https://img.shields.io/badge/version-67.67-orange?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Vanilla JS](https://img.shields.io/badge/built%20with-Vanilla%20JS-yellow?style=flat-square)
![No Backend](https://img.shields.io/badge/backend-none-lightgrey?style=flat-square)

---

## 📸 Preview

> *A fast, dark-mode NBA dashboard with live score cards, box scores, MVP ladders, standings, and highlights — zero dependencies, zero backend.*

![visual](media/t.gif)

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔴 **Live Scores** | Auto-refreshing game cards with quarter-by-quarter breakdowns |
| 📊 **Box Scores** | Full player stats per game with shooting splits |
| 🏆 **MVP Ladder** | Hollinger Game Score ranking across all players on the day |
| 🎯 **Well-Rounded Ladder** | Z-score composite across PTS / REB / AST / STL / BLK |
| 📅 **Date Navigator** | Browse any date ±30 days from today |
| 🏟 **Standings** | Live East/West conference tables with streak and GB |
| 🎬 **Highlights** | YouTube search links + ESPN video cards + NBA.com |
| 📺 **Watch Guide** | Broadcast finder with League Pass, ESPN, Max, Peacock |
| ⚙️ **Settings Panel** | Toggle data sources, display options, and auto-refresh |
| 📡 **Live Ticker** | Scrolling scoreboard banner during live games |

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | Vanilla HTML / CSS / JavaScript (ES2022) |
| **Fonts** | Bebas Neue · Rajdhani · IBM Plex Mono (Google Fonts) |
| **Data** | ESPN Public API (no key required) |
| **Proxies** | corsproxy.io · allorigins.win (CORS fallback chain) |
| **Storage** | localStorage (settings persistence only) |
| **Build Tool** | None — single HTML file, zero bundler |
| **Dependencies** | None — fully self-contained |

---

## 📡 Data Sources

| Source | Used For | Notes |
|---|---|---|
| `site.api.espn.com` | Scoreboard, game summaries, box scores | Primary |
| `site.web.api.espn.com` | Standings, extended summaries | Secondary |
| `cdn.espn.com` | Standings fallback | Tertiary |
| `corsproxy.io` | CORS proxy for direct fetch failures | Auto fallback |
| `allorigins.win` | CORS proxy second fallback | Auto fallback |
| YouTube | Highlights search links | Link-out only |
| NBA.com | Official game pages, highlights | Link-out only |

---

## 📐 Stat Formulas

### 🏆 MVP Ladder — Hollinger Game Score

```
GmSc = PTS + 0.4·FGM − 0.7·FGA − 0.4·(FTA − FTM)
     + 0.7·OREB + 0.3·DREB + STL + 0.7·AST + 0.7·BLK
     − 0.4·PF − TOV
```

### 🎯 Well-Rounded Ladder — Z-Score Composite

```
Z = Σ[(stat − field_mean) ÷ field_stddev]  across PTS, REB, AST, STL, BLK
  − [(TOV − field_mean) ÷ field_stddev]     (turnover penalty)
```

> Each player is ranked against **the entire field of players that day**, not career averages. Stats are single-game only.

---

## ⚙️ Settings

| Option | Default | Description |
|---|---|---|
| `opt-autorefresh` | ✅ On | Refresh live scores every 60 seconds |
| `opt-ticker` | ✅ On | Show scrolling score ticker during live games |
| `opt-ladders` | ✅ On | Display MVP and Well-Rounded ladder sections |
| `hl-espn` | ✅ On | Show ESPN video cards in Highlights tab |
| `hl-youtube` | ✅ On | Show YouTube search links in Highlights tab |
| `hl-nba` | ✅ On | Show NBA.com links in Highlights tab |
| `src-nba` | ✅ On | Use NBA.com as standings fallback |
| `src-bref` | ✅ On | Use Basketball-Reference as standings fallback |

Settings are persisted to `localStorage` under the key `cv_settings_v1`.

---

## 🚀 Getting Started

**No install. No build. No server.**

```bash
# Clone the repo
git clone https://github.com/twelv12-mon/courtvision.git

# Open in browser
open site/NBA/main.html
```

Or just visit the live site — it's a single `.html` file you can host anywhere (GitHub Pages, Netlify, Vercel, etc.).

---

## 📁 Project Structure

```
site
└── README.md      # Just there to fill the folder space
└── NBA/
     └── main.html      # Entire app — HTML + CSS + JS in one file
```

---

## ⚠️ Known Limitations

> **Please read before filing issues.**

| Issue | Cause | Workaround |
|---|---|---|
| ESPN video links returning 404 | ESPN CDN URLs expire after ~48 hours | Switch to YouTube in the Highlights tab |
| Inline video playback blocked | ESPN serves videos with `CORP: same-origin` header (CORB) | Videos are link-out cards only by design |
| YouTube iframe search blocked | Google blocks YouTube search result embeds | Click cards to open YouTube in a new tab |
| Standings show wrong season | ESPN API `season` param uses the year the season *ends* | Season 2025–26 = `season=2026` |
| CORS errors on direct fetch | Browser security policy | App automatically retries through proxy chain |

---

## 🔒 Security & Privacy

- **No user data is collected.** The app runs entirely in your browser.
- **No API keys are required or stored.**
- The only data written to disk is your settings preferences in `localStorage`.
- All external requests go to ESPN's public endpoints and open CORS proxies.

---

## 📊 Project Stats

| Metric | Value |
|---|---|
| Lines of code | ~1,100 |
| External dependencies | 0 |
| API keys required | 0 |
| Bundle size | ~42 KB (unminified) |
| Fonts loaded | 3 (Google Fonts CDN) |
| Time to first meaningful paint | < 1s |

---

## 🗺 Roadmap

- [ ] Player profile pages
- [ ] Season averages alongside single-game stats
- [ ] Push notifications for close games
- [ ] Dark/light theme toggle
- [ ] PWA offline support

---

## 📄 License

MIT © 2026 [@ndubbb12](https://twitter.com/ndubbb12)

---

<div align="center">

**Data via [ESPN](https://espn.com) · Built with 🧡 by [@ndubbb12](https://twitter.com/ndubbb12)**

</div>
































































































.


































(yes i used ai to make this :sob:)
____