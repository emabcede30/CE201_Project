# CE201_Project
CE201 Project of a structure

# 🏗️ 3D Matrix Structural Analysis Engine in Python

**A pure Python computational core and interactive web-CLI for solving 3D structural frameworks.**

This project is a high-performance Finite Element solver built to perform static equilibrium evaluations on complex space frame structures. It cleanly decouples a heavy mathematical backend (`NumPy`, `Pandas`) from a responsive, retro-style web-terminal UI (`FastAPI`, `Xterm.js`). 

Users can interact with the engine via browser-based terminal commands or natively through a Jupyter Notebook (`CE201_Project_code.ipynb`). The system reads concrete geometry and section properties directly from a `properties.csv` file, automatically calculates exact member self-weights (using a $2.4 \times 10^{-8} \text{ kN/mm}^3$ density), and executes full 3D spatial transformations to resolve structural displacements and internal forces.

### ✨ Core Capabilities
* **12x12 Stiffness Matrices:** Computes complete local element matrices accounting for axial stiffness, torsion, and biaxial bending.
* **Exact Geometric Loading:** Translates global gravity vectors into local element coordinate frames to generate precise Fixed-End Forces (FEF).
* **Direct Solver Partitioning:** Slices the global stiffness matrix to isolate and solve for active degrees of freedom (DOF) and boundary support reactions.

### 📐 Governing Equation
The underlying equilibrium is resolved using direct matrix partitioning:

$$
\begin{bmatrix}
K_{ff} & K_{fs} \\
K_{sf} & K_{ss}
\end{bmatrix}
\begin{bmatrix}
U_f \\
U_s
\end{bmatrix} = \begin{bmatrix}
P_f \\
P_s
\end{bmatrix}
$$

*Where:*
* $K_{ff}$ = Global stiffness matrix sub-tensor matching unconstrained (free) degrees of freedom.
* $U_f$ = Unknown global nodal translations and rotations to be computed ($U_f = K_{ff}^{-1} P_f$).
* $P_s$ = Assembled boundary matrix reactions evaluated post-displacement calculation ($P_s = K_{sf} U_f$).

## 🛠️ Environment Setup & Execution Guide

This project uses an Anaconda environment to manage all dependencies and matrix calculations. Follow these steps to recreate the environment on your local machine and launch the analysis notebook directly from your command line.

### Prerequisites
Make sure you have [Anaconda](https://www.anaconda.com/download) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installed on your system.

### Quick Start (Command Line)
Open your Terminal (or Anaconda Prompt on Windows), navigate to the root directory of this project, and run the following commands sequentially:

```bash
# 1. Create the environment from the configuration file
conda env create -f environment.yml

# 2. Activate the newly created environment
conda activate your_env_name

# 3. Launch Jupyter Notebook and open the project file directly
jupyter notebook CE201_Project_code.ipynb
