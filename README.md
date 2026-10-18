# Aurora 4X — Rust Port (Showcase)

## Credits

**Aurora 4X is created by Steve Walmsley.** All of the game's design, rules, data and artwork are his work, and all credit for Aurora belongs to him.

- This is an **unofficial, non-commercial fan project**. It is **not affiliated with or endorsed by Steve Walmsley**.
- **No source code or downloads are offered here.** This page is a showcase only.
- **To play Aurora, get the official game** and join its community at the [official Aurora 4X forums](https://aurora4x.com/).

---

A fan-made port of **Aurora 4X** to Rust, with a modern dark interface, built so the game runs natively on Linux.

## What is Aurora 4X?

Aurora 4X is a famously deep space-empire simulation created by Steve Walmsley. You guide a civilisation from its home system to the stars: designing every ship component by component, managing colonies, mining and industry, researching technology, surveying and exploring new systems, and fighting wars with beam weapons, missiles and ground forces. It has a dedicated community and is free to play on Windows.

## What is this project?

This project recreates Aurora (C# version 2.7.1) as a native Rust application, so it plays on Linux without Wine. The goal is a game that **plays like Aurora**, not a byte-for-byte copy: the game's rules and formulas are reproduced, while the code is written in idiomatic Rust.

The interface keeps Aurora's familiar layout — the icon toolbar, the time-increment buttons, the tactical map and its display options, and every management window — with a modern dark finish, a starfield behind the map, and windows that can be moved onto other monitors.

## Highlights

- **Full simulation:** turn loop with sub-pulses and production cycles; system generation including the real-star catalogue; colonies, mining, industry, shipbuilding, refits and repairs; research with every component designer, including missiles and turrets; commanders, academies, promotions and medals; ground forces, invasions, boarding and capture; fleet movement and orders, logistics, maintenance and civilian shipping; sensors, beam and missile combat with point defence, damage control, wrecks and lifepods; diplomacy and intelligence.
- **Living galaxy:** computer-controlled empires that research, design ships, build, expand and fight, plus the spoiler races (Precursors, Star Swarm, raiders, Invaders, Rakhas and Ancient constructs).
- **The complete interface:** the start screen and new-game setup with every game option, race creation with portraits and flags, Economics, Class Design, research, Missile and Turret Design, Naval Organization, Ground Forces, Commanders, Events, Intelligence, Galactic Map, System View and more.
- **Tactical map:** accurate elliptical orbits, comet tails, all display options, sensor and weapon range circles, and a distance ruler (Shift + drag).
- **Responsive:** time advances in the background so the interface never freezes; a 20-year game with three AI empires runs at roughly 10 seconds per game year.

## Tech stack

| Area | Technology |
|---|---|
| Language | Rust (2024 edition), four-crate Cargo workspace |
| User interface | egui / eframe (OpenGL via glow), egui_extras tables |
| Maps | Custom drawing with egui's painter |
| Game data | rusqlite, reading the original game's database |
| Saves | serde + JSON, gzip-compressed |
| Randomness | rand + rand_chacha, one seeded generator per game (games are reproducible from a seed) |
| Dates | chrono |
| Images | image (portraits, flags, ship icons) |

## Screenshots

Captured at 4K (3840×2160) from a game played forward through several stages.

### New game setup

**Start screen**
![Start screen](setup/01-start-screen.png)

**Game Information: new game options**
![Game Information](setup/02-game-information-new-game.png)

**Choosing a race portrait**
![Choose race portrait](setup/03-choose-race-portrait.png)

**Create New Race with portrait and flag**
![Create New Race](setup/04-create-new-race-portrait-flag.png)

### Early game

**Tactical map: the Sol system**
![Sol system](early/01-tactical-sol-system.png)

**Earth's weapon ranges**
![Weapon ranges](early/02-tactical-earth-weapon-ranges.png)

**Sensor and detection ranges**
![Sensor ranges](early/03-tactical-sensor-and-detection-ranges.png)

**Economics: Earth colony summary**
![Colony summary](early/04-economics-earth-colony-summary.png)

**Economics: active research**
![Active research](early/05-economics-active-research.png)

**Economics: shipyards**
![Shipyards](early/06-economics-shipyards.png)

**Naval Organization: battle fleet**
![Battle fleet](early/07-naval-organization-battle-fleet.png)

**Class Design: heavy cruiser**
![Heavy cruiser](early/08-class-design-heavy-cruiser.png)

**Galactic map: first jump points**
![Galactic map](early/09-galactic-map-first-jump-points.png)

### Mid game

**Battle at Barnard's Star: salvos and contacts**
![Battle salvos](mid/01-battle-barnards-star-salvos-and-contacts.png)

**Battle at Barnard's Star: event log overlay**
![Battle event log](mid/02-battle-barnards-star-event-log-overlay.png)

**Galactic map: 33 systems**
![Galactic map](mid/03-galactic-map-33-systems.png)

**Intelligence on a hostile class**
![Intelligence](mid/04-intelligence-hostile-fenethdra-class.png)

**Naval Organization: plotted moves**
![Plotted moves](mid/05-naval-organization-plotted-moves.png)

**Economics: industry production queue**
![Production queue](mid/06-economics-industry-production-queue.png)

**Ground Forces: order of battle**
![Order of battle](mid/07-ground-forces-order-of-battle.png)

**Commanders: ship captain record**
![Commanders](mid/08-commanders-ship-captain-record.png)

**Events log**
![Events](mid/09-events-log.png)

**Sol-wide mineral concentrations**
![Mineral concentrations](mid/10-tactical-sol-wide-mineral-concentrations.png)

### Late game

**Inner Sol defences**
![Inner Sol defences](late/01-tactical-inner-sol-defences.png)

**Earth body info**
![Earth body info](late/02-tactical-earth-body-info.png)

**Galactic map: warships and alien systems**
![Galactic map](late/03-galactic-map-warships-and-alien-systems.png)

**Economics: Earth at two billion people**
![Earth economics](late/04-economics-earth-two-billion.png)

**Economics: wealth and trade goods**
![Wealth](late/05-economics-wealth-and-trade-goods.png)

**Race Comparison: all empires**
![Race Comparison](late/06-race-comparison-all-empires-spacemaster.png)

**Race Information**
![Race Information](late/07-race-information.png)

**Economics: research projects and queues**
![Research](late/08-economics-research-projects-and-queues.png)

**Class Design: strike cruiser**
![Strike cruiser](late/09-class-design-strike-cruiser.png)

**Component designer: active sensor**
![Component designer](late/10-component-designer-active-sensor.png)

**Missile Design**
![Missile Design](late/11-missile-design.png)

**System View: Sol bodies**
![System View](late/12-system-view-sol-bodies.png)

**Wolf 359 fuel harvesters**
![Fuel harvesters](late/13-tactical-wolf-359-fuel-harvesters.png)

## Status

Most of the game is in place and playable. Still to come: supernovae, colony independence, passenger liners, some standing orders, a few Space Master tools, keyboard shortcuts and saved window positions.

## How it was built

This port was built as a personal project with **Claude Code**, working in short sessions over a few days, with the game play-tested side by side against the original throughout.

---

*Aurora 4X © Steve Walmsley. Please support the official game at the [official Aurora 4X forums](https://aurora4x.com/).*
