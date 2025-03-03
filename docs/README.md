# **Documentation for Code Execution, Dependencies, and Example Usage**

This document provides step-by-step instructions to **execute the code**, **install dependencies**, and **understand example usage** of the provided scripts and Jupyter notebooks.

---

## **1. Code Execution Instructions**
To run the provided scripts and notebooks, follow these steps:

### **A. Setup Environment**
Ensure you have **Python 3.8+** installed. We recommend using a virtual environment:

```bash
python -m venv env
source env/bin/activate  # On MacOS/Linux
env\Scripts\activate  # On Windows
```

### **B. Install Required Dependencies**
All dependencies are listed in `requirements.txt` in `dependencies/` folder. Install them using:

```bash
pip install -r docs/dependencies/requirements.txt
```

### **C. Run Jupyter Notebooks**
To execute the notebooks for data preprocessing and network analysis, use:

```bash
jupyter notebook
```

Then open:

`Data-Preprocessing-Steps.ipynb` (for cleaning and transforming the dataset)
`ML-Explanation-SNA.ipynb` (for Social Network Analysis and visualization)

### **D. Running Python Scripts (Alternative to Notebooks)**
For those preferring command-line execution, the equivalent Python scripts are provided. Run them as follows:

```bash
python data/dataPreprocessing/Data-Preprocessing-Steps.py
python code/ML-Explanation-SNA.py
```

## **2. Dependencies**
The following libraries are required for execution. They are included in `requirements.txt`, but can also be installed manually:

```bash
pip install pandas numpy matplotlib networkx scipy scikit-learn jupyter
```

- **pandas (>=1.3.0)** – For data handling and preprocessing
- **numpy (>=1.21.0)** – For numerical computations
- **matplotlib (>=3.4.0)** – For visualizing comorbidity networks
- **networkx (>=2.6.0)** – For constructing and analyzing disease networks
- **scipy (>=1.7.0)** – For statistical analysis (e.g., Fisher’s exact test)
- **scikit-learn (>=0.24.0)** – For machine learning utilities
- **jupyter (>=1.0.0**) – To run the provided notebooks

To check installed versions:

```bash
pip list
```

## **3. Example Usage**

### **A. Running Data Preprocessing**
After setting up the environment, open `Data-Preprocessing-Steps.ipynb` or run:

```bash
python data/dataPreprocessing/Data-Preprocessing-Steps.py
```

This script:

- Loads raw comorbidity data (`Preprocessed_Comorbidity_Data_PS2.csv`)
- Handles missing values using KNN imputation
- Normalizes numerical variables
- Saves the processed dataset for further analysis

### **B. Constructing and Analyzing the Comorbidity Network**
Open `ML-Explanation-SNA.ipynb` or run:

```bash
python code/ML-Explanation-SNA.py
```

This script:

- Constructs the comorbidity network from hospital admission records
- Calculates centrality measures (Degree, Betweenness, Eigenvector)
- Applies Louvain community detection to identify disease clusters
- Generates visualizations of the comorbidity network across different time periods

## **⚠️ Troubleshooting**

| Issue | Possible Cause | Solution |
|--------|------------------|------------|
| `ModuleNotFoundError` | Missing dependency | Run `pip install -r docs/dependencies/requirements.txt` |
| `FileNotFoundError` | Dataset missing | Ensure `Preprocessed_Comorbidity_Data_PS2.csv` is in `data/` folder |
| Kernel crashes in Jupyter | Memory overload | Run scripts instead of notebooks (`python code/ML-Explanation-SNA.py`) |
