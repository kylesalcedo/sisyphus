# Sisyphus

A minimalist idle clicker game in a single HTML file. Click the boulder. Push it up the hill. Forever.

**[Play it now](https://kylesalcedo.github.io/sisyphus/sisyphus.html)**

Sisyphus doubles as a finger workout. Every click is a rep — build Calloused Hands, earn an Iron Grip, and work toward Atlas' Grip one press at a time. If you're on a trackpad, try alternating fingers (index, middle, ring) to spread the effort and strengthen each one. Both left and right clicks count, so you can train your index finger with right-clicks too.

Built with vanilla HTML, CSS, and JavaScript — no dependencies, no build step. Just open `sisyphus.html` in a browser.

## Features

- **Click the boulder** to push it up the hill. Both left-click and right-click register. Meters accumulate as currency and lifetime score.
- **Upgrades** across three categories:
  - **Strength** — increase meters per click
  - **Helpers** — passive meters per second (the idle part)
  - **Blessings** — one-time multipliers to all production
- **Progressive disclosure** — upgrades are censored/blurred until you approach their cost (40% threshold).
- **Prestige system** — "Let the Boulder Fall" resets upgrades but grants a permanent +25% production multiplier. Your first prestige rewards you with a detailed boulder texture. Cost scales: 50k, 150k, 450k, ...
- **Daily Rites** — three customizable real-world habits (rename them to anything) that grant +50% production for 1 hour and build streaks for permanent bonuses.
- **Milestones** — achievements for lifetime meters, prestige count, and habit streaks.
- **Canvas scene** — parallax mountains, seamless looping hill, animated stick-figure Sisyphus, rotating textured boulder.
- **Idle earnings** — production continues in the background (even when tab is unfocused). Offline earnings calculated on return (up to 8 hours).
- **Auto-save** every 30 seconds to localStorage.

## Visual Effects

- **Scaled dust particles** — density and intensity grow with production rate
- **Ambient floating motes** — subtle drifting particles that appear with progression
- **Helper shadow figures** — ghostly silhouettes behind Sisyphus, up to 5 based on helpers purchased
- **Blessing glow** — white aura around the boulder that grows with blessings owned
- **Teumessian Fox** — a companion fox that trots alongside Sisyphus (unlocked with Stoic Acceptance)
- **Guardian Angel** — floats to the left of Sisyphus with flapping wings (unlocked with Olympian Favor)
- **Prestige boulder** — first prestige upgrades the procedural boulder to a detailed rock texture

## Tech

- Single HTML file + one image asset
- HTML5 Canvas with `requestAnimationFrame` for rendering
- `setInterval` (250ms) for economy ticks (works when tab is hidden)
- Seamless hill via pre-generated sine-wave noise tiles
- 3-layer parallax (mountains 0.05x, mid hills 0.15x, ground 1x)
- Google Fonts: Cinzel (headers) + Crimson Text (body)
- Black, white, grey palette only
- Hosted on GitHub Pages — no server required
