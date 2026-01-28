# SDP-Relaxed AC Optimal Power Flow (MATPOWER / PYPOWER)

This repository demonstrates an **AC Optimal Power Flow (AC-OPF)** formulation using a **semidefinite programming (SDP) relaxation** (Lavaei–Low) implemented in **Python**.

The workflow mirrors the classic **MATPOWER** pipeline:
- Load a MATPOWER-style case using **PYPOWER**
- Construct the network admittance matrix (`makeYbus`)
- Solve the relaxed AC-OPF using **CVXPY**
- Inspect solution quality via the rank of the lifted voltage matrix

## Contents
- `notebooks/`  
  - `sdp_opf_case9.ipynb` – SDP relaxation of AC-OPF on the IEEE 9-bus system

## How to run
Click the badge below to open the notebook directly in Google Colab (no local setup required):

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/notebooks/sdp_opf_case9.ipynb
)

Then run the cells top-to-bottom.

## Methods
- AC power flow modeled using the complex bus admittance matrix
- Voltage lifting: \( W = V V^H \)
- Rank-1 constraint relaxed → convex SDP
- Solved with the SCS solver via CVXPY

## Dependencies
- Python 3.x
- PYPOWER
- CVXPY
- NumPy / SciPy

(All installed automatically in Colab.)

## Notes
- This is a **relaxation** of the nonconvex AC-OPF problem.
- For many small test cases (e.g., IEEE 9-bus), the relaxation is tight.

## References
- R. D. Zimmerman et al., *MATPOWER: Steady-State Operations, Planning and Analysis Tools for Power Systems Research and Education*, IEEE TPS, 2011  
- J. Lavaei and S. H. Low, *Zero Duality Gap in Optimal Power Flow Problem*, IEEE TPS, 2012
