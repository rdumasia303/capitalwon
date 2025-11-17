# CAPITAL WINS

An unhinged single-file browser game — "Capital Won, Labor lost."  
You're a tiny neon worker in a hostile corporate arena: collect paychecks, dodge drones and managers, organize your coworkers, and survive the Board's whims. Equal parts satire and itch for you to punch The System with a mouse and a few keys.

---

## Play it now

- Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari).
- For a local web server (recommended when testing audio / cross-origin):
  - Python 3: `python -m http.server 8000` then open `http://localhost:8000/index.html`
  - Or: `npx serve` (if you have Node/npm)

index.html is a self-contained game (canvas + JS + WebAudio). No build step required.

---

## Quick controls

- Move: WASD or Arrow keys
- Hold Shift: Organizing aura (slows enemies, grows Solidarity)
- Space: Dash (consumes Hope)
- Click (mouse): Send "emails" (shoot)
- P: Pause

---

## What you'll see / core mechanics

- You are "Labor": a neon speck that collects paychecks (jobs).
- Jobs move toward the Monolith (Capital). Collect paychecks to earn score and wages.
- Debt grows over time (interest) and from enemy interactions. If debt gets out of hand, you lose.
- Drones: small hostile units that steal jobs and cause wage-theft when they hit you.
- Managers: larger, nastier foes that shrink wages, drain Hope, and cause disruptive "reorg" events.
- Solidarity: grows when you hold Shift to organize; it helps repel drones and blunt management.
- Hope: your stamina-like resource. Dashing and organizing consume Hope.
- Choices: Periodic two-option cards that change rules (side-hustle, union whisper, stock options, etc.). Choose wisely — the game's joke is that every upgrade has a cost.
- The Monolith / Board: the game's thematic final pressure — a timer or conditions force an endgame.

Win conditions are intentionally ambiguous: it's more about surviving and experiencing the satire than "beating" a strict campaign. You can lose by sinking into too much debt or certain scripted board events.

---

## UI elements

- Net Worth: total money/score (top-left UI)
- Debt: current debt with progress bar (keeps growing via interest)
- Hope: percentage, fuels dashes and actions
- Solidarity: percent, increases with organizing (Shift)

---

## Tips & strategies

- Use Shift to build Solidarity before big waves of drones — it slows and repels them.
- Don't spam the dash — it costs Hope and can leave you vulnerable.
- Shoot at drones and managers to disrupt their activities (click/hold mouse).
- Pay attention to choice cards — they can radically shift the balance for better or worse.
- Keep an eye on debt progress bar — interest compounds fast.

---

## Internals / For tinkering

index.html is a single self-contained file that contains:
- Canvas rendering and particle effects
- Simple entity systems: jobs, drones, managers, bullets, particles, texts
- Procedural WebAudio (no external audio assets) — generative music + SFX
- Tunable constants near the top/middle of the file

Some of the key tunables (variable names in the code)
- HOPE_REGEN — how quickly Hope recovers
- SOL_GROWTH — rate Solidarity increases while organizing
- MANAGER_MEANNESS — affects manager penalties
- MANAGER_SPEED — base manager movement multiplier
- DRONE_GREED — affects how punitive drones are
- JOB_RATE — spawn rate modifier
- PAY_SHRINK — shrinks paycheck value (for “gig” mode)
- game.debtMax — baseline debt capacity before game over
- game.timers (spawn, drone, manage, memo, choice, board) — control spawn & event cadence

If you want to change difficulty or behavior, open `index.html` in a text editor and search for the above names to experiment.

---

## Development notes

- No external assets — everything (sound, visuals) is generated in-browser.
- To debug visuals or gameplay behavior, open DevTools Console and tweak variables live.
- Audio: uses the WebAudio API. Browsers typically require a user gesture before starting audio; starting the game triggers/resumes audio context.

---

## Contributing

- This is a small, single-file project. If you have a fix, tweak, or idea:
  - Fork the repo
  - Edit `index.html` (or extract modules if you prefer)
  - Submit a PR with a short description of changes

Small PR suggestions:
- Add a proper LICENSE file if you want explicit sharing terms
- Add a screenshot / animated GIF to the README for a preview
- Split the large `index.html` into modules for maintainability (optional)

---

## Credits & Attribution

- Author / repo owner: rdumasia303 (check Git history in the repo)
- Game design, art, and audio: all embedded in `index.html` (procedural)
- Inspired by messy, capitalist-grade satire. A neon shrug in one file.

---

## License

No license file is present in the repository. If you want others to reuse or remix the game, add a license (e.g. MIT) to make permissions explicit.
