<div align="center">

# DPlearn

### An Interactive Course on Differential Privacy

**9 hands-on modules · ~15 minutes · zero setup**

[**Launch the app →**](https://mrg-hazmatz.github.io/dplearn/) · [Report a bug](../../issues) · [License](#license)

---

</div>

## What is this?

**DPlearn** is a single-page interactive web applet that teaches differential privacy from first principles to real-world deployment. It was built for classroom demos, conference presentations, and self-paced learning — designed so that anyone from a curious undergraduate to a seasoned data scientist walks away with an intuitive understanding of *why* differential privacy exists and *how* it works.

No slides. No lecture. You learn by doing.

## Modules

| # | Module | What you do |
|---|--------|-------------|
| 0 | **The Hook** | See real data breaches (Equifax, OPM, Cambridge Analytica) and understand why privacy math matters |
| 1 | **Key Terminology** | Explore 15 core terms — epsilon, delta, sensitivity, noise, composition, and more — with plain-English definitions and real-world examples |
| 2 | **Privacy Attacks** | Run five live attack demos yourself: *Differencing*, *Reconstruction* (story-driven game), *Membership Inference* (probe an AI), *Linkage*, and *Re-identification* with an interactive US map |
| 3 | **Randomized Response** | Answer a sensitive question, watch the coin-flip protocol protect you, then scale it to 300 people with dual live graphs. Take the **Case Study Challenge** — apply the reconstruction formula to a hidden dataset of 500 students |
| 4 | **The ε Dial** | Drag an interactive epsilon knob and watch noise, privacy, and utility change in real time on a 24-hour city traffic dataset |
| 5 | **Local vs Central DP** | Animated side-by-side comparison of the two deployment models with live data-flow visualization |
| 6 | **The Secret Map** | A 4×5 grid hides one 💎. Calibrate an ε slider per peek (blurry & cheap vs crisp & expensive), drain your 2.0 ε budget, then commit to a final guess — privacy-budget composition turned into a treasure hunt |
| 7 | **Industry Deployments** | See how Apple, Google, LinkedIn, Uber, and Microsoft deploy DP in production with detailed case cards |
| 8 | **Quiz** | 10 randomized questions from a 32-question pool, full review with explanations, and a score screen |

## Tech Stack

| Layer | Technology | Why |
|-------|-----------|-----|
| UI framework | React 18 (UMD via CDN) | Component model, hooks, no build step |
| JSX compilation | Babel Standalone | Write clean JSX directly in the HTML — compiled in-browser |
| Data visualization | D3.js + TopoJSON | US map rendering, SVG line charts |
| Fonts | Google Fonts (Syne, DM Sans, JetBrains Mono) | Clean typographic hierarchy |
| Styling | Inline styles + CSS keyframes | Zero dependencies, everything in one file |
| Deployment | Static HTML | Double-click to run, host anywhere |

**The entire project is a single HTML file.** No `npm install`. No build step. No server required.

## Quick Start

### Option A — Just open it
```
Double-click dplearn.html
```
That's it. Works in any modern browser.

### Option B — Local server (for demos)
```bash
cd differential-privacy-applet
python -m http.server 5500
# Open http://localhost:5500/dplearn.html
```

Share your local IP with the room so everyone can follow along on their own device.

### Option C — Deploy to the web
Host `dplearn.html` anywhere that serves static files — GitHub Pages, Netlify, Vercel, S3, or a USB stick.

## Key Design Decisions

- **Single-file architecture** — The entire app ships as one `.html` file. No build chain, no dependency hell. Copy it to a USB drive and it runs on any machine with a browser and an internet connection (for CDN libraries).

- **Story-driven attacks** — The Reconstruction Attack puts you in the shoes of Reporter Quinn investigating salary gaps at Luna Labs. Each aggregate query you run visibly collapses the search space until every salary is exposed.

- **Dual live graphs** — The Coin Flip module shows "what people really answered" alongside "what the server sees" updating in real time, making the noise injection viscerally obvious.

- **Case Study Challenge** — Instead of just showing the reconstruction formula, we generate a fresh hidden dataset (500 students, academic honesty survey) and dare you to crack it. You can retry with new random data as many times as you like.

- **Privacy budget as a game** — Module 6 reframes the abstract "every query costs ε" rule as a treasure hunt. A 20-tile map, one hidden 💎, a 2.0 ε budget, and a slider that trades peek clarity against cost. When the budget runs out you must commit to a final guess — exactly the dynamic that stops a real attacker from averaging away the noise through repeated queries.

- **Accessible by default** — Keyboard navigation (arrow keys), session-persisted progress, responsive layout, focus-visible states, and a dark theme that's easy on the eyes in dim lecture halls.

## Browser Support

Tested on Chrome, Edge, Firefox, and Safari (latest versions). Mobile-responsive down to 375px width.

## License

MIT — use it, remix it, teach with it.

---

<div align="center">

Built for learning. Built for teaching. Built to make differential privacy click.

</div>
