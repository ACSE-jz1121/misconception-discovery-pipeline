# Auditable Misconception Discovery

End-to-end pipeline for discovering **misconception-like error patterns** from multiple-choice wrong answers (distractor-level), and producing **auditable, evidence-linked cluster cards** using evidence-constrained LLM summarisation.

This repository supports:
- **Discovery (LLM-free):** hybrid representation + clustering (HDBSCAN) + baselines
- **Auditable abstraction (LLM-assisted):** evidence-constrained summarisation + consistency auditing
- **Evaluation:** stability (bootstrap ARI/NMI), human ratings, downstream diagnostic retrieval

---

## Project Overview

### What is a “distractor-level sample”?
Each sample corresponds to a **(question, wrong option)** pair. We aggregate response logs to compute behavioural signals (e.g., wrong-option selection rate) and combine them with text semantics (stem + correct option + wrong option).

### What does “auditable” mean here?
Each LLM-generated cluster explanation must:
1. Be **constrained to a provided evidence pack** (cluster exemplars)
2. **Cite exemplar IDs** in every evidence claim
3. Pass an **automatic consistency check** that flags unsupported summaries

---

## Pipeline

1. **Preprocess** raw response logs into distractor-level samples  
2. **Hybrid representation**: text embeddings + behavioural features  
3. **Clustering**: HDBSCAN (plus baselines)  
4. **Cluster bundles**: select exemplars as evidence packs  
5. **Evidence-constrained LLM summarisation**: generate cluster cards  
6. **Audit**: consistency checks + low-cohesion flags  
7. **Evaluation**: stability (bootstrap ARI/NMI), human ratings, downstream retrieval  

---

## Repository Structure

