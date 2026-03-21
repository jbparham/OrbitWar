# Orbit War

A browser-based digital adaptation of the 1992 Steve Jackson Games boardgame designed by Wallace Wang. Two players command satellite fleets in near-Earth orbit, firing missiles, laying mines, and scoring Victory Points until one side leads by 200 VP.

> **Original game:** *Orbit War* © 1992 Steve Jackson Games  
> Design: Wallace Wang | Development: Steve Jackson

![Original Game](physical_game.jpeg)
![Digital Game](digital.png)

---

## Playing the Game

Open `orbit-war_17.html` in any modern browser. No installation, no build step, no server required — it is a single self-contained HTML file.

### Starting a Game

The welcome screen offers four entry points:

| Option | Description |
|--------|-------------|
| **Blockade** | Asymmetric 12-turn scenario. APU (45 pts) blockades USA (35 pts). Unbalanced by design — play twice and swap sides. |
| **Total War** | Symmetric 100 vs 100 pts. Full force composition. Ends at a 200 VP lead or cease-fire. |
| **⚡ Easy Start** | Loads a pre-built Total War force for both sides with random placement. Start playing in seconds. |
| **📡 Tutorial** | Interactive 17-step walkthrough on a live board. Covers two full turns, every mechanic explained in context. |

A second **Quick Tutorial** button in the bottom row launches a lighter in-game tutorial bar usable mid-session.

---

## Rules Summary

### The Board

The hex grid represents the region of near-Earth space. Concentric **Orbit Lines** (rings 1–10) determine each satellite's travel speed. A **Spotting Cone** on each side of the map represents national radar coverage — satellites score VPs when inside the *enemy's* cone.

**Orbital speeds (hexes per turn):**

| Ring | Speed |
|------|-------|
| 1 | 4 |
| 2–3 | 3 |
| 4–5 | 2 |
| 6–7 | 1 |
| 8–9 | ½ (even turns only) |
| 10 | ⅓ (every 3rd turn) |

All orbital movement is **counterclockwise and mandatory** — no unit may skip it.

---

### Turn Sequence (9 Phases)

| # | Phase | Notes |
|---|-------|-------|
| 1 | **Turn Track** | Missiles expire; Earth rotates every 4th turn (shifting Spotting Cones). Auto-resolves. |
| 2 | **Orbital Movement** | All units sweep CCW by their ring speed. Mandatory, no exceptions. Auto-resolves. |
| 3 | **Player A Launches** | Up to 3 ELR launches from Earth (rings 1–3); OLR launches from OWPs/Shuttles/Space Stations. |
| 4 | **Player B Launches** | Same as above for Player B. |
| 5 | **Player A Move** | Optional movement up to MA hexes, +1 free hex toward Earth (gravity assist). Resupply available. |
| 6 | **Player B Move** | Same as above for Player B. |
| 7 | **Mine Combat** | Mines, missiles, and nukes fire automatically against enemies in their hex. Auto-resolves. |
| 8 | **Normal Combat** | Both players attack using the Combat Results Table. Each unit attacks once only. |
| 9 | **Scoring** | VPs awarded; win condition checked. A scored summary toast appears. Auto-resolves. |

**Player A** goes first on odd-numbered turns; **Player B** on even turns.

Passive phases (1, 2, 7, 9) chain automatically with short pauses so players can read the results.

---

### Unit Reference

#### Satellites & Platforms

| Unit | ATK | DEF | MOV | Token | Key Rule |
|------|-----|-----|-----|-------|----------|
| **OWP** — Orbital Weapons Platform | 1 | 2 | 1 | Diamond | Fires OLRs (max 3/turn, 1 nuke max). Cannot attack same turn it fires OLRs (§17). Carries up to 10 weapons. |
| **HK** — Hunter-Killer | 4 | 3 | 2 | Pentagon | Primary combat unit. Fast and strong. |
| **SS** — Space Station | 4 | 4 | 1 | Wide rect | Costs 12 pts. Logistics hub; fires OLRs. Worth **10 VP** if destroyed. |
| **EWR** — Early Warning Recon | 0 | 1 | 1 | Tall narrow rect | Scores **3 VP/turn** when inside enemy Spotting Cone. Jammed (0 VP) if inside any CJS radius. |
| **COM** — Communications Satellite | 0 | 1 | 1 | Rounded square | Scores **2 VP/turn** over friendly territory. |
| **CJS** — Comm Jamming Satellite | 0 | 1 | 2 | Hexagon | Radius-2 area: +1 DEF friendly, −1 DEF enemy, 50% missile jam (roll 1–3 on d6), jams enemy EWRs. |
| **SF** — Special Forces | 3 | 2 | 1 | Rounded square | 12-turn orbital limit; must return to Earth or be removed (opponent scores VPs). |
| **Shuttle** | 2 | 1 | 2 | Rounded square | Logistics. Carries up to 12 weapons + Supply counter. Fires OLRs. Worth **3 VP** if destroyed. |
| **Supply Counter** | — | 1 | 0 | Octagon | Floating weapons cache (up to 10 weapons). OWP/Shuttle/SS in same hex may draw from it during movement. Removed when empty. |

#### Weapons & Rockets

| Unit | ATK | Notes |
|------|-----|-------|
| **Mine** | 6 | Stationary; auto-fires Mine Combat every turn. Cannot fire turn it is placed. |
| **Missile** | 5 | One turn only; auto-fires then is removed. Tracked on paper (no counter). |
| **Nuke** | 5 | Must be launched via OLR. Detonating costs the owner **10 VP**. |
| **3-MIRV / 7-MIRV** | 5 | Multiple warheads in one payload slot. |
| **ELR** — Earth-Launch Rocket | — | Launches from Earth; reaches rings 1–3. Max 3/turn. Costs 0.5 pts each. |
| **OLR** — Orbit-Launch Rocket | — | Free; launched from OWPs, Shuttles, Space Stations in orbit. Range 3 hexes. |

---

### Combat Results Table

Combat is resolved by subtracting the defender's effective DEF from the attacker's ATK. CJS modifiers apply before the lookup.

| Differential | Result | Meaning |
|:---:|:---:|---------|
| +4 to +6 | **DE** | Defender Eliminated |
| +2 to +3 | **DE** | Defender Eliminated |
| +1 | **DR** | Defender Retreats (1 hex toward Earth) |
| 0 | **EX** | Exchange — both destroyed |
| −1 | **EX** | Exchange — both destroyed |
| −2 to −3 | **AR** | Attacker Retreats |
| −4 to −6 | **AE** | Attacker Eliminated |

---

### Victory Points

| Event | VP |
|-------|----|
| EWR inside enemy Spotting Cone | +3 per turn |
| COM over friendly territory | +2 per turn |
| CJS over friendly territory | +2 per turn |
| Space Station destroyed | +10 (one-time, to destroyer) |
| EWR destroyed | +3 (to destroyer) |
| Shuttle destroyed | +3 (to destroyer) |
| OWP, HK, or SF destroyed | +1 (to destroyer) |
| Nuke or suicide detonated | −10 (to owner) |

**Win condition:** Lead by **200 VP** at the end of any Scoring phase, or hold the highest score when the turn limit is reached (Blockade: 12 turns).

---

### Key Rules Quick Reference

- **Orbital movement is always mandatory and counterclockwise.** No unit may skip it.
- **Mine Combat fires before Normal Combat.** A mine can destroy a unit before it gets to fight back.
- **Newly placed mines cannot fire on the turn they arrive** (indicated by an orange NEW badge on the token).
- **An OWP cannot both fire OLRs and attack in Normal Combat on the same turn** (§17).
- **A unit that resupplies from a Supply counter cannot attack that turn** (§12). It defends normally.
- **Detonating a nuke — including suicide nukes — costs 10 VP and hits every unit in the hex, friendly and enemy** (§18/§19).
- **SF units removed after 12 turns in orbit** if they have not returned to Earth. Opponent scores VPs for the removal.
- **EWRs jammed:** any CJS within radius 2 (friendly or enemy) jams an EWR — it scores 0 VP that turn.

---

## UI Guide

### Board

Click any hex to inspect units there. During active phases, clicking one of your own units selects it (green hexes show valid move destinations). During Combat, click an enemy in the same hex to attack.

**Hover over a CJS** to see its jamming radius highlighted in green.

**Hover over any hex** to see ring number and unit identities in the status bar at the bottom.

### Sidebar

| Panel | Appears When |
|-------|-------------|
| **Unit panel** | A unit is selected. Shows ATK/DEF/MOV, weapon loads, CJS modifier, and available actions (⚔ Attack, ⛽ Resupply, ☢ Detonate). |
| **Launch panel** | During Launch phases. Lists Earth reserves (ELR launches), Deep Space reinforcements, and OLR-capable launchers in orbit. |
| **Unit Legend** | Always available — click to expand. Shows icon, full name, and rule notes for every unit type. |

### Actions Bar

**Next Phase →** advances to the next phase. Passive phases chain automatically.

During move mode: a **✕ Cancel** button aborts the current selection without moving the unit.

### Token Shapes

Each unit type has a distinct outer token shape to aid recognition:

| Shape | Units |
|-------|-------|
| Diamond | OWP |
| Pentagon | HK |
| Hexagon | CJS |
| Circle | Mine, OLR |
| Tall narrow rectangle | EWR |
| Very tall thin rectangle | ELR |
| Wide flat rectangle | Missile |
| Wide rectangle (~1.6:1) | Space Station |
| Upward triangle | Nuke, MIRV |
| Octagon | Supply Counter |
| Rounded square | SF, Shuttle, COM |

---

## Save / Load

**Save** (top-right button) serialises the full game state to `localStorage`. **Load Saved Game** on the welcome screen restores it. Only one save slot is available per browser origin.

---

## Architecture

The game is a single HTML file (~4200 lines). The JavaScript is divided into four classes:

```
Engine              — game state, rules enforcement, all phase logic
Renderer            — Canvas 2D drawing (board, units, overlays)
UI                  — DOM interaction, dialogs, force builder, phase flow
SpotlightTutorial   — overlay walkthrough system (17 steps, live engine)
```

Supporting structures: `TUT_STEPS[]` (bottom-bar tutorial content), `PHASES[]` (9-phase sequence), `UTYPES{}` (unit type catalogue), `SCENARIOS{}`, `QUICK_STARTS{}`.

The engine is fully headless-testable — all game logic runs without the DOM. A Node.js test harness (`engine_test2.js` + `harness2.js`) covers 64 unit tests across orbital movement, launches, combat, CJS jamming, mine combat, scoring, win conditions, and supply mechanics.

---

## Known Gaps vs. Original Rulebook

These mechanics from the original rulebook are not yet implemented:

| Section | Mechanic | Status |
|---------|----------|--------|
| §19 | MIRV split — 3-MIRV and 7-MIRV should deploy as independent warheads | Not implemented; fire as a single nuke |
| §23 | Cease-fire win condition — 18-turn cease-fire ends the game | Not tracked |
| §22 | Decoy placement — alternating facedown blank counters during setup | Not implemented |
| §6 | Retreating units entering mined hexes trigger that mine | Not checked |

---

## Credits

Original game design: **Wallace Wang**  
Development: **Steve Jackson**  
Published by: **Steve Jackson Games**, 1992

This digital adaptation is a fan implementation for personal use.
