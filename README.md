# COMP-4449-Project-1
Time-series analysis and forecasting of the Denver housing market using ZHVI data

# Denver Housing Market Time-Series Analysis

## Overview
This project performs a time-series analysis and forecasting study of the Denver housing
market using publicly available Zillow Home Value Index (ZHVI) data. The primary objective
is to understand historical price dynamics, evaluate market momentum, and generate
short-term forecasts using classical statistical models. Model results are compared against
Zillow’s proprietary Home Value Forecast (ZHVF) to assess convergence between transparent
statistical methods and industry-standard projections.

This repository is designed to be fully reproducible and easy to understand for reviewers,
instructors, and collaborators.

---

## Research Objective
The central research questions addressed in this project are:

- How has the Denver housing market evolved over time based on historical ZHVI data?
- Can classical time-series models capture meaningful trend-level dynamics in home values?
- How do independently generated forecasts compare to Zillow’s published expectations?

Rather than optimizing for short-term predictive accuracy, this work emphasizes
interpretability, validation, and economic plausibility of model behavior.

---

## Dataset Description
Two Zillow datasets are used:

- **ZHVI.csv** — Historical Zillow Home Value Index (observed home values)
- **ZHVF.csv** — Zillow Home Value Forecast (percentage-based projections)

The datasets include geographic metadata (RegionName, RegionType, StateName) and monthly
time-series values spanning multiple decades. ZHVI and ZHVF are treated independently
throughout the analysis to avoid mixing observed values with forecasted data.

Feature labeling and augmentation are performed through time-based transformations
(month-over-month change, year-over-year change, rolling averages) to encode temporal
dynamics suitable for analysis and modeling.

---

## Project Structure

```text
Project 1/
├── Project1.ipynb        # Main analysis notebook
├── environment.yml       # Conda environment specification
├── run_project1.sh       # Optional execution helper script
├── data/                # Raw Zillow datasets
├── outputs/             # Processed data and model outputs
└── README.md             # Project documentation


```
## How to Run This Project

The instructions below assume no prior setup beyond a working operating system and an
internet connection. The project uses a Conda environment to ensure reproducibility across
platforms.

---

## (Windows)

These instructions are written for users who have never run a Python data science project
before. All steps can be completed using **Anaconda Prompt** or **Windows PowerShell**.

---

### Step 1 — Install Required Software

1. **Install Git**

Download Git for Windows from:
https://git-scm.com/download/win

During installation, accept the default options.

Verify installation by opening **Anaconda Prompt** or **Windows PowerShell** and running:
```powershell
git --version
```

2. **Install Miniconda**

Download the Windows 64-bit installer from:
https://docs.conda.io/en/latest/miniconda.html

During installation:
- Allow Conda to initialize
- Accept the default settings

After installation, restart **Anaconda Prompt** or **Windows PowerShell**, then verify:
```powershell
conda --version
```

---

### Step 2 — Clone the Repository

Choose a location on your computer (for example, Desktop) and run:

```powershell
git clone https://github.com/abramsj7/COMP-4449-Project-1.git
cd COMP-4449-Project-1
```

---

### Step 3 — Create the Conda Environment

This step installs all required dependencies defined in `environment.yml`:

```powershell
conda env create -f environment.yml
```

This process may take several minutes depending on your system.

---

### Step 4 — Activate the Environment

```powershell
conda activate project1
```

After activation, your terminal prompt should begin with `(project1)`.

---

### Step 5 — Launch the Analysis Notebook

```powershell
jupyter lab Project1.ipynb
```

A browser window will open automatically.  
Run the notebook cells from top to bottom to reproduce all results and figures.

---

### (Optional) Troubleshooting

If Jupyter Lab is not recognized, install it inside the environment:

```powershell
conda install jupyterlab
```


## (Linux)

These instructions are written for users who have never run a Python data science project
before on a Linux system. All steps can be completed using a standard terminal and do not
require prior experience with Conda or Jupyter.

### Step 1 — Install Required Software

Most Linux distributions include Git by default. If Git is not installed, install it using
your package manager. For Ubuntu/Debian-based systems:

```bash
sudo apt update
sudo apt install -y git
```

Verify Git installation:

```bash
git --version
```

Install **Miniconda** by downloading and running the Linux installer:

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

Follow the on-screen prompts and allow Conda to initialize your shell.

Restart your terminal, then verify Conda installation:

```bash
conda --version
```

---

### Step 2 — Clone the Repository

Choose a location on your system (for example, your home directory) and run:

```bash
git clone https://github.com/abramsj7/COMP-4449-Project-1.git
cd COMP-4449-Project-1
```

---

### Step 3 — Create the Conda Environment

This step installs all required dependencies defined in `environment.yml`:

```bash
conda env create -f environment.yml
```

This process may take several minutes depending on your system.

---

### Step 4 — Activate the Environment

```bash
conda activate project1
```

After activation, your terminal prompt should begin with `(project1)`.

---

### Step 5 — Launch the Analysis Notebook

```bash
jupyter lab Project1.ipynb
```

A browser window will open automatically.  
Run the notebook cells from top to bottom to reproduce all results and figures.

---

### (Optional) Troubleshooting

If Jupyter Lab is not recognized, install it inside the environment:

```bash
conda install jupyterlab
```

## (MacOS)

These instructions are written for users who have never run a Python data science project
before on macOS. All steps can be completed using the Terminal application and do not
require prior experience with Conda or Jupyter.

### Step 1 — Install Required Software

1. **Install Git**

macOS includes Git, but it may prompt you to install Command Line Tools if not present.
You can also install Git explicitly using Homebrew.

If Homebrew is not installed, install it first:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then install Git:
```bash
brew install git
```

Verify installation:
```bash
git --version
```

2. **Install Miniconda**

Download the macOS installer from:
https://docs.conda.io/en/latest/miniconda.html

For Apple Silicon (M1/M2/M3):
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
bash Miniconda3-latest-MacOSX-arm64.sh
```

For Intel-based Macs:
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh
```

Follow the on-screen prompts and allow Conda to initialize your shell.

Restart your terminal, then verify Conda installation:
```bash
conda --version
```

---

### Step 2 — Clone the Repository

Choose a location on your system (for example, your home directory) and run:

```bash
git clone https://github.com/abramsj7/COMP-4449-Project-1.git
cd COMP-4449-Project-1
```

---

### Step 3 — Create the Conda Environment

This step installs all required dependencies defined in `environment.yml`:

```bash
conda env create -f environment.yml
```

This process may take several minutes depending on your system.

---

### Step 4 — Activate the Environment

```bash
conda activate project1
```

After activation, your terminal prompt should begin with `(project1)`.

---

### Step 5 — Launch the Analysis Notebook

```bash
jupyter lab Project1.ipynb
```

A browser window will open automatically.  
Run the notebook cells from top to bottom to reproduce all results and figures.

---

### (Optional) Troubleshooting

If Jupyter Lab is not recognized, install it inside the environment:

```bash
conda install jupyterlab
```


## Methods and Modeling
The analysis follows a structured pipeline:

1. Data loading and validation
2. Geographic filtering for the Denver market
3. Time-series reshaping and feature engineering
4. Exploratory visualization and diagnostics
5. Stationarity testing and model justification
6. ARIMA and SARIMA model fitting
7. Backtesting using a holdout period
8. Forecast comparison with Zillow’s ZHVF
9. Interpretation and real-world impact discussion

Model validation emphasizes trend-level behavior and stability rather than exact point
prediction accuracy, which is appropriate for macro housing market analysis.

---

## Reproducibility and Environment Setup

This project is fully reproducible using a Conda-managed environment. All dependencies
are explicitly defined in `environment.yml`, ensuring consistent results across operating
systems and machines.

Detailed, platform-specific setup instructions are provided in the
**How to Run This Project** section above.


