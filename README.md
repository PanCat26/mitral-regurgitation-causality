# Causal Structure Learning for Mitral Regurgitation via Graph Neural Networks

Code and data for the paper *"Causal Structure Learning for Mitral Regurgitation via Graph Neural Networks"*.

The pipeline learns a directed dependency graph over echocardiographic measurements centered on mitral regurgitation (MR) area, producing an interpretable heatmap rather than only a scalar prediction.

## Repository Structure

```
.
├── data/
│   ├── pacients_raw.xlsx          # Raw echocardiographic spreadsheet
│   ├── pacients_clean.csv         # Systolic-filtered subset
│   ├── pacients_train.csv         # Training split (preprocessed)
│   ├── pacients_val.csv           # Validation split (preprocessed)
│   └── pacients_test.csv          # Test split (preprocessed)
├── model/
│   ├── graph_causality_pipeline.ipynb   # Main notebook (data prep + both approaches)
├── paper/
│   └── Causal_Structure_Learning_for_Mitral_Regurgitation_via_Graph_Neural_Networks.pdf
└── README.md
```

## Environment Setup

**Python >= 3.10** is recommended.

Make sure the required packages are installed:

### Option A: pip

```bash
pip install numpy pandas scikit-learn torch matplotlib seaborn openpyxl
```

### Option B: conda

```bash
conda create -n mr-causality python=3.10 -y
conda activate mr-causality
conda install numpy pandas scikit-learn matplotlib seaborn openpyxl -c conda-forge
conda install pytorch -c pytorch
```

## Usage

Open `model/graph_causality_pipeline.ipynb` and run all cells sequentially.
   - **Section 2** filters systolic frames and writes `pacients_clean.csv`.
   - **Section 3** performs the patient-level train/val/test split and preprocessing.
   - **Section 5** trains the single-layer masked graph model (Approach 1).
   - **Section 6** trains the two-layer masked graph model (Approach 2).

## License

This project is provided for academic and research purposes.
