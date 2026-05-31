# Graph Neural Networks for Approximating Vertex Cover & Matching Problems

## Overview
This project investigates the use of **Graph Neural Networks (GNNs)** to approximate solutions for two classical NP-hard problems:

- Minimum Vertex Cover (MVC)
- Minimum Edge Dominating Set (MEDS)

Traditional approximation algorithms rely on fixed heuristics (e.g., 2-approximation). In contrast, this project explores **data-driven approaches** where neural networks learn structural patterns in graphs to produce high-quality approximations.

---

## Key Idea
Instead of manually designing approximation strategies, we:

- Train GNNs on synthetically generated graph datasets  
- Learn structural patterns across different graph families  
- Use these learned representations to generate near-optimal solutions  

This approach combines ideas from:
- Graph Neural Networks
- Probabilistic methods
- Reinforcement learning

---

## Graph Families
The models are trained and evaluated on diverse graph distributions:

- Barabási–Albert (scale-free networks)
- Bipartite graphs
- D-Regular graphs
- Erdős–Rényi random graphs
- Watts–Strogatz small-world networks

This ensures robustness and generalization across different graph structures.

---

## Models Implemented

### 1. Simple GNN
- Node-level message passing
- Binary classification for node inclusion
- Uses BCE loss with size penalty

### 2. Edge-Based GNN
- Operates on line graph representation
- Captures edge adjacency constraints effectively

### 3. GATv2 + Positional Encoding
- Attention-based model
- Uses Laplacian positional encodings for spatial awareness

### 4. Graph Isomorphism Network (GIN)
- Highly expressive architecture
- Incorporates structural graph features

### 5. S2V + DQN (Reinforcement Learning)
- Sequential decision-making approach
- Learns greedy construction of solutions via Q-learning

---

## Methodology

### Training Strategy
- Train on smaller graphs
- Test on larger unseen graphs
- Evaluate generalization capability

### Evaluation Metrics
Models are compared against the standard **2-approximation baseline** using:

- Percentage of cases where the model:
  - Beats the baseline
  - Matches the baseline
  - Performs worse
- Average approximation ratio

Lower approximation ratio indicates better performance.

---

## Results Summary
- GNN models frequently **match or outperform classical baselines**
- Strong performance observed across multiple graph families
- Models demonstrate:
  - Good generalization
  - Scalability to larger graphs
  - Ability to learn effective heuristics

---

## Tech Stack
- Python
- PyTorch / PyTorch Geometric
- NetworkX
- Reinforcement Learning (DQN)

---

## Authors
- Debrup Chatterjee
- Debanjan Kola
