# CE201_Project
CE201 Project of a structure

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
