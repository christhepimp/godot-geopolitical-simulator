# Project Vision – Living Civilization Simulator

## Design Philosophy

This is not a traditional strategy game with abstracted systems.

It is an attempt to run a continuous, multiplayer civilization where:

- Politics, economics, military, science, culture, crime, media, and environment all exist simultaneously
- Player and NPC decisions create permanent, cascading consequences
- The world never resets or reaches a “win” state
- History is generated, not scripted

The goal is for the game to feel less like a game and more like a persistent virtual world that happens to be playable.

## Scale Constraints (Critical)

- **Max players**: 300 concurrent (hard design limit)
- This allows much deeper simulation per player than mass-market MMOs
- Server authority is mandatory for all meaningful state
- Client is primarily a high-fidelity 3D map + UI + local prediction where safe

## Primary View

High-altitude / orbital 3D camera looking down at the world.

Players spend most of their time at this scale, zooming in for cities, units, or negotiations, then zooming back out to see the global picture.

## Time Model

Default ratio: **1 real day = 1 in-game week**

Configurable per server. This balance is intentional so that long-term policies, infrastructure, and demographic shifts are actually visible within a human lifespan of play.

## NPC Philosophy

NPCs are not just background.

Key NPCs (leaders, generals, CEOs, journalists, crime bosses, scientists, religious figures) maintain memory of interactions, form goals, and can act independently. Aggregated population simulation handles the millions of ordinary citizens.

## Success Metric

If, after a year of continuous server uptime, players are still arguing about:
- who owns a particular island
- whether a currency crash was caused by a real policy or market manipulation
- whether a war was justified or manufactured by media
- whether a new ideology is rising

…then the simulation is working.
