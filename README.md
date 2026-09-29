# Adaptive Society Network Lab

`society-network-lab.html` is a single-file simulator of a society as an adaptive, weighted, directed network. It has no dependencies and needs no server: open the file in a browser.

## What it models

- **Formation.** A Watts–Strogatz base, extended by preferential and fitness attachment, spatial gravity, homophily, triadic closure and a structural-hole bonus. Each link attempt runs a roulette over 8 candidates.
- **Flow.** Resources move down pressure gradients: `F = k·w·max(0, P_i − P_j)/(1+ν)`, capped by edge capacity. Congestion is `F/C`. A Reynolds-like number, `Re = congestion·ln(1+k)/ν`, marks turbulent regions.
- **Economy.** Each node has a skill vector matched against its cluster's demand. Application volume and signal quality set hiring. Receptivity saturates as volume rises, so mass applications crowd each other out. Automation raises the hiring bar.
- **Adaptation.** Edges strengthen with flow and decay without it. Trust tracks exchange success. Nodes become stressed, go dormant or get pruned. They migrate on a utility difference, retrain their skills, and their fitness drifts. Innovation spreads by reaction–diffusion.
- **Instrumentation.** About 60 live metrics, including degree tail (Hill), clustering, modularity, rich-club ratio, Gini, sampled betweenness, eigenvector centrality, percolation, random-vs-targeted resilience, and flow AR(1)/variance as early-warning signals. Also included:
  - rolling z-score anomaly detection
  - a regime classifier
  - pattern detectors for rich clubs, echo chambers, broker capture, spam collapse, monopoly, poverty traps, innovation fronts, cascades and critical slowing down
  - a diagnostics panel that checks theoretical expectations

## Using it

- **Presets** rebuild the network. **Shocks** hit the running system, and recovery is logged 60 and 200 ticks later.
- Click nodes or edges to inspect them. You can inject resources, freeze a node, force a migration, add or cut edges, or trace shortest and max-flow paths.
- **Research** runs 1-D or 2-D parameter sweeps headless, with replicate seeds, and exports CSV or JSON. **Diagnostics → Run controlled tests** runs paired A/B experiments.
- **Export** gives you the graph (JSON), metric time series (CSV), the event log, a full save/load of simulation state, a shareable parameter link and a PNG.
- The simulation is deterministic: the same seed, parameters and interventions reproduce the same run. The Model & help dialog lists every equation.

Keyboard: `Space` play/pause, `→` step, `R` reset, `F` fit view, `[` `]` speed, `H` help.
