# IDS Feature Selection & Hyperparameter Optimization using Metaheuristic Algorithms

## COMP2024 — AI Methods Coursework

### Overview
This project implements and evaluates three metaheuristic algorithms for optimizing an Intrusion Detection System (IDS) classifier on the CICIDS2017 dataset. The algorithms simultaneously perform **feature selection** and **hyperparameter tuning** for a Random Forest classifier.

### Algorithms Implemented
1. **Genetic Algorithm (GA)** — Population-based evolutionary optimization
2. **Particle Swarm Optimization (PSO)** — Swarm intelligence-based optimization
3. **Simulated Annealing (SA)** — Single-solution temperature-based optimization

### Dataset
- **CICIDS2017** — Canadian Institute for Cybersecurity Intrusion Detection Dataset 2017
- Contains network traffic captures (Monday–Friday) with BENIGN and various attack types
- Binary classification: BENIGN (0) vs ATTACK (1)
- Dataset files should be placed in the `archive/` directory

### Project Structure
```
├── README.md                    # This file
├── requirements.txt             # Python dependencies
├── 01_data_preprocessing.ipynb  # Data loading, EDA, cleaning, split, scaling
├── 02_baseline_model.ipynb      # Baseline Random Forest evaluation
├── 03_metaheuristics.ipynb      # GA, PSO, SA optimization experiments
├── archive/                     # CICIDS2017 dataset CSV files
│   ├── Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv
│   ├── Friday-WorkingHours-Afternoon-PortScan.pcap_ISCX.csv
│   ├── Friday-WorkingHours-Morning.pcap_ISCX.csv
│   ├── Monday-WorkingHours.pcap_ISCX.csv
│   ├── Thursday-WorkingHours-Afternoon-Infilteration.pcap_ISCX.csv
│   ├── Thursday-WorkingHours-Morning-WebAttacks.pcap_ISCX.csv
│   ├── Tuesday-WorkingHours.pcap_ISCX.csv
│   └── Wednesday-workingHours.pcap_ISCX.csv
└── results/                     # Generated results (after running notebooks)
    ├── preprocessed_data.pkl    # Preprocessed data (from Notebook 1)
    ├── all_results.json         # Full results JSON
    ├── results_summary.csv      # Summary table
    └── *.png                    # All generated plots
```

### Setup Instructions

1. **Install Python 3.8+** (recommended: Python 3.9 or 3.10)

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Place the dataset:**
   - Extract the CICIDS2017 CSV files into the `archive/` directory

4. **Run the notebooks in order:**
   ```bash
   jupyter notebook
   ```
   - **Notebook 1** (`01_baseline.ipynb`): Run first — loads data, performs EDA, trains baseline, saves preprocessed data
   - **Notebook 2** (`02_preprocessing.ipynb`): Run anytime — detailed data analysis
   - **Notebook 3** (`03_metaheuristics.ipynb`): Run after Notebook 1 — runs GA, PSO, SA optimization (~30–60 minutes)

### Configuration
- **Sample size**: 100,000 rows (configurable in Notebook 1)
- **Random seed**: 42 (for reproducibility)
- **Train/Test split**: 70/30 stratified

### Metaheuristic Parameters
| Algorithm | Key Parameters |
|-----------|---------------|
| GA | Population: 30, Generations: 50, Crossover: 0.8, Mutation: 0.1 |
| PSO | Particles: 30, Iterations: 50, w: 0.9→0.4, c1=c2=2.0 |
| SA | Init temp: 100, Cooling: 0.95, Max iterations: 500 |

### Evaluation Metrics
- Accuracy, Precision, Recall, F1-Score
- False Positive Rate (FPR)
- Number of features selected
- Computational runtime

### Authors
COMP2024 Group XXX
