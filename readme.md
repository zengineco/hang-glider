You are a full-stack savant and expert game developer specializing in addictive endless runners and mobile-first arcade games. Create a complete, production-ready, responsive single-page application (SPA) called **GlideFury** — a forward/up-scrolling hang gliding survival game where the player soars through endless skies, dodging deadly aerial obstacles like flying squirrels, bats, birds, helicopters, and planes.

## Core Gameplay (Precise Mechanics)
- **Endless Scroller**: Screen auto-scrolls upward/forward at accelerating speed (start 2px/frame → ramp to 10px/frame). Player hang glider stays centered horizontally but can move up/down/left/right within screen bounds.
- **Controls** (mobile/desktop perfect):
  | Device    | Primary Control          | Fallback          |
  |-----------|--------------------------|-------------------|
  | Mobile    | Tilt phone (DeviceMotion) or touch-drag | Virtual joystick |
  | Desktop   | Mouse move / Arrow keys  | WASD             |
- **Obstacles** (spawned in lanes, increasing density/speed):
  1. **Flying Squirrels** (small, fast, erratic zig-zag, acorn trail)
  2. **Bats** (flocking swarms, swoop in waves)
  3. **Birds** (flocks in V-formation, realistic gliding)
  4. **Helicopters** (large, slow, rotating blades, searchlight beam)
  5. **Planes** (massive, rare, screen-spanning contrails, turbulence wake)
- **Collision**: Touch any obstacle = instant death + dramatic crash animation (glider spins, feathers/particles explode).
- **Scoring**: Distance (primary) + multipliers for combos (perfect dodges), rare obstacles survived, airtime bonuses.
- **Powerups** (falling from destroyed obstacles or clouds):
  - Shield (invincible 5s, glowing aura)
  - Speed Burst (double scroll speed temporarily)
  - Magnet (auto-collect coins)
- **Game States**: Menu → Playing → Crashed (score screen) → High Score (localStorage + optional backend).

## Visual Design: Epic Sky Adventure Aesthetic
- **Background**: Parallax layered infinite sky:
  - Layer 1: Fast-moving clouds (puffy, volumetric)
  - Layer 2: Distant mountains/horizon
  - Layer 3: Starry sunset/night cycle (day→dusk→night over distance)
- **Player**: Sleek hang glider with fabric flaps, pilot silhouette, dynamic banking animation (tilt on turns).
- **Obstacles** (high detail, smooth 60fps sprite animation):
  | Obstacle     | Visual Style                  | Behavior          |
  |--------------|-------------------------------|-------------------|
  | Squirrels   | Bushy tail, acorn bombs      | Zigzag, chitter   |
  | Bats        | Leathery wings, glowing eyes | Flock waves       |
  | Birds       | Feathered, flapping          | V-formation       |
  | Helicopters | Rotors spin, metallic shine  | Patrol patterns   |
  | Planes      | Jet streaks, wing flex       | Straight + barrel |
- **Effects**: Particle explosions, screen shake, motion blur on high speeds, lens flare on sun, turbulence distortion.
- **UI**: Minimalist HUD — score/distance top-right, multiplier gauge bottom, "SWOOSH" combo text bursts.

## Technical Requirements: Full-Stack, GitHub-Ready, PWA-Capable
- **Frontend**: Vanilla JS + HTML5 Canvas (requestAnimationFrame 60fps loop). No frameworks for max performance.
- **Backend** (for leaderboards/high scores): Node.js/Express + Supabase/PostgreSQL integration.
- **Folder Structure**:
/glidefury/
├── index.html
├── css/style.css (CSS vars: --sky-blue, --squirrel-brown)
├── js/
│   ├── main.js         (game loop, input)
│   ├── player.js       (glider physics)
│   ├── obstacles.js    (spawning/AI)
│   ├── renderer.js     (canvas magic)
│   ├── particles.js    (explosions/trails)
│   └── leaderboard.js  (Supabase client)
├── assets/             (sprites optional, all vector/JS-drawn)
├── backend/
│   ├── server.js
│   └── package.json
└── README.md
text- **Physics**:
- Smooth inertia (lerp position to input)
- Collision: Circle-rect + pixel-perfect optional
- Obstacle AI: Sine waves, bezier curves, flocking (Boids-lite for bats/birds)
- **Audio**: Web Audio API — whooshing wind, obstacle screeches, crash boom, combo chimes.
- **PWA**: Service worker for offline, install prompt, push for daily challenges.
- **Responsive**: Fullscreen mobile, landscape lock, gyro calibration.

## Progression & Replayability
Distance = scrollSpeed × survivalTime
Score = distance × multiplier + (rarePlaneDodges × 1000)
High Score persistence + Global Leaderboard (name + score + glider cosmetic)
Daily Challenge: Fixed seed obstacle pattern, bonus rewards
Achievements: "Squirrel Slayer" (100 kills), "Plane Whisperer" (dodge 5 planes)
text## Backend APIs (Supabase-Ready)
POST /api/score → {username, score, distance, timestamp}
GET /api/leaderboard → Top 100 weekly/global
GET /api/daily-challenge → {seed, targetDistance, topPlayers}
text## Performance Targets
- 60fps on mid-range mobile (iPhone 12 / Galaxy S20 equivalent)
- <100KB initial load (gzip)
- No GC pauses (object pooling for particles/obstacles)

## Output Format (Copy-Paste Ready)
1. **Complete frontend code** (single index.html + modular JS/CSS)
2. **Backend code** (server.js + Supabase setup SQL)
3. **Deploy guide**: GitHub Pages (frontend) + Vercel/Railway (backend)
4. **Demo replay** with sample obstacle waves
5. **Customization**: "Swap squirrels for drones in 3 lines"

Make it **brutally addictive** — that "one more run" itch. Polish to itch.io/App Store quality. Include mobile tilt controls that feel like REAL hang gliding. Generate FULL WORKING CODE now. 🪂✈️🐿️
P
