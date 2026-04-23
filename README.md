<div align="center">

# DPlearn

### An Interactive Course on Differential Privacy

**9 hands-on modules · ~45–60 minute guided flow · zero setup**

[**Launch the app →**](https://mrg-hazmatz.github.io/dplearn/) · [Presentation Companion](./DPlearn_Presentation_Companion.html) · [Report a bug](../../issues) · [License](#license)

---

</div>

## What is this?

**DPlearn** is a single-page interactive web applet that teaches differential privacy from first principles to real-world deployment. Built for classroom demos, conference presentations, and self-paced learning, it moves anyone — from a curious undergraduate to a seasoned data scientist — through an intuitive understanding of *why* differential privacy exists and *how* it works.

No slides. No lecture. Every idea lands through a demo you run yourself.

## Modules

| # | Module | What you do |
|---|--------|-------------|
| 0 | **The Hook** | Three real-world breaches (Equifax, OPM, Cambridge Analytica) ground the question: why does privacy math matter? |
| 1 | **Key Terminology** | Explore 15 core terms — epsilon, delta, sensitivity, noise, composition, and more — with plain-English definitions and real-world examples |
| 2 | **Privacy Attacks** | Run five live attack demos yourself: *Differencing*, *Reconstruction* (story-driven investigative game), *Membership Inference* (probe an AI), *Linkage*, and *Re-identification* on an interactive US map |
| 3 | **Randomized Response** | Answer a sensitive question; watch a **protocol flowchart** map out both branches of the two-coin decision tree; preview the **50 / 25 / 25 probability table**; then flip two coins and see which branch you landed on ("You landed on the *truth* branch — 50% chance — the server got your real answer"). Scale to 300 people on dual live graphs, then take the **Case Study Challenge** — crack the true rate of a hidden 500-student dataset using the reconstruction formula |
| 4 | **The ε Dial** | Drag an interactive epsilon knob and watch noise, privacy, and utility change in real time on a 24-hour city traffic dataset. Published industry presets (Google Mobility, Apple Health, LinkedIn) marked on the dial for calibration |
| 5 | **Local vs Central DP** | Animated side-by-side comparison of the two deployment models with live data-flow visualization |
| 6 | **The Secret Map** | A 4×5 grid hides one 💎. Calibrate an ε slider per peek (blurry & cheap vs crisp & expensive), drain your 2.0 ε budget, then commit to a final guess. Finishing a hunt unlocks the **Real-World Case Study** — a medical-registry attack simulator plus four deep-dive cards (US Census 2020, genetic databases, Strava heatmaps, pharmacy records) showing where this exact composition mechanic decides privacy in production |
| 7 | **Industry Deployments** | Detailed case cards for Apple, Google, LinkedIn, Uber, and Microsoft — epsilon values, mechanisms, and published deployments |
| 8 | **Quiz** | 10 randomized questions from a 32-question pool, full review with explanations, and a score screen |

## What's in the repository

| File | Purpose |
|------|---------|
| [`dplearn.html`](./dplearn.html) | The entire interactive course — open this to learn |
| [`DPlearn_Presentation_Companion.html`](./DPlearn_Presentation_Companion.html) | Presenter's guide: module-by-module flow, Coin Flip formula derivation, Membership Inference & AI-era deep dive, two landmark breach case studies, and the Secret Map ε/cost explanation |
| [`index.html`](./index.html) | Root redirect for GitHub Pages hosting |
| [`README.md`](./README.md) | This file |

## Tech Stack

| Layer | Technology | Why |
|-------|-----------|-----|
| UI framework | React 18 (UMD via CDN) | Component model, hooks, no build step |
| JSX compilation | Babel Standalone | Write clean JSX directly in the HTML — compiled in-browser |
| Data visualization | D3.js + TopoJSON | US map rendering, SVG line charts, inline flowchart graphics |
| Fonts | Google Fonts (Syne, DM Sans, JetBrains Mono) | Clean typographic hierarchy |
| Styling | Inline styles + CSS keyframes | Zero dependencies, everything in one file |
| Deployment | Static HTML | Double-click to run, host anywhere |

**The entire course ships as a single HTML file.** No `npm install`. No build step. No server required.

## Quick Start

### Option A — Just open it
```
Double-click dplearn.html
```
That's it. Works in any modern browser.

### Option B — Local server (for classroom demos)
```bash
cd differential-privacy-applet
python -m http.server 5500
# Open http://localhost:5500/dplearn.html
```
Share your local IP with the room so everyone can follow along on their own device.

### Option C — Deploy to the web
Host `dplearn.html` anywhere that serves static files — GitHub Pages, Netlify, Vercel, S3, or a USB stick.

## Using DPlearn for teaching

A companion presenter's guide, [`DPlearn_Presentation_Companion.html`](./DPlearn_Presentation_Companion.html), is included in the repo. Open it in a browser (or print it to PDF — it's styled for that too) for:

1. **Presentation flow** — Per-module speaker notes, pacing, and audience prompts (runs ~45–60 min start to finish)
2. **Coin Flip formula** — Algebraic derivation of how `p_true = 2 × p_reported − ½` falls out of the two-coin protocol
3. **Membership Inference & the AI era** — Shokri's shadow-model attack, Carlini's verbatim GPT-2 extractions, diffusion-model training-data leaks, GDPR / EU AI Act implications, DP-SGD as the standard mitigation
4. **Two landmark breach deep-dives** — Cambridge Analytica (87M profiles) and Sweeney's 1996 re-identification of the Massachusetts governor
5. **The epsilon vs cost distinction** — Exactly why the Secret Map's slider and budget are two *different* quantities (noise parameter vs accumulated spend), with worked numbers

## Key Design Decisions

- **Single-file architecture** — The entire app ships as one `.html` file. No build chain, no dependency hell. Copy it to a USB drive and it runs on any machine with a browser and an internet connection (for CDN libraries).

- **Story-driven attacks** — The Reconstruction Attack puts you in the shoes of Reporter Quinn investigating salary gaps at Luna Labs. Each aggregate query you run visibly collapses the search space until every salary is exposed.

- **Both possible worlds, every time** — The Coin Flip module shows the full decision tree before you click (SVG flowchart + 50/25/25 probability table), then names which branch the coin landed on after the flip ("*truth* branch — 50% chance — the server got your real answer"). Learners never have to wonder which of two worlds they're in.

- **Dual live graphs** — The Coin Flip simulation shows "what people really answered" alongside "what the server sees" updating in real time, making noise injection viscerally obvious.

- **Case Study Challenge** — Instead of just showing the reconstruction formula, we generate a fresh hidden dataset (500 students, academic honesty survey) and dare you to crack it. Retry with new random data as many times as you like.

- **Privacy budget as a game, then as life or death** — Module 6 reframes the abstract "every query costs ε" rule as a treasure hunt. A 20-tile map, one hidden 💎, a 2.0 ε budget, and a slider that trades peek clarity against cost. When the budget runs out you must commit to a final guess — exactly the dynamic that stops a real attacker from averaging away the noise through repeated queries. Finishing a hunt then unlocks a **Real-World Case Study**: a medical-registry attack you run yourself (seven aggregate queries compose into a one-patient identification), plus four full-paragraph deep dives on where this same pattern decides privacy in production — the US Census 2020 DP deployment, genetic-testing databases, the Strava heatmap incident, and pharmacy/insurance records.

- **Fact-checked industry data** — Every epsilon value cited for Apple, Google, LinkedIn, Uber, and Microsoft is sourced from published papers or policy documents. Apple's tier breakdown (ε=1 for Photos scene learning, ε=2 for Health type data, ε=4 for emoji/Safari high-resource domains, ε=8 for lookup hints, ε=16 for QuickType) reflects the company's own *Differential Privacy Overview* and *Learning with Privacy at Scale* paper.

- **Accessible by default** — Keyboard navigation (arrow keys), session-persisted progress, responsive layout, focus-visible states, and a dark theme that's easy on the eyes in dim lecture halls.

## Browser Support

Tested on Chrome, Edge, Firefox, and Safari (latest versions). Mobile-responsive down to 375px width.

## License

MIT — use it, remix it, teach with it.

---

<div align="center">

Built for learning. Built for teaching. Built to make differential privacy click.

</div>
