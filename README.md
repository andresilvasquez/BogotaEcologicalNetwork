# Ecological Interaction Network of Bogotá

## Overview
This repository contains the analysis of the biotic interaction network of Bogotá, built from publicly available data from the Jardín Botánico de Bogotá. The network integrates interactions across multiple kingdoms (plants, animals, fungi, bacteria, protozoa), including mutualistic and parasitic relationships. The project was developed as part of the *Introduction to Sociophysics* course and explores how network structure relates to ecological organization and resilience.

---

## Objectives
- Construct a directed interaction network from ecological records.
- Quantify structural properties such as modularity, nestedness, clustering, and centrality metrics.
- Compare native vs. non-native species in network position.
- Evaluate robustness under targeted removal of species.
- Identify abrupt structural transitions indicative of loss of resilience.

---

## Methods
Network properties were computed using standard graph-theoretical tools:

- Modularity — greedy Newman algorithm
- Nestedness — NODF metric
- Centrality — degree (in/out), PageRank, closeness, betweenness
- Clustering coefficient
- Density
- Robustness — size of the largest strongly connected component under node removal

Species were classified as native or non-native using metadata from the database.

A targeted attack strategy was performed by iteratively removing nodes with the highest out-degree.

---

## Main Results

### 1. Network Structure
The biotic network exhibits a mixed modular and nested organization. Modularity is more apparent among native species, while non-native generalists increase nestedness.

![Modularity_Nestedness](Figures/Modularity_Nestedness.png)

---

### 2. Centrality Distributions
Native and non-native species show similar centrality distributions, although the highest-ranked nodes tend to be non-native.

![Centrality_Distributions](Figures/Centrality_Distributions.png)

---

### 3. Clustering and Density
Clustering remains relatively high despite network heterogeneity, indicating multiple interaction pathways across taxonomic groups.

![Clustering_Density](Figures/Clustering_Density.png)

---

### 4. Targeted Node Removal
Removing nodes with the largest out-degree causes:
- rapid decrease in edge density
- increase in modularity
- sudden drop in robustness near ~50% removal
- fragmentation of the strongly connected component

This behavior contrasts with near-linear degradation under random removal.

![Removal_Simulation](Figures/Removal_Simulation.png)

---

### 5. Interpretation
Non-native species tend to participate more frequently in non-mutualistic interactions compared to native species. Their generalist roles shift the global architecture toward higher nestedness and reduce modular separation, potentially affecting ecological stability.

---

## Repository Structure
