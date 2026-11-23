# Avalanche vs Devils (28 Oct 2026) — Seating Nodes & State Overlays

**Ball Arena · Temporal Velocity Mapping · Using only existing Oroboro / Oroboro Relay components**

Registered observer nodes (exact seats from two ticket orders):

| Seat | Level | Arena notes (hockey) | Temporal velocity | Role |
|------|-------|-----------------------|-------------------|------|
| Section 140, Row 12, Seat 4 | Lower (100) | East end, attack-twice zone (Avs shoot toward this end in 1st & 3rd) | Near-zero (fixed) | Close viewpoint; high influence on near-ice slime-chunk mesh |
| Section 342, Row 6, Seat 7 | Upper (300) | Upper balcony, near center / north side | Near-zero (fixed) | Elevated overview; broader mesh coverage, higher residual on fine skeletal detail |

## Node classes registered in Nexus

1. Player skeletal nodes (joint position + velocity inside slime-chunk cells)
2. Slime-chunk mesh nodes (16×16 spatial partitions, intensity, occupancy, deformation)
3. Audio / song nodes (tempo, energy proxy, active real-clock window)
4. Seat / observer nodes (above)

## Temporal velocity (derived property)

From existing pieces only: previous state → current state → state delta → rate/direction of change → relational influence on mesh → delta reconciliation.

Not a new subsystem. Every node carries position, previous/current state, delta, temporal velocity, and influence on neighboring cells.

## State-specific overlays

- **Position overlay** — skeletal wireframes + pinned seat nodes on the mesh.
- **Temporal-velocity overlay** — intensity by rate of state change (skeletal velocity, chunk intensity delta, song-tempo alignment).
- **Audio-alignment overlay** — active song tempo projected onto chunks in each seat’s view cone (Vendetta 120 BPM strongest early-third peak; Heart of Courage 68/135 sustained second-period field; etc.).
- **Observer-influence / neuro-proxy overlay** — stillness intervals at either seat raise neuro-proxy weight on cells in that seat’s view cone (same pattern as Epic Universe layer set).
- **Reconciliation residual overlay** — residual after delta reconciliation. Section 140 lower residual on near-ice skeletal detail; Section 342 higher residual on fine joints, lower residual on whole-rink intensity.

## Recombined observable (after state reduction + delta reconciliation)

Early third-period intensity peak (Vendetta window + elevated skeletal velocity around Kadri/Kelly goals) is strongest inside Section 140’s closer attack-twice view cone and appears as a broader, lower-amplitude peak from Section 342. Both seat nodes remain near-zero temporal velocity; influence is purely relational.

All processing stays inside Nexus (register / archive / telemeter), state reduction, mesh consensus, and delta reconciliation. No external frameworks.

---

*Synthetic / derived values used where full game video is unavailable. Ready for What If experiments.*
