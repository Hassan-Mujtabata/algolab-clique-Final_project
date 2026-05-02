# Clique Problem — Interactive Visualizer

> **BCS 309 · Algorithms I · Final Project · Spring 2026**  
> Canadian University Dubai · Instructor: Dr. Arash Kermani

**Live demo → [https://hassan-mujtabata.github.io/algolab-clique-Final_project/](https://hassan-mujtabata.github.io/algolab-clique-Final_project/)**

---

## Overview

An interactive, single-file web tool that teaches the **Clique problem** — a classical NP-complete problem in graph theory. The tool visualizes both a brute-force solver and a backtracking-with-pruning solver on user-defined or preset graphs, and includes a full NP-completeness proof walkthrough and an educational learning module.

The Clique problem asks: given an undirected graph G = (V, E) and an integer k, does G contain k vertices where every pair is connected? It has applications in social network analysis, bioinformatics (protein interaction networks), and coding theory.

---

## Features

### Visualizer
- Animated step-by-step graph traversal for both **Brute Force** (enumerate all k-subsets) and **Backtracking with Pruning** (branch-and-bound, prune when `candidates + clique < k`)
- Color-coded node states: candidate, in-clique, rejected, checked
- Live statistics: subsets checked, edge checks, prune events, backtracks
- Pseudocode panel with line-by-line highlighting synced to each algorithm step
- Step counter, speed slider, Play / Pause / Step / Reset controls
- 5 built-in preset graphs (K4 subgraph, dense, sparse, triangle, bipartite)

### Comparison Mode
- Side-by-side simultaneous animation of brute force vs. backtracking on the same graph
- Per-algorithm stat summaries after each run to quantify pruning impact

### NP-Completeness Proof
- Dedicated tab with a structured, two-part proof:
  1. **Clique ∈ NP** — certificate (k vertices) verified in O(k²) via adjacency matrix
  2. **NP-Hardness** — polynomial-time reduction from Independent Set via graph complement construction, with forward and backward direction proofs and polynomiality argument (O(V²))
- Reduction diagram rendered in SVG

### Learn Tab
- Collapsible sections covering problem definition, algorithm paradigm, complexity analysis, and worked example
- Growth curve chart comparing brute-force vs. backtracking empirical operation counts
- Concept boxes for key ideas (NP, NP-complete, pruning condition)

---

## Algorithm Design

| Approach | Paradigm | Time Complexity | Correct? |
|---|---|---|---|
| Brute Force | Exhaustive enumeration | O(V^k · k²) | ✅ Always |
| Backtracking | Divide-and-conquer variant | O(2^V) worst case, much less in practice | ✅ Always |

The backtracking pruning condition: if `|current clique| + |remaining candidates| < k`, the branch cannot possibly produce a clique of size k — backtrack immediately. This eliminates large subtrees from the search space without sacrificing correctness.

---

## Tech Stack

| | |
|---|---|
| Language | Vanilla JavaScript (ES6+) |
| Markup / Style | HTML5, CSS3, SVG |
| Dependencies | **None** — zero external libraries or frameworks |
| Deployment | GitHub Pages (single `index.html`) |

---

## Course Learning Outcomes

| CLO | Description | Coverage |
|---|---|---|
| CLO-3 | Design algorithms using strategies like divide and conquer | Backtracking algorithm design, branching strategy, pruning condition |
| CLO-4 | Apply key algorithm paradigms and methods of analysis | Brute-force vs. backtracking implementation, comparison, visualization |
| CLO-5 | Prove NP-Completeness using polynomial-time reductions | Full Independent Set ≤ₚ Clique proof with both directions |

---

## Run Locally

No build step needed.

```bash
git clone https://github.com/Hassan-Mujtabata/algolab-clique-Final_project.git
cd algolab-clique-Final_project
# Open index.html in any modern browser
```

Or just open `index.html` directly — no server required.

---

## Project Structure

```
algolab-clique-Final_project/
└── index.html   # Entire tool: HTML + CSS + JS in one file
```

---

## Author

**Hassan Mujtaba** · Student ID: 20220002085  
B.Sc. Computer Science · Canadian University Dubai
