# SDP-Relaxed AC Optimal Power Flow (CVXPY)

This repo contains a **semidefinite programming (SDP) relaxation** of **AC Optimal Power Flow (AC-OPF)** implemented in **Python** using **CVXPY**, with MATPOWER-style cases loaded via **PYPOWER**.

## Notebook
- `OPF_cvxpy.ipynb` — end-to-end workflow:
  1) Load a MATPOWER/PYPOWER test case (e.g., IEEE 9-bus)
  2) Build the admittance matrix using `makeYbus`
  3) Formulate the SDP relaxation with lifted voltage matrix \( W = V V^H \) (rank constraint relaxed)
  4) Solve using CVXPY (SCS) and check relaxation tightness via eigenvalues/rank

## Run in Google Colab
Open the notebook directly in Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/OPF_cvxpy.ipynb)

## Notes
- This is a **convex relaxation** of the nonconvex AC-OPF problem (rank-1 constraint dropped).
- If the solution matrix \(W\) is approximately rank-1, the relaxation is typically tight for that case.

## References
- R. D. Zimmerman et al., *MATPOWER: Steady-State Operations, Planning and Analysis Tools for Power Systems Research and Education*, IEEE TPS, 2011  
- J. Lavaei and S. H. Low, *Zero Duality Gap in Optimal Power Flow Problem*, IEEE TPS, 2012
