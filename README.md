# OPF with CVXPY

This repository contains a Python implementation of **Optimal Power Flow (OPF)** using **CVXPY**, with MATPOWER-style test cases loaded via **PYPOWER**.

## Notebook
- **OPF_cvxpy.ipynb**  
  https://github.com/Abhiramvp/OPF-with-CVXpy/blob/main/OPF_cvxpy.ipynb

## Description
The notebook demonstrates:
- Loading MATPOWER/PYPOWER test cases (e.g., IEEE 9-bus)
- Construction of the network admittance matrix using `makeYbus`
- Formulation of an **SDP relaxation of AC-OPF** using a lifted voltage matrix
- Solving the convex relaxation with CVXPY and inspecting solution tightness

## References
- R. D. Zimmerman et al., *MATPOWER: Steady-State Operations, Planning and Analysis Tools for Power Systems Research and Education*, IEEE Transactions on Power Systems, 2011  
- J. Lavaei and S. H. Low, *Zero Duality Gap in Optimal Power Flow Problem*, IEEE Transactions on Power Systems, 2012
