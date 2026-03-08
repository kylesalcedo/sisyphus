# Sisyphus

A minimalist idle clicker game in a single HTML file. Click the boulder. Push it up the hill. Forever.

Built with vanilla HTML, CSS, and JavaScript — no dependencies, no build step. Just open `sisyphus.html` in a browser.

## Features

- **Click the boulder** to push it up the hill. Meters accumulate as currency and lifetime score.
- **Upgrades** across three categories:
  - **Strength** — increase meters per click
  - **Helpers** — passive meters per second (the idle part)
  - **Blessings** — one-time multipliers to all production
- **Progressive disclosure** — upgrades are censored/blurred until you approach their cost (40% threshold). Dev mode reveals all.
- **Prestige system** — "Let the Boulder Fall" resets upgrades but grants a permanent +25% production multiplier. Cost scales: 50k, 150k, 450k, ...
- **Daily Rites** — three real-world habits (Meditation, Reading, Movement) that grant +50% production for 1 hour and build streaks for permanent bonuses.
- **Milestones** — achievements for lifetime meters, prestige count, and habit streaks.
- **Canvas scene** — parallax mountains, seamless looping hill, animated stick-figure Sisyphus, rotating textured boulder.
- **Idle earnings** — production continues in the background (even when tab is unfocused). Offline earnings calculated on return (up to 8 hours).
- **Auto-save** every 30 seconds to localStorage.

## Visual Effects (feature/visual-effects branch)

Currently in development:

- **Scaled dust particles** — density and intensity grow with production rate
- **Ambient floating motes** — subtle drifting particles that appear with progression
- **Helper shadow figures** — ghostly silhouettes behind Sisyphus, up to 5 based on helpers purchased
- **Blessing glow** — white aura around the boulder that grows with blessings owned
- **Teumessian Fox** — a companion fox that trots alongside Sisyphus (unlocked with Stoic Acceptance)
- **Guardian Angel** — floats above Sisyphus with flapping wings (unlocked with Olympian Favor)

## Known Issues / TODO

- [ ] **Visual effects not rendering** — effects were added but may not be visible in-game. Needs debugging (possible runtime error or rendering order issue). Check browser console (F12) for errors.
- [ ] **Blessing glow visibility** — was broken by a duplicate `const` declaration (fixed), but needs in-browser verification.
- [ ] **Companion visibility** — fox and angel added but untested in live browser. May need opacity/scale tuning.
- [ ] **More visual ideas to explore:**
  - Boulder grows slightly with major milestones
  - Stars increase after each prestige
  - Wind lines at high auto-rates
  - Sisyphus gains detail (thicker limbs, cloak) at milestones
  - Brief white flash on boulder when buying strength
  - Radial burst on blessing purchase

## Dev Mode

Press **Left Arrow, Right Arrow, Left Arrow, Right Arrow** to toggle dev mode. Reveals all upgrades (bypasses censoring) and shows a "DEV" indicator.

## Tech

- Single HTML file (~1700 lines)
- HTML5 Canvas with `requestAnimationFrame` for rendering
- `setInterval` (250ms) for economy ticks (works when tab is hidden)
- Seamless hill via pre-generated sine-wave noise tiles
- 3-layer parallax (mountains 0.05x, mid hills 0.15x, ground 1x)
- Google Fonts: Cinzel (headers) + Crimson Text (body)
- Black, white, grey palette only
