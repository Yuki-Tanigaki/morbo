[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

# Multi-Objective Bayesian Optimization over High-Dimensional Search Spaces (Modified Version)

This repository is a **research-focused fork** of the original MORBO codebase:

> **Multi-Objective Bayesian Optimization over High-Dimensional Search Spaces**  
> https://arxiv.org/abs/2109.10964

Original implementation by **Samuel Daulton, David Eriksson, Maximilian Balandat, and Eytan Bakshy**  
(© Meta Platforms / Facebook Research — MIT License).

This fork updates the environment to modern PyTorch/GPyTorch/BoTorch versions and fixes several compatibility issues while preserving the original algorithmic structure.

If you use this repository in academic work, **please cite the original paper**:

```
@InProceedings{pmlr-v162-daulton22a,
  title = 	 {Multi-Objective Bayesian Optimization over High-Dimensional Search Spaces},
  author =       {Daulton, Samuel and Eriksson, David and Balandat, Maximilian and Bakshy, Eytan},
  booktitle = 	 {Proceedings of the Thirty-Eighth Conference on Uncertainty in Artificial Intelligence},
  year = 	 {2022},
  series = 	 {Proceedings of Machine Learning Research},
  publisher =    {PMLR},
}
```

---

# 🚀 Getting Started (with uv)

This project now uses **uv** for environment creation and dependency management, replacing the original `setup.py` workflow.

## 1. Install uv

Linux / WSL:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

macOS:

```bash
brew install uv
```

---

## 2. Clone the repository

```bash
git clone https://github.com/<your-name>/morbo.git
cd morbo
```

---

## 3. Create the environment

```bash
uv sync
```

---

## 4. Activate the environment

```bash
source .venv/bin/activate
```

or

```bash
uv run python experiments/main.py dtlz2_100d morbo 0
```

---

# 🧪 Running Experiments

Experiments are defined in the `experiments/` directory.  
Each experiment folder contains a `config.json` describing the benchmark settings.

### Basic usage:

```bash
cd experiments
python main.py <experiment_name> <algorithm> <seed>
```

Example:

```bash
python main.py dtlz2_100d morbo 0
```

The available algorithms:

```
algorithms = [
    ("morbo", "MORBO"),
]
```

Available experiment configs:

```
experiments = {
    "dtlz2_10d":       "DTLZ2 (d=10)",
    "dtlz2_30d":       "DTLZ2 (d=30)",
    "dtlz2_100d":      "DTLZ2 (d=100)",
    "dtlz3_m2":        "DTLZ3 (M=2)",
    "dtlz5_m2":        "DTLZ5 (M=2)",
    "dtlz7_m2":        "DTLZ7 (M=2)",
    "dtlz3_m4":        "DTLZ3 (M=4)",
    "dtlz5_m4":        "DTLZ5 (M=4)",
    "dtlz7_m4":        "DTLZ7 (M=4)",
    "rover":           "Rover",
    "vehicle_safety":  "Vehicle Safety",
    "welded_beam":     "Welded Beam",
}
```

GPU acceleration is supported and can significantly speed up experiments.

---

# 📁 Repository Structure

```
morbo/
  ├── morbo/                # Core MORBO implementation (modified)
  ├── experiments/          # Experiment configs and main runner
  ├── pyproject.toml        # Modern dependency & package metadata
  ├── uv.lock               # Reproducible lockfile for uv
  ├── LICENSE               # MIT License (original project)
  └── README.md             # This file
```

---

# 📚 Acknowledgements

This repository builds upon the excellent work by the original MORBO authors.  
All algorithmic credit belongs to the original paper and its contributors.



