# Double-layer-computer-network-communication-relationship-structure-dataset

# Real-World Double-Layer Network Datasets

This repository contains two real-world network datasets used for validating malware propagation models in the paper _"Modeling and Predicting Malware Propagation in Double-Layer Computer Networks"_.

## Dataset 1: Facebook Social Circles
**Source**: Stanford Network Analysis Project (SNAP)
**Original Context**:
- Nodes represent anonymized Facebook users from designated social circles
- Edges represent direct social relationships (friendships, messaging interactions)
- Collected via Facebook API from survey participants

**Double-Layer Construction**:
- Created using ego networks of **Node 0** and **Node 348** from original data
- Subnetwork A: 334 nodes, avg. degree ⟨k⟩^A = 17.08
- Subnetwork B: 225 nodes, avg. degree ⟨k⟩^B = 30.36
- **44 inter-layer dependency edges** (⟨q⟩^C = 5.855×10⁻⁴)

## Dataset 2: Email-Eu-Core
**Source**: European Research Institution Emails
**Original Context**:
- Nodes represent institution members from 42 departments
- Edges capture email exchanges (direction preserved)
- Temporal span: 18 months of communication records

**Double-Layer Construction**:
- Integrated email interactions within **Department 4** and **Department 14**
- Subnetwork A: 109 nodes, avg. degree ⟨k⟩^A = 4.08
- Subnetwork B: 92 nodes, avg. degree ⟨k⟩^B = 6.00
- **288 inter-layer dependency edges** (⟨q⟩^C = 2.87×10⁻²)

## File Format
**Structured Data Files** (Excel Workbook):
- `facebook_double_layer.xlsx`:
- *Sheet A*: Intra-layer adjacency matrix for Subnetwork A (334×334)
- *Sheet B*: Intra-layer adjacency matrix for Subnetwork B (225×225)
- *Sheet C*: Inter-layer dependency matrix (334×225)

- `email_eu_core.xlsx`:
- *Sheet A*: Intra-layer adjacency matrix for Subnetwork A (109×109)
- *Sheet B*: Intra-layer adjacency matrix for Subnetwork B (92×92)
- *Sheet C*: Inter-layer dependency matrix (109×92)

**Data Specifications**:
- Binary adjacency matrices (1 = connection exists, 0 = no connection)
- Symmetric matrices for undirected intra-layer connections
- Non-symmetric matrices for directed inter-layer dependencies

**Auxiliary Files**:
- `data_conversion.py`: Python script containing:
- Edge list to matrix conversion logic
- Matrix symmetry validation
- Excel file export functionality

## Usage in Research
These datasets were used to:
1.  Validate double-layer propagation model accuracy
2.  Analyze infection thresholds via reproduction number R₀
3.  Quantify structural/dynamic perturbation impacts

## Citation
When using these datasets, please cite both:
```bibtex
@article{leskovec2014snap,
title={SNAP Datasets: Stanford large network dataset collection},
author={Leskovec, Jure and Krevl, Andrej},
year={2014},
url={http://snap.stanford.edu/data}
}

@article{duan2024modeling,
title={Modeling and Predicting Malware Propagation in Double-Layer Computer Networks},
author={Duan, Dongli and Yang, Xiaohao and Lv, Changchun and Cai, Zhiqiang},
journal={IEEE Transactions},
year={2024},
doi={pending}
}
