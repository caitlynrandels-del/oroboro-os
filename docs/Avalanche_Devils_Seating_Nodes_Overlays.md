# Avalanche vs Devils (28 Oct 2026) — Seating Nodes & State Overlays

**Ball Arena · Temporal Velocity Mapping · Using only existing Oroboro / Oroboro Relay components**

Registered observer nodes (exact seats from two ticket orders):

| Seat | Level | Arena notes (hockey) | Temporal velocity | Role |
|------|-------|-----------------------|-------------------|------|
| Section 140, Row 12, Seat 4 | Lower (100) | East end, attack-twice zone (Avs shoot toward this end in 1st & 3rd) | Near-zero (fixed) | Close viewpoint; high influence on near-ice slime-chunk mesh |
| Section 342, Row 6, Seat 7 | Upper (300) | Upper balcony, near center / north side | Near-zero (fixed) | Elevated overview; broader mesh coverage, higher residual on fine skeletal detail |

## Additional toggleable node

**Epcot Ball (Spaceship Earth)** — positioned behind the net at the attack-twice end (east end).  
- Toggleable on/off.  
- Originally used as a tool to demonstrate polygons / geometric mesh.  
- Fixed spatial landmark node (near-zero temporal velocity).  
- Visible primarily from Section 140’s closer view cone.  
- Remains locked as a stable reference while skeletal players and intensity layers move in front of it.

## Node classes registered in Nexus

1. Player skeletal nodes (joint position + velocity inside slime-chunk cells)
2. Slime-chunk mesh nodes (16×16 spatial partitions, intensity, occupancy, deformation)
3. Audio / song nodes (tempo, energy proxy, active real-clock window)
4. Seat / observer nodes (above)
5. Toggleable landmark nodes (Epcot ball / polygon demonstration)

## Temporal velocity (derived property)

From existing pieces only: previous state → current state → state delta → rate/direction of change → relational influence on mesh → delta reconciliation.

Not a new subsystem. Every node carries position, previous/current state, delta, temporal velocity, and influence on neighboring cells. Toggleable nodes can be enabled or disabled without breaking the mesh.

## State-specific overlays

- **Position overlay** — skeletal wireframes + pinned seat nodes + optional Epcot ball behind the net.
- **Temporal-velocity overlay** — intensity by rate of state change (skeletal velocity, chunk intensity delta, song-tempo alignment).
- **Audio-alignment overlay** — active song tempo projected onto chunks in each seat’s view cone.
- **Observer-influence / neuro-proxy overlay** — stillness intervals at either seat raise neuro-proxy weight on cells in that seat’s view cone.
- **Reconciliation residual overlay** — residual after delta reconciliation.
- **Polygon demonstration overlay** — toggles the Epcot ball to show geometric mesh / polygon structure behind the net.

## Recombined observable (after state reduction + delta reconciliation)

Early third-period intensity peak is strongest inside Section 140’s closer attack-twice view cone (with or without the Epcot ball visible behind the net) and appears as a broader, lower-amplitude peak from Section 342. Both seat nodes and the Epcot ball remain near-zero temporal velocity; influence is purely relational. The ball can be toggled off without changing the underlying skeletal or intensity results.

All processing stays inside Nexus (register / archive / telemeter), state reduction, mesh consensus, and delta reconciliation. No external frameworks.

---

*Synthetic / derived values used where full game video is unavailable. Ready for What If experiments.*
