# Transporter - Holy Mapper

**Transporter** is a holonomy-first algorithm for analyzing local representation systems through transport geometry.

> **Feature identity is determined by transport, not by index.**

Where [Mapper](https://en.wikipedia.org/wiki/Mapper_algorithm) gave a combinatorial coordinatization of high-dimensional point clouds, Transporter gives a combinatorial **transport geometry** of local representation systems — local feature spaces, transport maps between them, loop consistency, holonomy, synchronization, and transport-aware operators.

-----

## The problem

Classical TDA is built for:

- too many points, too much dimension
- unclear coarse shape
- need for a multiscale topological summary

Modern ML systems create a different problem:

- local feature frames are only locally meaningful
- neighboring regions may be comparable only through transport
- the same “direction” may not mean the same thing globally
- loops through context, depth, or neighborhood space may induce nontrivial return maps
- global synchronization may fail even when local structure is coherent

Persistent homology can detect loops. It does **not** tell you how local structure twists, aligns, or fails to return to itself around those loops. Transporter is built for that gap.

-----

## What Transporter does

Transporter takes data organized into a graph or cell-complex neighborhood structure and builds a transport-aware summary with:

- **local feature spaces** attached to nodes or cells
- **transport maps** attached to edges or incidences
- **path transport** and **loop holonomy**
- **cycle-consistency** and **synchronization** diagnostics
- **connection-Laplacian** style operators
- optional lift to **cellular sheaf** structure

Instead of asking only: *what topological features persist across scale?*

Transporter asks: *how does local semantic identity behave under transport, and can local structure be made globally coherent?*

-----

## Algorithm

Transporter proceeds in six stages.

**1. Build a neighborhood structure** — construct a graph or cell complex from input-space, latent-space, or behavior-space neighborhoods, layer/context overlap, or task-specific adjacency.

**2. Attach local feature spaces** — for each node or cell, define a local chart via local PCA, sparse directions, learned local frames, or subspace estimation.

**3. Estimate transports** — for each edge or incidence, infer a transport map via Procrustes alignment, whitened alignment, orthogonal projection, or learned local transport operators.

**4. Compute transport summaries** — path transport, loop holonomy, cycle consistency, inverse consistency, synchronization residuals.

**5. Build transport-aware operators** — connection-Laplacian blocks, section smoothness objectives, optional sheaf Laplacians.

**6. Report invariants and diagnostics** — loop defects, conjugacy-stable summaries, flatness indicators, frustration proxies, neighborhood distortion, alignment quality.

-----

## Outputs

```
loop_holonomy
cycle_defect
transport_consistency
synchronization_report
connection_laplacian
flatness_report
frame_instability
neighborhood_distortion
```

-----

## Use cases

**Mechanistic interpretability** — local concept charts for transformers, cross-layer feature comparison, context-dependent feature tracking, basis instability diagnosis.

**Representation learning** — transport-aware sparse autoencoders, holonomic regularization, flat-versus-curved representation regimes, local-to-global coherence benchmarks.

**TDA / geometric ML** — discrete vector bundles on graphs, sheaf-based local-data analysis, synchronization and frustration analysis, transport-aware multiscale summaries.

**Scientific and engineering systems** — deterministic transport kernels, loop-level diagnostics, block-operator assembly, bounded-memory and auditable implementations.

-----

## Mapper vs. Transporter

|              |Mapper                                |Transporter                                             |
|--------------|--------------------------------------|--------------------------------------------------------|
|**Summarizes**|Point-cloud shape                     |Local representation transport geometry                 |
|**Built for** |High-dimensional static clouds        |Local representation systems                            |
|**Focuses on**|Coarse topology                       |Coherence, transport, path dependence                   |
|**Detects**   |Components, flares, loops             |Transport consistency, holonomy, synchronization failure|
|**Output**    |Combinatorial coordinatization of data|Combinatorial transport geometry of local meaning       |

-----

## Design principles

- **Transport first** — do not assume one global basis
- **Invariant first** — prefer gauge-robust outputs over raw coordinate dumps
- **Local-to-global** — model coherence through local state spaces plus compatibility maps
- **Deterministic core** — keep the semantic kernel auditable and implementation-stable
- **Sheaf-ready** — do not trap the design at graph-only scalar abstractions

-----

## Scope

**In scope:** transport-aware graph construction, local frame attachment, transport estimation, path and loop computations, synchronization and consistency, connection-Laplacian assembly, optional sheaf-ready interfaces, benchmarks and diagnostics.

**Out of scope:** generic graph-library replacement, general-purpose PH/barcode engine, heavyweight GUI-first tooling, monolithic research-notebook code.

-----

## Status

Early-stage algorithm and research repo. Current emphasis is on kernel semantics, transport-aware data model, holonomy-first benchmarks, and project definition.

-----

## One-line summary

**Transporter is to holonomy-first representation analysis what Mapper was to point-cloud topology: a combinatorial summary built from local feature spaces, transport relations, and loop consistency.**
