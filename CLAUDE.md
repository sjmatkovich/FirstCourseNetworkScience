# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## About This Repository

Supplementary materials for **"A First Course in Network Science"** (Cambridge University Press, 2020) by Menczer, Fortunato, and Davis. The repository contains Jupyter notebooks, datasets, and sample materials for teaching network science.

## Running the Notebooks

No build system or test suite exists — notebooks are the primary artifact. Run them interactively:

```bash
jupyter notebook
```

Or for a specific notebook:
```bash
jupyter notebook "tutorials/Chapter 1 Tutorial.ipynb"
```

**Required packages:** Python 3, NetworkX (≥2.4), matplotlib, jupyter. The standard Anaconda distribution includes all of these.

**Chapter 4 Twitter notebooks** additionally require `twarc`:
```bash
pip install twarc
```

**Chapter 7** depends on the bundled [tutorials/simulation.py](tutorials/simulation.py) — this file must be in the same directory when running that notebook.

## Repository Structure

- [tutorials/](tutorials/) — 7 chapter notebooks + Python appendix + `simulation.py`
- [datasets/](datasets/) — Network datasets in `.edges`, `.adjlist`, `.graphml`, `.json` formats
- [sample/](sample/) — Instructor materials (chapter PDFs, slides, exercise solutions)

## Notebook Conventions

All tutorial notebooks follow a consistent pattern:
- Markdown cells explain concepts with equations
- Code cells demonstrate NetworkX usage step-by-step
- Exercise prompts for students to complete

Datasets are loaded via relative paths from the notebook's location, e.g.:
```python
G = nx.read_edgelist('../datasets/karate_club.graphml')
```

## Key Libraries Used

| Library | Purpose |
|---------|---------|
| `networkx` | Core graph creation, metrics, algorithms |
| `matplotlib.pyplot` | Network visualization and plots |
| `collections.Counter` | Degree distributions |
| `twarc` | Twitter/X API data collection (Ch. 4 only) |

The `simulation.py` module provides a `Simulation` class used in Chapter 7 for modeling dynamic processes (spreading, diffusion) on networks.
