# Auditable Misconception Discovery

Auditable discovery of student misconception patterns from multiple-choice wrong answers using hybrid clustering and evidence-constrained LLM summarisation.

## Overview

This project discovers misconception-like error patterns from MCQ response data (Eedi / NeurIPS 2020 Education Challenge format) and produces **auditable cluster cards**:
- cluster name & definition
- evidence bullets citing exemplar IDs
- diagnostic question & remediation hint
- automatic consistency checks (audit report)

## Pipeline

1. **Preprocess** raw response logs into distractor-level samples
2. **Hybrid representation**: text embeddings + behavioural features
3. **Clustering**: HDBSCAN (plus baselines)
4. **Cluster bundles**: select exemplars as evidence packs
5. **Evidence-constrained LLM summarisation**: generate cluster cards
6. **Audit**: consistency checks + low-cohesion flags
7. **Evaluation**: stability (bootstrap ARI/NMI), human ratings, downstream retrieval

## Repository Structure

