# Quorum-Based Privacy-Preserving Distributed Anomaly Detection

**Implementation of quorum-consensus federated anomaly detection using Isolation Forests.**  
Clients train local Isolation Forest models and share models or scores to reach a quorum-based decision on anomalies while keeping raw data local.

---

## Table of contents
- [Overview](#overview)  
- [Repository structure](#repository-structure)  
- [Requirements](#requirements)  
- [Quickstart](#quickstart)  
- [Notebooks & usage](#notebooks--usage)  
- [Data](#data)  
- [Experimental notes](#experimental-notes)  
- [Citation](#citation)
- [Contributions](#contributions)
---

## Overview
This project demonstrates two practical approaches for federated anomaly detection:

- **Equal-weight quorum:** every client’s model contributes equally to the aggregated decision.  
- **Weighted quorum:** client contributions are weighted (e.g., by local dataset size or validation reliability) for more robust aggregation in heterogeneous settings.

These methods preserve client privacy by sharing only models, scores, or secure aggregates — no raw data leaves clients.

---

## Repository Structure
Code/                       # Jupyter notebooks (experiments & plots)
  equal_quorum.ipynb
  weighted_quorum.ipynb
  utils.ipynb
Data/                       # Dataset files (tracked via Git LFS)
  x.csv
  README.md
References/                 # Bibliographic references
  references.bib
.gitattributes             # Git LFS configuration
README.md                  # This file

---

## Requirements
Tested with Python 3.8+; core dependencies typically include:
- numpy, pandas
- scikit-learn (IsolationForest)
- matplotlib / seaborn
- jupyterlab / notebook

Install from `requirements.txt` (add this file if not present):
```bash
python -m pip install -r requirements.txt
```
---
## Quickstart
1. Clone the repo
```
git clone https://github.com/ParthN9i4/A-Quorum-based-Privacy-Preserving-Distributed-Learning-Technique-for-Anomaly-Detection.git
cd A-Quorum-based-Privacy-Preserving-Distributed-Learning-Technique-for-Anomaly-Detection
```

2. Install and pull LFS objects
```
# Linux example: follow https://github.com/git-lfs/git-lfs/wiki/Installation
git lfs install
git lfs pull
```

3. Run the notebooks
```
jupyter notebook Code/
```
## Notebooks & usage
- equal_quorum.ipynb — trains local Isolation Forests on partitioned data, shares models, and produces equal-weight quorum-based labels/metrics.

- weighted_quorum.ipynb — same flow but computes a weighted aggregated score (weights by dataset size / validation metric).

- utils.ipynb — helper functions: data split, scoring, plotting, evaluation metrics.

Recommended workflow:

- Prepare Data/x.csv (or provide path to your dataset).

- Run the preferred notebook end-to-end.

- Adjust quorum q and weighting rules in the notebook parameters.

## Data
- The Data/ folder contains x.csv (main dataset). This file may be large and is tracked via Git LFS. If you cannot clone LFS objects, download the dataset separately (see Data/README.md).

- If you plan to host the dataset externally (Zenodo / Figshare), include a DOI or public URL in Data/README.md for reproducibility.

## Experimental notes
-  Isolation Forest isolates anomalies via average path length across trees — suitable for unsupervised anomaly detection (Liu et al., 2008).

- Weighted aggregation helps when clients have heterogeneous dataset sizes or quality: scale each client’s score by an appropriate weight (e.g., w_j ∝ |D_j| or validation F1).

- For privacy in real deployments, prefer sending local scores (or masked/crypted contributions) and use secure aggregation or homomorphic encryption rather than raw model-sharing (Bonawitz et al., 2017; McMahan et al., 2017).

## Citation
If you use this repository or code in your research, please cite the implementation:
@misc{parth2025quorum,
  author       = {{ParthN9i4}},
  title        = {A Quorum-based Privacy-Preserving Distributed Learning Technique for Anomaly Detection},
  year         = {2025},
  howpublished = {\url{https://github.com/ParthN9i4/A-Quorum-based-Privacy-Preserving-Distributed-Learning-Technique-for-Anomaly-Detection}},
}

## Contributions
- Primary implementation by Pranav P.S.S contact <pranav040801@gmail.com>
- For any other information, contact <nparth@sssihl.edu.in>




