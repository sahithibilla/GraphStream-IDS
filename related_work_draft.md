# Related Work (Draft)

## Graph-based intrusion detection
Static GNN-based IDS approaches such as E-GraphSAGE, Anomal-E, FN-GNN, and PPT-GNN have shown
that representing network traffic as a graph over hosts, ports, and sessions captures relational
structure that ordinary tabular classifiers miss. However, these methods assume a fixed data
distribution and do not address performance degradation as traffic and attack patterns evolve over
time.

## Continual learning for tabular intrusion detection
Strategic Selection and Forgetting (SSF) [arXiv:2412.16264] introduces drift-aware sample selection
and forgetting for continual IDS: new samples associated with drifted patterns are prioritized for
retention, while outdated samples are dropped once significant drift is detected. SOUL
[arXiv:2412.00911] addresses open-world continual learning for NIDS, aiming to distinguish genuine
zero-day attacks from ordinary distribution shift within known classes. Related replay-based
approaches (e.g., Amalapuram et al., augmented memory replay) similarly mitigate catastrophic
forgetting in sequential IDS training. All of these methods operate on tabular feature
representations rather than graph structures.

## Graph-based continual learning for intrusion detection
EL-GNN combines a graph convolutional architecture with elastic weight consolidation (EWC), a
regularization-based continual-learning mechanism, for task-incremental intrusion detection. This is
the closest existing work to GraphStream-IDS in combining graph representation with continual
learning. However, EL-GNN is evaluated in a closed-world, task-incremental setting: it does not
address zero-day/unknown-attack detection, does not use a replay-based memory mechanism, and does
not incorporate explicit drift detection.

## Graph + temporal modeling for advanced threats
CONTINUUM applies a spatio-temporal GNN to APT (advanced persistent threat) detection, modeling both
temporal and relational dependencies in attack campaigns. This is scoped specifically to APT
detection rather than general intrusion detection, and its treatment of drift detection, selective
replay, and uncertainty-based novelty detection is not established in available summaries.

## Uncertainty-driven and human-in-the-loop zero-day detection
Cognitive NIDS (CNIDS) frames zero-day resilience as a continuous learning process, using continual
pretraining, fine-tuning, and a human-feedback loop that converts low-confidence alerts into
structured learning updates. This shares GraphStream-IDS's interest in uncertainty as a signal for
triggering adaptation, but is not graph-based and depends on human-in-the-loop labeling rather than
an automated selective-replay mechanism.

## Positioning of GraphStream-IDS
No existing method combines all of the following within a single framework: (1) dynamic graph
representation of network entities and communications, (2) explicit, automated drift detection over
feature/embedding distributions, (3) selective (not purely regularization-based) replay memory for
catastrophic-forgetting mitigation, and (4) uncertainty-calibrated unknown-attack detection evaluated
under a chronological, non-i.i.d. zero-day protocol. GraphStream-IDS is positioned as the first
framework to unify these four elements, extending the graph+continual-learning direction opened by
EL-GNN with the drift-awareness of SSF and the open-world zero-day framing of SOUL, on a graph
backbone that none of these tabular methods use.

---
*Note: verify all citation details (author names, venues, exact publication years) against the
original papers before submission — this draft is based on search-derived summaries and needs
direct-source confirmation.*
