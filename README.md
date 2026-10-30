# Semantic Entropy Policy Engine

A retrieval-based question-answering prototype exploring how semantic disagreement and evidence quality can inform uncertainty-aware answering and abstention.

## Overview

The Semantic Entropy Policy Engine investigates how a question-answering system can recognise when its retrieved evidence is insufficient or its candidate answers are inconsistent.

The prototype uses semantic comparison and an entropy-inspired disagreement measure to inform three possible actions:

- **ANSWER:** Respond when the available evidence meets configured criteria.
- **RETRIEVE_MORE:** Seek additional supporting evidence.
- **ABSTAIN:** Avoid answering when confidence in the available evidence is insufficient.

## Technical Approach

The pipeline explores:

1. **Semantic Retrieval:** Dense vector retrieval combined with keyword-based ranking.
2. **Reciprocal Rank Fusion:** Combining retrieval rankings.
3. **Natural Language Inference:** Using DeBERTa to compare candidate answers through bidirectional entailment.
4. **Semantic Clustering:** Grouping semantically consistent answers using Union-Find.
5. **Uncertainty Estimation:** Calculating an entropy-inspired measure of disagreement.
6. **Decision Routing:** Using configured thresholds to select ANSWER, RETRIEVE_MORE, or ABSTAIN.

## Technology Stack

- Python
- PyTorch
- DeBERTa
- Sentence Transformers
- ChromaDB
- FastAPI
- SQLite
- Next.js
- Tailwind CSS

## Important Implementation Notes

This is an experimental prototype, not a validated measure of true model uncertainty.

The current implementation uses evidence-based templates for candidate answer generation rather than independent language-model samples. Semantic agreement therefore does not independently establish factual correctness.

The entropy-inspired score and decision thresholds should be interpreted within the limitations of the current implementation.

## Research Motivation

The project explores a practical question in AI reliability:

**How can a question-answering system recognise when it should answer, retrieve more information, or abstain rather than produce an unsupported response?**

## Project Status

Experimental prototype — under development.
