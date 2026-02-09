# Principal Component Analysis Implementation for African Agricultural Data

This repository contains a comprehensive implementation of Principal Component Analysis (PCA) applied to large-scale African agricultural survey data. The implementation demonstrates advanced linear algebra concepts including eigenvalue decomposition, covariance matrix analysis, and dimensionality reduction techniques applied to real-world socioeconomic data.

## Dataset

**African Agricultural Survey (2002-2004)**

This analysis uses data from an extensive agricultural survey conducted across eleven African countries by the World Bank and Global Environment Facility. The survey captured detailed information from over 9,500 households during the 2002/2003 and 2003/2004 growing seasons, providing insights into farming systems, climate adaptation strategies, and agricultural characteristics across diverse African agro-climatic zones.

**Data Characteristics:**
- 9,597 household observations across 1,753 variables
- Countries covered: Burkina Faso, Cameroon, Ghana, Niger, Senegal, Egypt, Ethiopia, Kenya, South Africa, Zambia, and Zimbabwe
- Multi-dimensional survey data including numeric measurements, categorical responses, and missing value patterns
- Seven-section questionnaire covering household demographics, farming practices, climate adaptation, and economic factors

**Source:** Agricultural Survey of African Farm Households (Kaggle)
**Original Research:** Waha, K., Zipf, B., Kurukulasuriya, P., & Hassan, R. (2016). An agricultural survey for more than 9,500 African households. Nature Scientific Data.
**DOI:** https://doi.org/10.6084/m9.figshare.c.1574094

## Technical Implementation

This project implements PCA entirely from scratch using NumPy, demonstrating mastery of the underlying mathematical concepts without relying on high-level machine learning libraries. The implementation includes:

**Core PCA Algorithm:**
- Manual data standardization using the formula: (Data - Data Mean) / Data Standard Deviation
- Covariance matrix computation for understanding feature relationships
- Eigenvalue decomposition to identify principal components and explained variance
- Dynamic component selection based on cumulative explained variance thresholds
- Data projection onto selected principal components for dimensionality reduction

**Key Features:**
- Robust handling of missing values through intelligent imputation strategies
- Automatic detection and encoding of categorical variables
- Performance-optimized matrix operations for large datasets
- Comprehensive variance analysis and component interpretation
- Comparative visualization of original versus transformed feature spaces

## Installation

**Prerequisites:**
- Python 3.7 or higher
- pip package manager

**Required Dependencies:**

Install the necessary packages using pip:

```bash
pip install numpy pandas matplotlib
```

Alternatively, install from the requirements file:

```bash
pip install -r requirements.txt
```

**Verify Installation:**

Open Python and verify the packages are correctly installed:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
print("All packages installed successfully")
```

## Usage

**Running the Analysis:**

1. Clone or download this repository to your local machine
2. Ensure the `data.csv` file is placed in the same directory as the notebook
3. Open the Jupyter notebook in your preferred environment:

```bash
jupyter notebook Template_PCA_Formative_1[Peer_Pair_Number].ipynb
```

**Step-by-Step Execution:**

The notebook is structured in sequential steps that build upon each other:

1. **Data Loading and Preprocessing:** Load the CSV file and examine the dataset structure
2. **Data Standardization:** Apply manual standardization to normalize feature scales
3. **Covariance Analysis:** Compute the covariance matrix to understand feature relationships
4. **Eigenvalue Decomposition:** Extract eigenvalues and eigenvectors from the covariance matrix
5. **Component Selection:** Sort components by explained variance and select optimal number
6. **Data Transformation:** Project original data onto selected principal components
7. **Visualization:** Compare original and transformed data spaces through scatter plots

**Expected Outputs:**

- Detailed analysis of data preprocessing steps and missing value handling
- Variance explained by each principal component with cumulative percentages
- Dimensionality reduction summary showing compression from 1,708 to optimal feature count
- Side-by-side visualizations comparing original feature space with principal component space
- Statistical summaries demonstrating successful standardization and transformation

## Results Interpretation

The PCA implementation successfully reduces the dimensionality of the African agricultural dataset while preserving approximately 90% of the original variance. The analysis reveals:

- **Dimensionality Reduction:** Significant compression from 1,708 original features to a much smaller set of principal components
- **Variance Preservation:** Dynamic selection ensures retention of maximum information content
- **Feature Relationships:** Principal components capture underlying patterns in African agricultural practices
- **Data Visualization:** Clear demonstration of how PCA rotates data into directions of maximum variance

## Project Structure

```
Formative-2---Principle-Component-Analysis/
│
├── Template_PCA_Formative_1[Peer_Pair_Number].ipynb    # Main analysis notebook
├── data.csv                                            # African agricultural dataset
├── requirements.txt                                    # Python package dependencies
├── README.md                                          # This documentation file
└── PCA_Assignment_Interactive.py                      # Alternative Python script version
```

## Academic Context

This implementation fulfills the requirements for an advanced linear algebra formative assignment focusing on Principal Component Analysis. The work demonstrates practical application of eigenvalue decomposition, covariance analysis, and multivariate statistics to real-world African agricultural data, contributing to understanding of farming systems and climate adaptation across diverse African contexts.

The choice of African agricultural data aligns with the assignment's emphasis on meaningful, real-world applications while meeting technical requirements for dataset complexity, missing values, and mixed data types.

## Technical Notes

- All mathematical operations implemented using NumPy for educational transparency
- Standardization follows the explicit formula provided in assignment guidelines
- Error handling includes edge cases such as zero standard deviation and missing data patterns
- Visualization code optimized for clear interpretation of PCA transformation effects
- Code documentation emphasizes understanding of underlying mathematical concepts

## References

Waha, K., Zipf, B., Kurukulasuriya, P., & Hassan, R. (2016). An agricultural survey for more than 9,500 African households. *Nature Scientific Data*, 3, 160020. https://doi.org/10.6084/m9.figshare.c.1574094

Dataset source: https://www.kaggle.com/datasets/crawford/agricultural-survey-of-african-farm-households