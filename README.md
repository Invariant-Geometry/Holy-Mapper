Transporter — Holy Mapper
What it is: A graph-based algorithm for analyzing how local feature representations relate to each other through transport — not just what shape the data has.
Core thesis: Feature identity is determined by transport, not by index. A “direction” in one local feature space may not mean the same thing in another. Transporter measures whether and how local meaning drifts, twists, or fails to return to itself.
The gap it fills: Classical TDA (Mapper, persistent homology) tells you about the coarse topology of a point cloud. It doesn’t tell you how local structure behaves as you move through it — whether features stay consistent across layers, contexts, or loops. Transporter fills that gap.

Six-stage pipeline:
	1.	Build a neighborhood graph or cell complex
	2.	Attach a local feature space (chart) to each node
	3.	Estimate a transport map on each edge
	4.	Compute path transport, loop holonomy, and cycle consistency
	5.	Assemble connection-Laplacian operators
	6.	Report invariants: holonomy magnitude, frame instability, synchronization residuals, flatness

Key outputs: loop_holonomy, cycle_defect, transport_consistency, frame_instability, synchronization_report
Primary targets: Mechanistic interpretability, layerwise representation analysis, transformer/LLM feature tracking, sheaf-based geometric ML
Mapper vs. Transporter in one line:
Mapper gives a combinatorial coordinatization of point clouds. Transporter gives a combinatorial transport geometry of local meaning.
Status: Early-stage — currently at kernel design, framing, and holonomy-first benchmarks.​​​​​​​​​​​​​​​​
