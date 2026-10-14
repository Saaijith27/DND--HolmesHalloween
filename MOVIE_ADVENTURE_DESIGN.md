# Chandramukhi: The Movie Adventure — Narrative & Game Design v1

## Creative direction
A 60-minute, five-player, TV-hosted isometric adventure inspired by the *2005 Tamil film Chandramukhi*. Follow its **dramatic progression**: Senthil and Ganga's return, the purchase of the feared Vettaiyapuram palace, Saravanan's arrival and larger-than-life hero moment, family comedy, strange incidents, psychological investigation, the historical Chandramukhi–Vettaiyan–Gunasekaran backstory, and the climactic ritual.

**Important fidelity:** The movie's mystery is not simply a generic ghost haunting. Saravanan investigates Ganga's behavior and the psychological explanation behind the apparent possession. Preserve the ambiguity and the film's eventual revelation. Don't reveal the twist in the first act.

## Six acts / runtime
1. **Homecoming & hero build-up (0–10 min)** — Cinematic introduction of Senthil and Ganga, family interactions, mansion purchase. Saravanan arrives with a signature hero-intro moment. Introduce five player roles with ability cards. Music cue slots for *Devuda Devuda* / licensed intro material where appropriate; do not assume the entire song is a scene-accurate chronological cue.
2. **Road to Vettaiyapuram (10–18 min)** — Isometric village street and palace gates; Vadivelu/Murugesan-style comedy; first playable dice challenge to enter safely; the household warns about the forbidden wing.
3. **Life inside the mansion (18–30 min)** — Multi-room exploration, anklet sounds, eerie sightings, comedy beats and clues; Ganga becomes increasingly fascinated by the sealed room. Optional music cue slot for *Konja Neram* where appropriate, subject to film-accurate placement and licensing.
4. **Saravanan investigates (30–44 min)** — Evidence board, interviews, forensic/psychological clues, misleading supernatural interpretations, clues from paintings, documents, and observed behavior. Ability checks unlock additional context; failed rolls create setbacks, never block essential story progress.
5. **The tragic past (44–52 min)** — Interactive reconstruction of Chandramukhi, Gunasekaran and Vettaiyan; discover why the story matters to the present. Music cue slot for *Raa Raa* in the dramatic dance-related sequence.
6. **The confrontation (52–60 min)** — Team coordinates a staged ritual/plan, navigates a timed sequence, solves evidence-based challenges and completes a D20 team check. Ending preserves the film's core revelation, with variable epilogues based on player choices.

## Five playable roles
- Dr. Saravanan — Investigation / deduction: +3 Insight; once per act reroll a failed clue check.
- Senthil — Courage / social trust: +3 Resolve; shield a teammate from one setback.
- Ganga — Memory / cultural knowledge: +3 Lore; unique perspective scenes, handled sensitively and without treating mental illness as a monster or combat target.
- Murugesan — Comedy / distraction: +3 Charm; defuse a tense encounter, unlocking an alternate approach.
- Fifth role — **Original supporting character** (e.g. palace caretaker's apprentice) with +3 Perception; do not make Chandramukhi a simultaneous autonomous ghost adventurer, since that spoils the story. Existing five-character roster must be migrated carefully.

## Interactive mechanics
- Isometric world maps: family home, village road, palace courtyard, entrance, corridors, library, forbidden wing, dance hall, ritual chamber.
- Move tile-by-tile via phone; shared TV shows all players and camera follows current encounter.
- D20 roll animation on TV; server-validated or host-authoritative outcomes for fairness.
- Skills, clues, inventory, evidence board, limited character abilities, team checks.
- Triggered encounters, cutscenes and auto-DM Tanglish narration.
- Fog of war and story gates prevent premature access to spoilers.
- Scene transitions use optional video/audio cue assets uploaded by the owner. Use original licensed media only when the user has the rights to use it; otherwise use original royalty-free compositions and inspired-but-not-copied visuals.
- Use the film's distinctive comedy/horror pacing rather than timed multiple-choice rounds.
- Automatic DM can pace scenes, but exploration should be player-driven; allow a soft 60-minute time budget, not a hard cut-off mid-scene.

## Engineering architecture
Keep GitHub Pages as static client. Firebase Anonymous Auth and Realtime Database handle lobby, five players, presence, movements, inventory, encounter phase, dice requests/results and clue discoveries. TV host drives story state. Add Firebase security rules and transaction-based state changes, avoid arbitrary client writes to shared state. Move from SVG to Three.js/WebGL for isometric camera, walls, doors, lighting and animation once core mechanics work. Maintain low-end Android compatibility with quality settings.

## First vertical slice: Prologue -> palace gate
1. TV intro cinematic: Senthil/Ganga homecoming, player joins, hero reveal and optional music cue.
2. TV transitions to a playable village street isometric map.
3. Five players walk toward palace gate and can interact with watchman, gate, and warning plaque.
4. Saravanan rolls Insight to interpret a clue; Murugesan can distract watchman; Senthil can convince family to proceed.
5. Success or failure changes a comedic/horror complication, but all paths eventually open the gate.
6. Record the clue on a shared evidence board; fade into the mansion courtyard.

## Release milestones
- M1: Prologue and village/gate map, phone movement, TV dice animation, Firebase synchronized interactions.
- M2: Mansion rooms, fog of war, inventory and evidence board.
- M3: Investigation and historical flashback.
- M4: Ritual finale, soundtrack cue integration, polish and five-device testing.

## Current state
The separate `isometric.html` prototype on this branch is only a **mechanical test room** and does not yet implement this film-flow campaign. Do not advertise it as the finished movie game.


## Romance arcs — essential to the campaign

Romance is a core narrative pillar, not optional trivia or a detached minigame.

1. **Senthil and Ganga — present-day marriage:** Begin with their affectionate partnership and playful interactions before the mansion. Their bond gives emotional stakes to the escalating mystery. Add a cooperative trust encounter in which Senthil supports Ganga without treating her as an enemy.
2. **Saravanan and Durga — romance and comedy:** Introduce Durga as a recurring NPC with her own dialogue and agency. Between investigative scenes, include teasing exchanges, a lighthearted encounter and a later heartfelt beat. Make their relationship develop over the adventure rather than instantly.
3. **Chandramukhi and Gunasekaran — tragic historical love:** In the historical reconstruction, let players witness their relationship and the jealousy of Vettaiyan. This is the emotional center of the past-life story. Uncover it through clues and a playable flashback, culminating in a dramatic dance sequence.

### Romance-linked interactive scenes
- Prologue: Senthil and Ganga's relationship established through cinematic dialogue and a two-player trust interaction.
- Village / palace: Saravanan and Durga meet and exchange playful dialogue, with optional original music cues.
- Investigation: Senthil can make a Resolve roll to support Ganga; Saravanan and Durga share an important clue-gathering scene.
- Historical flashback: Chandramukhi and Gunasekaran's relationship is revealed in stages. Players explore their meeting place and discover letters or keepsakes.
- Finale: Emotional resolution reflects the love stories and preserves the movie's underlying revelation.

**Music:** Add configurable cues for licensed romantic songs where narratively appropriate; avoid assuming a soundtrack song appears at a specific moment without verifying film scene order. Original substitute music must not copy protected melodies or recordings.

**Design guardrail:** Romance choices should affect dialogue, trust and epilogues, but should not let players arbitrarily overwrite the established identities or remove consent and agency from story characters.
