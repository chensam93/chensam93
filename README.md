Welcome to my repo, almost everything is just vibecoded projects.

Most of what I build is private, so each project below has screenshots and a short tour to show what it does.

**Jump to:** [no-rake](#no-rake) · [job-autofill](#job-autofill) · [humble-beginnings](#humble-beginnings) · [gmail-calendar-sync](#gmail-calendar-sync) · [sleeper-fantasy](#sleeper-fantasy) · [insider-smells](#insider-smells) · [polytopia-plus](#polytopia-plus) · [sql-interview-prep](#sql-interview-prep)

---

## Private projects

### no-rake

<sub>Node · Fastify · WebSockets · React · Postgres · Railway &nbsp;|&nbsp; ~95% agent &nbsp;|&nbsp; <a href="https://no-rake-server-production.up.railway.app/">Play →</a></sub>

Virtual Texas hold'em for friends and family, no real money. It started as "PokerNow, but with more features."

- Full no-limit hold'em from preflop to showdown, including side pots and all-in runouts
- Private rooms over WebSockets, host controls (adjust stacks, kick, move seats) and optional bots
- Every hand is saved: replay any hand street by street, see all-in EV, and export the ledger to CSV
- CI runs Playwright end-to-end tests on desktop, mobile Chrome, mobile Safari and tablet

<table>
<tr>
<td width="50%"><img src="assets/no-rake-table.jpg" alt="no-rake poker table mid-hand with the betting controls open"></td>
<td width="50%"><img src="assets/no-rake-hand-history.png" alt="no-rake hand history panel replaying a showdown street by street"></td>
</tr>
<tr>
<td align="center"><sub>A live hand at the table</sub></td>
<td align="center"><sub>Hand history with street-by-street replay</sub></td>
</tr>
</table>

---

### job-autofill

<sub>Chrome extension (Manifest V3) · TypeScript · esbuild · Playwright &nbsp;|&nbsp; ~95% agent</sub>

Fills job applications from a profile stored locally. It never submits anything; you review every field first.

- Matches fields on any page by label, placeholder, name and ARIA, then adds fixes for specific applicant tracking systems (Greenhouse, Ashby, iCIMS, Workday, Lever and others) where the generic match fails
- Handles the awkward inputs: custom dropdowns, comboboxes, split phone fields and demographic questions
- After each fill, a review panel lists what was filled, what was skipped and what it's unsure about
- Optional AI drafts for open-ended questions, always editable; there's no backend
- Tested against a library of saved application forms

<img src="assets/job-autofill-fill.png" alt="job-autofill popup reporting 13 of 14 fields filled on a Greenhouse-style application form">
<p align="center"><sub>A sample profile ("Jane Example") filling a test form built like a real Greenhouse application. 13 of 14 fields filled; the résumé shows as missed because none was loaded.</sub></p>

---

### humble-beginnings

<sub>Unity 6 · C# · 2D URP &nbsp;|&nbsp; ~95% agent</sub>

My first real game: a tactical RPG with two loops. You grow a hand-built base from a small camp out across a continuous landmass, and you fight roguelike battles.

- The world map lives in a text file (`map.json`) that syncs into the scene, so a hundred-odd hand-placed locations can be edited and reviewed like code
- A custom Unity menu handles the busywork: preparing art, rebuilding the UI, scattering foliage, roughing in terrain and capturing screenshots
- A small command bridge lets outside scripts run those same editor actions while Unity is open

<p align="center"><img src="assets/humble-beginnings-camp.png" width="620" alt="humble-beginnings pixel-art camp with a timber house, firewood and labelled map locations"></p>
<p align="center"><sub>The starting camp and the first location on the map</sub></p>

---

### gmail-calendar-sync

<sub>Node · Gmail API · Google Calendar API · OpenAI &nbsp;|&nbsp; ~95% agent</sub>

Turns my inbox into calendar events every day, then emails me a summary of what changed.

- Handles calendar invites (ICS files), including updates and cancellations
- Picks up appointment emails that have no invite attached
- Package tracking: shipping emails become all-day delivery events that move when the ETA changes, using the live UPS tracking API
- An LLM reads personal and important threads and turns them into follow-ups and meetings, checking for an existing event first so nothing is added twice

<p align="center"><img src="assets/gmail-calendar-sync-digest.png" width="560" alt="gmail-calendar-sync summary email listing created, updated and cancelled events"></p>
<p align="center"><sub>The summary email, produced by the project's own formatter. The events are made-up sample data.</sub></p>

---

### sleeper-fantasy

<sub>React · TypeScript · Vite &nbsp;|&nbsp; ~95% agent</sub>

A local dashboard for my fantasy football team. It tells me which waiver claims and trades to make for my Sleeper league.

- Six tabs: Plan, Team, Waivers, Trades, Analysis and League
- Scores every trade and waiver claim by how many lineup points it adds over the rest of the regular season, using only legal lineups
- Averages expert rankings from FantasyPros, ESPN and RotoBaller, and runs seeded season simulations for playoff and title odds
- Read-only: it uses Sleeper's public API and can't submit anything. Saved inputs can be replayed offline to check any recommendation

<img src="assets/sleeper-fantasy-pipeline.png" alt="sleeper-fantasy pipeline: Sleeper API, expert ranks and projections feed a local cache, then an analysis engine, then the React dashboard">

---

### insider-smells

<sub>Python · uv · Postgres · Alembic · Railway &nbsp;|&nbsp; ~95% agent</sub>

Research tooling for Polymarket. The goal is to spot trading that looks coordinated or unusually well timed: who traded, how much, and how early.

- Streams live trades from Polymarket's market WebSocket and backfills historical fills from the public orderbook subgraph
- Stores everything in one Postgres database, removing duplicates, with versioned schema migrations
- A small password-protected dashboard confirms the data is flowing
- Next up: linking wallets, scoring timing and alerts. This is for research, not legal advice

<img src="assets/insider-smells-pipeline.png" alt="insider-smells pipeline: live feed, historical fills and market list go through ingest into Postgres and a dashboard">

---

### polytopia-plus

<sub>TypeScript · React · Three.js · Fastify · SQLite · Vitest &nbsp;|&nbsp; ~95% agent</sub>

A strategy game inspired by The Battle of Polytopia, for a private group of friends. It recreates the base game's rules and adds our own custom features.

- A rules engine that runs with no graphics and always gives the same result for the same moves, with content matched to the Steam v2.16.5 release
- Map generation, an invite-code lobby and online multiplayer where players take turns at their own pace, with the server deciding what's legal
- A 3D board built with Three.js, plus the tech tree, combat previews and a phone layout
- The current phase is visual polish: matching the original game's look, screenshot by screenshot

<table>
<tr>
<td width="50%"><img src="assets/polytopia-plus-board.png" alt="polytopia-plus 3D board late game, with a combat preview tooltip"></td>
<td width="50%"><img src="assets/polytopia-plus-tech-tree.png" alt="polytopia-plus radial tech tree"></td>
</tr>
<tr>
<td align="center"><sub>Late game on turn 20, previewing an attack</sub></td>
<td align="center"><sub>The tech tree</sub></td>
</tr>
</table>

---

## Public projects

### sql-interview-prep

<sub>DuckDB · Python &nbsp;|&nbsp; ~70% agent &nbsp;|&nbsp; <a href="https://github.com/chensam93/sql-interview-prep">View repo →</a></sub>

Interview-style SQL questions backed by DuckDB sample data. You run queries against real rows instead of whiteboarding on paper.
