# Game Concept: Amazon — Hammer and Domino

*Created: 2026-10-11*
*Status: Draft*

---

## Elevator Pitch

> It's a turn-based strategy game where you manage Amazon basin land use on a 2D map, balancing economic development quotas against an ecosystem that fights back with delayed, remote, and irreversible consequences — all driven by a real climate science model running underneath.

---

## Core Identity

| Aspect | Detail |
| ---- | ---- |
| **Genre** | Turn-based ecological strategy / management simulation |
| **Platform** | Web (HTML5) + PC (cross-platform desktop) |
| **Target Audience** | System-thinkers, strategy gamers, climate-curious players, educators and students |
| **Player Count** | Single-player |
| **Session Length** | 30-60 minutes per chapter scenario |
| **Monetization** | None yet (academic/educational context initially) |
| **Estimated Scope** | Medium (3-6 months for demo, 9-12 months for full campaign, solo) |
| **Comparable Titles** | Oxygen Not Included, Frostpunk, Anno series, Fate of the World |

---

## Core Fantasy

You are a regional development coordinator managing the Amazon basin. You have the power to decide what the land becomes — agriculture, logging, protected forest, or restored wilderness. But the Amazon is a coupled climate system with memory, thresholds, and delayed consequences that you cannot see until it's too late. Your fantasy is the illusion of control over a system that is smarter than you — and the hard-won understanding that comes from watching that illusion shatter.

No other game lets you run a real climate experiment, watch a real tipping cascade unfold across real geography, and then try to undo it — only to discover that the path back is harder than the path in.

---

## Unique Hook

Like Civilization, AND ALSO the terrain itself remembers what you did to it and changes its physical rules when you've pushed it too far — because the climate simulation underneath is real science, not game-balanced fiction.

The hook has three layers:
1. **Delayed spatial consequences**: Clearing forest in Pará dries Acre three years later, 2000km away
2. **Hysteresis**: Reforesting to 60% forest cover does NOT restore the rainfall you had at 60% on the way down — the system followed a different path
3. **Progressive physics**: Each campaign chapter adds a real feedback mechanism (moisture recycling → drought stress → fire lock-in), and the player discovers each one by running the same experiment under different rules

---

## Player Experience Analysis (MDA Framework)

### Target Aesthetics (What the player FEELS)

| Aesthetic | Priority | How We Deliver It |
| ---- | ---- | ---- |
| **Sensation** (sensory pleasure) | 5 | Immersive Amazon map, atmospheric audio (rain, fire, river), overlay transitions |
| **Fantasy** (make-believe, role-playing) | 4 | You ARE the coordinator — your stamp on a region is irreversible |
| **Narrative** (drama, story arc) | 3 | Campaign chapters tell the research story; events narrate consequences in human terms |
| **Challenge** (obstacle course, mastery) | 2 | Balancing economic targets against ecological thresholds with imperfect information |
| **Fellowship** (social connection) | N/A | Single-player |
| **Discovery** (exploration, secrets) | 1 | The primary aesthetic — discovering how deforestation cascades, why geography matters, what hysteresis feels like |
| **Expression** (self-expression, creativity) | 6 | Free-play scenarios and sandbox mode let players test their own hypotheses |
| **Submission** (relaxation, comfort zone) | N/A | This game is deliberately uncomfortable |

### Key Dynamics (Emergent player behaviors)

- Players will experiment with clearing patterns to understand why east-origin is more harmful than west-origin
- Players will compare outcomes across chapters (A1 vs A2 vs A3) to isolate the marginal contribution of each feedback
- Players will develop spatial intuition about moisture recycling without being taught the physics explicitly
- Players will try to "game" the economic system and discover that the ecological system doesn't cooperate
- Players will attempt reforestation and discover hysteresis — then try to find the minimum intervention that restores the system

### Core Mechanics (Systems we build)

1. **Land-use zoning** — Paint land-use designations (agriculture, logging, protected, reforestation, fire management) onto geographic regions of the Amazon basin map
2. **Climate simulation** — A simplified 1D box model (derived from a validated 100-box research model) runs underneath the 2D map, computing moisture recycling, evapotranspiration, precipitation, drought stress, and fire dynamics per yearly timestep
3. **Overlay diagnostics** — ONI-inspired overlay system lets players toggle between rainfall, vegetation health, drought stress, fire risk, moisture transport, and economic output views
4. **Economic pressure** — Yearly development targets create graduated consequences: warnings → budget cuts → forced development → removal (with fast-forward aftermath)
5. **Progressive chapter system** — Each chapter enables one additional feedback mechanism (A1 → A2 → A3 → reforestation), with guided sub-scenarios controlling deforestation origin to teach directionality

---

## Player Motivation Profile

### Primary Psychological Needs Served

| Need | How This Game Satisfies It | Strength |
| ---- | ---- | ---- |
| **Autonomy** (freedom, meaningful choice) | WHERE you clear matters as much as HOW MUCH. East vs. west creates genuinely different trajectories. Players choose their own land-use strategy. | Core |
| **Competence** (mastery, skill growth) | Players develop a mental model of moisture recycling, drought cascades, and fire lock-in through play. They feel smarter, not lectured. Chapter comparisons reveal scientific insight. | Core |
| **Relatedness** (connection, belonging) | The Amazon — its biodiversity, its rivers, its Indigenous communities — is the character the player cares about. The forest is alive and responsive, not abstract. | Supporting |

### Player Type Appeal (Bartle Taxonomy)

- [x] **Explorers** (discovery, understanding systems, finding secrets) — Primary. The entire game is about discovering how a complex coupled system behaves. Every chapter reveals a new mechanism. Sandbox mode lets them test hypotheses.
- [x] **Achievers** (goal completion, collection, progression) — Secondary. Meeting development targets while preserving the ecosystem is a genuine optimization challenge. Campaign completion and scenario scores provide achievement structure.
- [ ] **Socializers** (relationships, cooperation, community) — Minimal. Single-player. Community sharing of strategies and discoveries could emerge organically.
- [ ] **Killers/Competitors** (domination, PvP, leaderboards) — Not served.

### Flow State Design

- **Onboarding curve**: Chapter 1 (A1 physics only) is the tutorial. Deforestation and moisture recycling are the simplest feedback. Guided sub-scenarios (east-origin, west-origin, free-play) teach directionality within the first chapter. No text tutorials — the game teaches through comparison.
- **Difficulty scaling**: Each chapter adds one feedback mechanism. Economic targets tighten in later chapters. Climate change forcing (future feature) adds a rising difficulty floor.
- **Feedback clarity**: Overlays show exactly what changed and where. Scenario comparison screens show A1 vs. A2 vs. A3 outcomes side by side. Event notifications narrate threshold crossings in plain language.
- **Recovery from failure**: Economic removal triggers a fast-forward showing 20 years of consequences — failure is educational, not punishing. Players can restart a chapter with new knowledge. The game explicitly says: "Your successor prioritized growth. By 2050, the eastern basin had crossed Threshold B."

---

## Core Loop

### Moment-to-Moment (30 seconds)
The player looks at the 2D Amazon map, selects a region, and paints a land-use designation. They toggle overlays to diagnose the current state — where is rainfall declining? Where is drought stress building? Where are fire-prone edges forming? Each zoning decision is a stamp on the map that cannot be easily undone.

### Short-Term (5-15 minutes — one turn = one year)
1. Review dashboard: economic quota, ecological indicators, events from last year
2. Read warnings: "Drought stress rising in Acre." "Fire risk elevated along Rondônia frontier."
3. Make 2-4 zoning decisions across the map
4. Advance Year: the model runs (~1-2 seconds). Consequences animate across the map — rainfall contours shift, fire icons appear, vegetation changes color
5. Events resolve: threshold crossings, economic reports, community impacts

The "one more turn" hook: every advance reveals delayed consequences of decisions made 3-5 years ago. The present always feels manageable; the future always surprises.

### Session-Level (30-60 minutes — one campaign chapter)
Each chapter is a standalone scenario of ~15-20 turns (years). Chapters have 2-3 guided sub-scenarios that control a single variable (e.g., east-origin vs. west-origin clearing), followed by a free-play run. At the end of each chapter, a comparison screen shows outcomes across sub-scenarios, revealing the scientific insight the chapter teaches.

A session plays 1-2 chapters. Natural stopping point: chapter completion with comparison summary.

### Long-Term Progression
The player's scientific understanding IS the progression. Each chapter adds a feedback mechanism:

| Chapter | Physics | Discovery |
| ---- | ---- | ---- |
| 1: The Hammer | A1 — deforestation + moisture recycling | "Clearing here dried the forest OVER THERE" |
| 2: The Memory | A2 — + drought feedback (PWD, vegetation health) | "The forest remembers. It's still declining even though I stopped." |
| 3: Fire Season | A3 — + repeated fire (ignition, reburn, lock-in) | "Fire is locking in damage that drought alone would have recovered from." |
| 4: The Way Back | + reforestation + hysteresis | "I'm reforesting, but the rainfall isn't coming back at the same rate." |

Chapter 4 unlocks the Science View — the raw 1D transect alongside the 2D map, scenario comparison across all chapters, and the full diagnostic overlay suite.

### Retention Hooks
- **Curiosity**: "What happens if I clear from the west instead?" "What if I protect the middle?" "Can I find a development pattern that doesn't trigger the cascade?" Each chapter raises a new question the player must play to answer.
- **Investment**: The Amazon itself — its regions, its communities, its biodiversity indicators. The player grieves what they lose and fights for what remains.
- **Mastery**: The player develops genuine scientific intuition. By Chapter 4, they understand moisture recycling, drought feedback, fire lock-in, and hysteresis — not as vocabulary, but as felt experience.

---

## Game Pillars

### Pillar 1: Scientific Integrity
The climate system is grounded in validated physics, not hand-tuned game balance.

*Design test*: If gameplay balance and scientific accuracy conflict, we adjust the game design to make the real physics fun — we don't fudge the physics to make the game easier.

### Pillar 2: Discovery Over Instruction
Players discover climate concepts through play, comparison, and failure — never through lecture.

*Design test*: If we're choosing between a tutorial tooltip explaining moisture recycling and letting the player see their eastern clearing dry the west and figure it out, we let them figure it out.

### Pillar 3: Consequence Has Weight
Every decision has delayed, irreversible, spatially remote effects. The system remembers.

*Design test*: If a player action can be easily undone without lasting trace, it doesn't belong in the game's core loop.

### Pillar 4: The Forest Is Alive
The Amazon's biodiversity, rivers, people, and cultures are present and responsive — not abstracted into numbers.

*Design test*: If a region is just a colored tile with stats and nothing else, we haven't done enough. The player should grieve what they lose.

### Pillar 5: No Easy Answers
Economic development and ecological preservation genuinely compete. No trivially optimal strategy exists.

*Design test*: If the player can "win" without ever feeling torn between development and conservation, the balance is broken.

### Anti-Pillars (What This Game Is NOT)

- **NOT a micromanagement game**: No pipe routing, no worker scheduling, no tile-by-tile optimization. We take ONI's diagnostic discovery, not its mechanical complexity.
- **NOT procedurally generated**: The Amazon has real geography, real places, real communities. Randomized maps undermine the scientific and cultural specificity.
- **NOT symmetrically "fair"**: East-origin clearing IS more harmful than west-origin. That asymmetry is the lesson, not a bug.
- **NOT a lecture with game mechanics bolted on**: If a concept requires a text box to understand, we redesign the mechanic.

---

## Inspiration and References

| Reference | What We Take From It | What We Do Differently | Why It Matters |
| ---- | ---- | ---- | ---- |
| **Oxygen Not Included** | Overlay-based diagnosis of emergent physical systems. Simple player actions + coherent hidden physics = emergent problems. | Strategic scope (basin management) instead of micro-engineering. Real physics instead of game-physics. | Validates that system-diagnosis gameplay can sustain hundreds of hours |
| **Frostpunk** | Moral weight of resource management. The dread of irreversible decisions under pressure. | Spatial consequences instead of social ones. Real science instead of fictional scenario. | Validates that strategy games can carry emotional weight through consequence |
| **Civilization** | Turn-based strategy on a geographic map. "One more turn" through decades. | The map fights back based on physics, not AI opponents. The terrain itself changes rules. | Validates that turn-based strategy on a map is an enduring and accessible format |

**Non-game inspirations**:
- The validated Amazon box model (pybamocs) — 100-box transect with moisture recycling, deforestation, drought, and fire
- Research experiments A1, A2, A3, A3b — the mechanism-isolation ladder that becomes the campaign structure
- Levi-Strauss's *Tristes Tropiques* — the anthropological weight of the Amazon; Indigenous knowledge as a real epistemology, not a game resource
- The hysteresis discovery from the research — the asymmetry between deforestation and reforestation paths in rainfall state space

---

## Target Player Profile

| Attribute | Detail |
| ---- | ---- |
| **Age range** | 16-45 |
| **Gaming experience** | Mid-core to hardcore strategy players; also first-time gamers in educational contexts |
| **Time availability** | 30-60 minute sessions; 4-8 sessions for full campaign |
| **Platform preference** | PC (Steam/itch.io) and web browser (classroom/education) |
| **Current games they play** | ONI, Factorio, Frostpunk, Anno, Civilization; students play whatever their professor assigns |
| **What they're looking for** | A strategy game that teaches real science through genuine emergence, not scripted lessons |
| **What would turn them away** | Lecturing, heavy text, simplistic "green = good" morality, inaccurate science |

---

## Technical Considerations

| Consideration | Assessment |
| ---- | ---- |
| **Recommended Engine** | Godot 4 — GDScript is Python-like (matches developer background), free/open-source (MIT), excellent 2D support, HTML5 + desktop export. Decision deferred to `/setup-engine`. |
| **Key Technical Challenges** | (1) Porting the Python box model to game-engine-compatible simulation while maintaining numerical stability at coarser timesteps. (2) Mapping 2D geographic regions to 1D transect positions for physics projection. (3) First game engine project — unknowns in UI, scene management, export. |
| **Art Style** | 2D stylized — illustrated Amazon map with region outlines, river systems, overlay color gradients. Not pixel art, not photorealistic. Warm, organic, alive. |
| **Art Pipeline Complexity** | Low-Medium (stylized 2D map, overlay systems, UI elements; no character animation or 3D assets in MVP) |
| **Audio Needs** | Moderate-Adaptive (ambient rainforest soundscape that degrades with deforestation; fire audio; rain intensity tied to simulation; UI feedback sounds) |
| **Networking** | None |
| **Content Volume** | 4 campaign chapters (15-20 turns each), 3 sub-scenarios per chapter, ~12-16 map regions, 5+ overlay types, sandbox mode |
| **Procedural Systems** | None — geography is fixed (real Amazon); stochastic fire ignition uses the model's existing probabilistic system |

### Hybrid 2D Map / 1D Physics Architecture

The game presents a **2D geographic map** of the Amazon basin divided into ~12-16 named regions (Pará, Mato Grosso, Rondônia, Acre, Amazonas, etc.). Players interact with the map — painting land-use zones, toggling overlays, reading events.

Underneath, a **1D box model** (simplified from the 100-box research model) runs the physics. Each 2D region maps to a position on the east-west transect based on its longitude. When the player deforests a region, it clears boxes at the corresponding transect position. Moisture recycling, drought stress, fire, and vegetation dynamics propagate along the 1D chain. Results are projected back onto the 2D map as overlay contours.

This architecture is scientifically defensible because moisture transport in the Amazon is dominantly zonal (east-to-west, driven by trade winds). The 1D transect captures the primary axis of causation.

---

## Risks and Open Questions

### Design Risks
- Core loop may feel like watching graphs rather than playing a game if the 2D map isn't emotionally engaging
- The "just don't deforest" trivial strategy must be blocked by economic pressure that feels real, not arbitrary
- Progressive physics (each chapter = different rules) may confuse players who expect continuity

### Technical Risks
- Porting the Python box model to GDScript (or embedding Python) while maintaining numerical stability at daily timesteps instead of hourly
- 2D→1D region projection: mapping irregular geographic polygons to transect positions without losing scientific meaning
- Fire stochasticity: deterministic replay for scenario comparison vs. stochastic fire for realism
- Web export performance: running the simulation in browser JavaScript/WebAssembly within acceptable frame times

### Market Risks
- "Educational game" label can suppress interest from strategy gamers who would enjoy it
- Climate fatigue: audience may assume it's preachy or didactic
- Niche audience size may limit commercial viability (but academic/grant funding is an alternative path)

### Scope Risks
- The full vision (biodiversity, Indigenous knowledge, field view, climate change forcing) could expand indefinitely
- Art direction for an immersive Amazon map requires more visual investment than placeholder tiles
- Campaign balancing (economic targets vs. ecological thresholds) across 4 chapters × 3 sub-scenarios is labor-intensive

### Open Questions
- What is the right number of 2D regions? 12 (fast, simple) vs. 16-20 (more geographic resolution)? — answer with prototype playtesting
- Should fire be deterministic (reproducible scenarios) or stochastic (realistic but harder to compare)? — answer by testing both in prototype
- Can the model run at daily timestep without CFL instability? — answer with numerical experiments on the existing Python model before porting
- Should the Science View show the raw 1D transect, or a stylized version? — answer based on target audience feedback
- How to represent Indigenous knowledge ethically — not as a "resource" the player extracts, but as a genuine epistemology? — requires cultural consultation

---

## MVP Definition

**Core hypothesis**: Players will find the land-use zoning + delayed consequence loop engaging for 30+ minute sessions, and will develop intuitive understanding of moisture recycling through play rather than instruction.

**Required for MVP**:
1. 2D stylized Amazon map with ~12 clickable/paintable regions
2. 1D physics model ported (A1 — deforestation + moisture recycling only, coarsened to daily timestep)
3. 3 land-use types: Agriculture (clear), Protected (preserve), Halt (stop clearing)
4. 2 overlays: Rainfall, Vegetation health
5. Economic pressure: simple yearly development target with warning on miss
6. Advance Year button → model runs → map updates with animated overlay transitions
7. One guided sub-scenario (east-origin) + one free-play run
8. Win/lose: survive 15 years meeting targets without crashing rainfall below threshold in too many regions

**Explicitly NOT in MVP** (defer to later):
- Art assets beyond placeholder colors and shapes
- Audio / music
- Fire or drought feedback mechanics (those are Chapters 2-3)
- Reforestation or intervention tools
- Multiple campaign chapters
- Science View / scenario comparison
- Indigenous/cultural layer
- Biodiversity indicators
- Climate change forcing
- Narrative events or field notes

### Scope Tiers

| Tier | Content | Features | Timeline |
| ---- | ---- | ---- | ---- |
| **MVP** | 12 regions, A1 physics, 1 sub-scenario | Core loop: zone + advance + overlay | 6-8 weeks |
| **Demo** | Chapter 1 complete (3 sub-scenarios), basic art | + event text, east/west/free comparison | +4-6 weeks |
| **Campaign** | Chapters 1-4, all physics (A1-A3 + reforestation) | + full overlay suite, Science View, scenario comparison | +3-6 months |
| **Full Vision** | All chapters + sandbox + climate change | + art direction, audio, biodiversity, Indigenous knowledge layer | +6-12 months |

---

## Next Steps

- [ ] Run `/setup-engine` to configure Godot 4 and populate version-aware reference docs
- [ ] Run `/art-bible` to establish the visual identity before writing system GDDs
- [ ] Use `/design-review design/gdd/game-concept.md` to validate concept completeness
- [ ] Decompose the concept into systems with `/map-systems` — climate sim, economy, overlays, campaign progression, map projection
- [ ] Author per-system GDDs with `/design-system` for each system identified above
- [ ] Plan technical architecture with `/create-architecture` — especially the 2D→1D projection and model port strategy
- [ ] Record key architectural decisions with `/architecture-decision` — model port approach, timestep coarsening, fire determinism
- [ ] Run `/architecture-review` — bootstrap TR registry and Requirements Traceability Matrix
- [ ] Validate readiness with `/gate-check` before committing to production
- [ ] **Alternatively**: Run `/prototype` after `/setup-engine` to validate the core loop is fun before writing full GDDs (recommended given unproven mechanic)
