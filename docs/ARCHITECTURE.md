# Architecture Notes (Early)

## Core Principles

1. **Server-authoritative** – All meaningful simulation state lives on the server.
2. **Data-driven** – Governments, laws, technologies, unit types, resources, etc. defined in data (JSON / custom resources) rather than hard-coded logic.
3. **Layered simulation** – Fast tactical layers (combat, logistics) run at higher tick rates; slow strategic layers (demographics, climate, research) run slower.
4. **LOD everything** – Visual and simulation detail scales with distance and player focus.
5. **300-player ceiling** – Designed around this limit so we can afford deeper systems.

## Suggested High-Level Structure (Godot)

```
server/
  simulation/          # Core world tick, systems
  networking/          # Authoritative multiplayer
  persistence/         # Save / load world state

client/
  map/                 # High-altitude 3D world + LOD + streaming
  ui/                  # Nation management, diplomacy, intel, etc.
  prediction/          # Local prediction where safe

shared/
  data/                # Definitions (tech trees, unit types, laws…)
  protocols/           # Message definitions
```

## Map & Rendering Targets

- Primary view: high-altitude orbital / sky-down 3D
- Aggressive LODs + chunk streaming for mobile performance
- Night lights, borders, resource overlays, weather, unit icons as separate layers
- Possible use of MultiMeshInstance3D / GPU particles for large-scale elements

## Networking Direction

- Custom dedicated server (Godot or separate process)
- Reliable ordered channels for state, unreliable for frequent position updates where needed
- Interest management so clients only receive relevant regional data

## Next Implementation Steps

1. Basic Godot 4 project with high-altitude camera + simple procedural / heightmap terrain
2. Minimal multiplayer lobby + server authority skeleton
3. Data-driven nation / government prototype
4. Resource & simple economy tick
5. Expand outward from there
