# Smarter, not harder: machine learning for scalable drug screening

This repository contains the proof-of-concept (POC) analysis presented in our study on **distribution-preserving sampling subset selection approach for docking score prediction**.
The goal of this work is to demonstrate that for a scaffold-based dataset, it is possible to train predictive models on a very small fraction of the data (≈1%) while maintaining accuracy, thereby reducing computational costs by over 100× compared to training on larger fractions.

---

## Repository Structure
- **POC.ipynb** — Jupyter notebook containing all analyses (feature extraction, distribution comparison, model training, and evaluation).  
- **merged_filtered_data_no_outliers.csv** — Scaffold-based dataset (≈413k molecules), derived from fragment-based virtual screening and filtered for outliers.  
- **HSD11B1_filtered_data_no_outliers.csv** — Benchmark dataset from the DOCKSTRING project, filtered for outliers (≈255k molecules).  

---

## Methods
- **Divergence Analysis**: We quantified how well feature and docking score distributions were preserved across subsets using Kolmogorov–Smirnov, Wasserstein, Jensen–Shannon, and Kullback–Leibler metrics.  
- **Feature Selection**: Top 50 molecular descriptors were selected using regression-based mutual information.  
- **Subset Sampling**: Random vs. distribution-preserving strategies were compared across fractions (1%–75%).  
- **Model Training**: Random Forest regressors were trained on subsets to evaluate predictive performance.  
- **Runtime Comparison**: Training on 1% of the scaffold dataset required ~1 min, compared to ~115 min for 75%, while maintaining similar accuracy.  

---

## Requirements
The analysis uses only widely available Python libraries:

- `numpy`  
- `pandas`  
- `matplotlib`  
- `seaborn`  
- `scikit-learn`  
- `scipy`  

Install requirements with:

`pip install numpy pandas matplotlib seaborn scikit-learn scipy`

## Usage

1. Clone this repository:

	`git clone https://github.com/csbarak/POC.git`
	`cd POC`

2. Open the Jupyter notebook:

	`jupyter notebook POC.ipynb`

3. Run the notebook cells step by step to reproduce the full analysis.

## Citation

If you use this repository, data, or methodology in your work, please cite:

Trachtenberg, A.; Spelkov A.; Akabayov B. (2025). Smarter, not harder: machine learning for scalable drug screening.

## License
This project is released under the MIT License.