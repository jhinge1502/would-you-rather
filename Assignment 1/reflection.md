# Assignment 1: Rapid Prototyping — Reflection

## 1. What files make up your site and what does each one do?

The site consists of 26 HTML files:

- **index.html** — The gallery page. It serves as the homepage and tells the story of the design process across 4 phases (Go Wide, Converge, Narrow Down, Refine). Each version is presented as a clickable card organized by phase, with descriptions explaining the design intent. It links to all 25 versions and highlights v25 as the final choice.

- **v1.html through v25.html** — 25 standalone landing pages, each a fully interactive "Would You Rather" quiz. Every version contains the same 10 dilemmas (with TV/movie character references like Michael Scott, Dwight Schrute, Chandler Bing, Ron Swanson, etc.), the same scoring logic (tracking chaotic vs. safe picks), and the same personality result system (5 tiers from "The Absolute Menace" to "Safety Manual"). What changes across versions is the visual design — layout, typography, color palette, progress indicators, button styles, and overall mood.

There are no external dependencies, no frameworks, and no build tools. Each file is self-contained with inline CSS and vanilla JavaScript. The site uses Google Fonts via CDN links for typography variety across versions.

## 2. Describe the pipeline: what happens from git push to your site updating on Vercel?

When I run `git push`, the following happens:

1. **Git pushes commits** to the remote repository on GitHub (`github.com/jhinge1502/would-you-rather`).
2. **GitHub sends a webhook** to Vercel, notifying it that new commits have arrived on the `master` branch.
3. **Vercel receives the webhook** and pulls the latest code from the repository.
4. **Vercel runs its build process** — since this is a static site with no build step (pure HTML/CSS/JS), it simply identifies and serves the static files from the configured root directory (`Assignment 1/`).
5. **Vercel deploys the files** to its global CDN (Content Delivery Network), making them available at the assigned `.vercel.app` URL.
6. **The live site updates** — typically within seconds. Each deployment gets a unique preview URL, and the production URL always points to the latest deployment on the main branch.

The entire pipeline is automatic after the initial setup. Every push to `master` triggers a new deployment with zero manual intervention.

## 3. Justify v25 — after your entire exploration, why did you land on this version?

The journey to v25 was a funnel of creative decisions:

**Going wide (v1–v10)** revealed what worked and what didn't. The neon arcade (v2) and vaporwave (v8) were fun but hard to read. The brutalist (v4) was bold but felt hostile for a playful quiz. The magazine editorial (v3) was elegant but too formal. The split-screen duel (v6) was engaging but only worked on desktop. The bubblegum (v10) was energetic but too niche. What consistently felt right was the gradient party (v5) and the dark, focused layouts — they let the funny content breathe.

**Converging (v11–v15)** confirmed the direction. The glassmorphism from v15 and the dark minimal from v14 stood out because they created visual hierarchy without competing with the quiz content. The dark background focuses attention, the glass card frames each question as a moment, and the gradient accents (gold for highlights, pink-purple for interaction) add warmth without distraction.

**Refining (v21–v25)** was about feel, not look. v21 established the foundation. v22 added breathing room with more padding and a fade-in transition that makes each question feel intentional. v23 replaced the progress dots with a smooth gold progress bar — more satisfying to watch fill. v24 added the animated gradient border that gives the card a subtle, living quality. v25 perfected the spacing: more room at the top, a barely-visible gradient in the background that adds depth, and a polished results page that makes the personality reveal feel like a real moment.

v25 is the version where nothing feels like it needs to change. The design serves the content — the funny questions and pop culture references are the star, and the UI gets out of the way while still feeling premium and intentional.
