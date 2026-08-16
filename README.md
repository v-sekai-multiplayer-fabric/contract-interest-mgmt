# contract-interest-mgmt

Authority-interest + solve-order hexagon: who-sees-whom and solve sequencing.

> Split out of the [`lean-predictive-bvh`](https://github.com/v-sekai-multiplayer-fabric/lean-predictive-bvh) monorepo (now archived). Each hexagon cluster is its own repo following the `core/ports/adapters` convention; cross-cluster wiring is via Lake `require ... from git`.

## Dependencies

- [`entities-lean-shared`](https://github.com/v-sekai-multiplayer-fabric/entities-lean-shared) — common primitive types
- [`entities-lean-rebac`](https://github.com/v-sekai-multiplayer-fabric/entities-lean-rebac) — authority decisions
- [`interactor-spatial-oracle`](https://github.com/v-sekai-multiplayer-fabric/interactor-spatial-oracle) — reachability/mapping references (also the transitive Mathlib source)
- [`contract-protocol`](https://github.com/v-sekai-multiplayer-fabric/contract-protocol) — interest queries source

## Build

```sh
lake build         # production gate: typecheck the  cluster
lake build Research  # research-tier (non-gating; may fail)
```

## Hexagon layout

- `core/` — dependency-free domain logic + proofs
- `ports/` — narrow driving (source) / driven (sink) contracts
- `adapters/` — concrete I/O at the edges
