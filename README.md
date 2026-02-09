# My Principal Component Analysis Implementation - African Agricultural Data Analysis

This is my individual formative assignment for Advanced Linear Algebra, where I implemented Principal Component Analysis (PCA) completely from scratch using NumPy. I chose to analyze African agricultural survey data because it represents a meaningful real-world dataset that meets all the assignment requirements - it contains missing values, non-numeric columns, and over 10 features as specified in the rubric.

## What I Accomplished

- **Built PCA from scratch** using only NumPy - no sklearn or pre-built PCA functions
- **Analyzed real African data** - 9,597 households across 11 countries with 1,753 original features
- **Achieved 90% variance retention** while reducing dimensions from 1,708 to ~627 components
- **Created before/after visualizations** showing the transformation from original feature space to principal component space
- **Implemented dynamic component selection** based on explained variance thresholds
- **Handled missing values and categorical data** as required by the assignment rubric

## Why I Chose This Dataset

I selected the African Agricultural Survey data because it perfectly meets the assignment requirements and represents meaningful research. The dataset contains:

**Assignment Requirements Met:**
- **Missing Values:** The dataset has many NaN values across different columns that I properly handled
- **Non-Numeric Data:** Multiple categorical columns including country names, farming practices, and survey responses that I encoded appropriately
- **10+ Columns:** Contains 1,753 features - far exceeding the 10 column requirement
- **Impactful African Data:** Real survey data from 11 African countries, not generic datasets like house prices or wine quality

**Dataset Details:**
- **Source:** Agricultural Survey of African Farm Households (World Bank & Global Environment Facility)
- **Size:** 9,597 households × 1,753 variables (35MB CSV file)
- **Countries:** Burkina Faso, Cameroon, Ghana, Niger, Senegal, Egypt, Ethiopia, Kenya, South Africa, Zambia, Zimbabwe
- **Time Period:** 2002-2004 growing seasons
- **Content:** Household demographics, farming practices, climate adaptation strategies, economic factors

This data allowed me to demonstrate PCA on a real-world problem while meeting all technical requirements for the assignment.

## My PCA Implementation Process

I implemented PCA completely from scratch using only NumPy to demonstrate my understanding of the underlying mathematical concepts. Here's what I accomplished:

**Step 1: Data Preprocessing (Rubric - Data Handling)**
- Identified and handled all missing values using appropriate imputation techniques
- Found and properly encoded non-numeric columns (country names, categorical responses)
- Applied feature scaling to ensure all variables are on the same scale

**Step 2: Mathematical Implementation**
- **Manual Standardization:** Applied the formula (Data - Data.mean()) / Data.std() to each feature
- **Covariance Matrix:** Calculated the covariance matrix to understand feature relationships
- **Eigendecomposition:** Used np.linalg.eig() to extract eigenvalues and eigenvectors

**Step 3: Component Selection (Rubric - Explained Variance Calculation)**
- **Sorted eigenvalues in descending order** to identify components with highest variance
- **Calculated explained variance percentages** for each component
- **Implemented dynamic selection** based on 90% cumulative variance threshold
- **Selected optimal number of components** (~627) that retain most information while reducing dimensions

**Step 4: Visualization (Rubric - Before/After PCA)**
- **Before PCA Plot:** Shows original feature space with actual feature names as axis labels
- **After PCA Plot:** Shows principal component space with PC1 and PC2 as axis labels
- **Preserved data structure:** Same number of data points, clusters remain visible but rotated
- **Correct PCA scaling:** PC1 shows highest variance, PC2 shows second highest variance
- **Clear explanation:** Documented how PCA transforms the data and what the rotation means

This implementation demonstrates my understanding of eigenvalue decomposition, covariance analysis, and the mathematical foundations of PCA without relying on pre-built functions.

## How to Run My Project

**Quick Start (5 minutes):**
1. `git clone https://github.com/ARIIK-ANTHONY/Formative-2---Principle-Component-Analysis.git`
2. `cd Formative-2---Principle-Component-Analysis`
3. `pip install -r requirements.txt`
4. Download `data.csv` from [Kaggle](https://www.kaggle.com/datasets/crawford/agricultural-survey-of-african-farm-households) → put in project folder
5. `jupyter notebook "Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb"`
6. Run all cells (Cell → Run All)

**Important:** Step 4 is CRITICAL - you must download the data file separately!

## Installation Instructions

**Step-by-Step Setup Guide:**

**1. Prerequisites Check**
Make sure you have:
- Python 3.7 or higher installed
- pip package manager (comes with Python)
- Jupyter Notebook or JupyterLab installed

**2. Clone My Repository**
```bash
git clone https://github.com/ARIIK-ANTHONY/Formative-2---Principle-Component-Analysis.git
cd Formative-2---Principle-Component-Analysis
```

**3. Install Required Python Packages**
```bash
# Install all dependencies at once
pip install -r requirements.txt

# OR install individually
pip install numpy pandas matplotlib jupyter
```

**4. Download the Dataset (CRITICAL STEP)**
 **You MUST download this file separately - the project won't work without it!**

- Visit: https://www.kaggle.com/datasets/crawford/agricultural-survey-of-african-farm-households
- Click "Download" button (35MB file)
- Extract and save `data.csv` in the project root directory
- The file should be in the same folder as the notebook

**5. Verify Your Setup**
```bash
# Test that everything is installed correctly
python -c "import numpy, pandas, matplotlib; print('All packages ready!')"

# Check if data file exists
python -c "import os; print('Data file found!' if os.path.exists('data.csv') else 'ERROR: Download data.csv first!')"
```

Open Python and verify the packages are correctly installed:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
print("All packages installed successfully")
```

## How to Use My PCA Implementation

**Quick Start:**
```bash
# After completing installation above
jupyter notebook "Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb"
```

**Detailed Usage Instructions:**

**1. Launch the Notebook**
```bash
# From your project directory
jupyter notebook
# Then click on "Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb"
```

**2. Run All Cells in Order**
My notebook is designed to run sequentially. You can either:
- **Option A:** Click "Cell" → "Run All" to execute everything at once
- **Option B:** Run each cell individually using `Shift + Enter`

**3. What Each Section Does:**

**Cell 1-2 (Data Loading):**
- Loads the 35MB African agricultural dataset
- Checks for missing file and provides download instructions
- Shows original dataset dimensions (9,597 × 1,753)

**Cell 3-4 (Data Preprocessing):**
- Handles missing values using mean imputation
- Encodes categorical variables (country names, survey responses)
- Applies manual standardization: `(Data - Mean) / Standard Deviation`

**Cell 5-6 (PCA Implementation):**
- Calculates covariance matrix using `np.cov()`
- Performs eigendecomposition with `np.linalg.eig()`
- Sorts eigenvalues in descending order (highest variance first)

**Cell 7-8 (Component Selection):**
- Calculates explained variance ratios for each component
- Dynamically selects components for 90% variance retention
- Reduces dimensions from 1,708 to ~627 components

**Cell 9 (Visualization):**
- Creates before/after PCA comparison plots
- Shows original feature space vs principal component space
- Demonstrates how PCA rotates data for maximum variance

**4. Expected Outputs:**
- **Data preprocessing:** Status messages showing successful encoding and standardization
- **Variance analysis:** Percentage variance explained by each principal component
- **Dimensionality reduction:** Summary showing 63.3% reduction in features
- **Visualizations:** Two side-by-side scatter plots comparing original vs transformed data
- **Mathematical verification:** Confirmation that PC1 > PC2 in terms of variance explained

**5. Troubleshooting:**
- **"File not found" error:** Download data.csv from Kaggle first
- **Import errors:** Run `pip install -r requirements.txt`
- **Jupyter not opening:** Install with `pip install jupyter`
- **Plots not showing:** Make sure matplotlib is installed

## My Results

**What I Achieved:**
- **Reduced 1,708 features down to ~627 components** while keeping 90% of the variance
- **Successfully handled missing values and categorical data** as required by the assignment
- **Implemented PCA completely from scratch** using only NumPy (no sklearn)
- **Created proper before/after visualizations** with correct axis labels
- **Demonstrated dynamic component selection** based on explained variance

**Why This Matters:**
- I reduced the dataset by 63.3% while retaining most of the important information
- My visualizations clearly show how PCA rotates data into directions of maximum variance
- The first principal component (PC1) captures the most variance, PC2 captures the second most
- All 9,597 data points are preserved, just transformed into a better coordinate system

**Assignment Requirements Met:**
✓ Used African dataset with missing values and non-numeric columns  
✓ Correctly calculated explained variance percentages  
✓ Sorted eigenvalues in descending order  
✓ Selected components based on explained variance (not arbitrary)  
✓ Created both before and after PCA plots  
✓ Properly labeled axes (feature names → PC1, PC2)  
✓ Preserved data structure while showing rotation effect  
✓ Demonstrated that PC1 has highest variance  

## What I Learned from This Analysis

Working with this African agricultural data taught me a lot about both PCA and real-world data science:

**About PCA:**
- **Dimensionality Reduction Works:** I successfully compressed 1,708 features into ~627 components while keeping 90% of the variance - that's huge data reduction with minimal information loss
- **Eigenvalues Tell the Story:** Sorting eigenvalues in descending order clearly shows which components matter most
- **Visualization is Key:** My before/after plots prove that PCA rotates data into directions of maximum variance - you can see how the data spreads out differently along PC1 vs PC2
- **Math Actually Works:** Implementing the covariance matrix and eigendecomposition from scratch helped me understand what's really happening under the hood

**About African Agricultural Data:**
- **Complex Relationships:** The high dimensionality reflects how many factors influence farming in Africa - everything from household size to rainfall patterns
- **Missing Data Challenges:** Real survey data is messy - I had to carefully handle NaN values and mixed data types
- **Cultural Context Matters:** Working with African data instead of generic datasets made the analysis more meaningful

**Technical Insights:**
- **Component Selection:** Using explained variance threshold (90%) is smarter than picking an arbitrary number of components
- **Data Preprocessing:** Proper standardization is crucial - without it, features with larger scales dominate the principal components
- **Visualization Impact:** Comparing original feature space vs PC space clearly shows how PCA finds the "best" coordinate system for the data

## Project Structure & Files

```
Formative-2---Principle-Component-Analysis/
│
├── Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb  # MAIN FILE - My PCA implementation
├── data.csv                                           # DOWNLOAD REQUIRED - African agricultural dataset  
├── requirements.txt                                   # Python packages needed
├── README.md                                          # This instruction file
├── .gitignore                                         # Excludes large data file from git
└── .git/                                              # Git repository files
```

**File Descriptions:**

**`Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb`**
- **Purpose:** Main Jupyter notebook containing my complete PCA implementation
- **Size:** ~15KB
- **Contents:** All code cells with visible outputs, step-by-step PCA from scratch
- **How to use:** Open with Jupyter and run cells sequentially

**`data.csv`** 
- **Purpose:** African Agricultural Survey dataset (source for analysis)
- **Size:** 35MB (too large for GitHub)
- **Contents:** 9,597 households × 1,753 features from 11 African countries
- **How to get:** Download from Kaggle link provided in installation section

**`requirements.txt`**
- **Purpose:** Lists all Python packages needed to run my code
- **Contents:** numpy, pandas, matplotlib (minimal dependencies)
- **How to use:** Run `pip install -r requirements.txt`

**`README.md`**
- **Purpose:** Complete instructions for installation and usage (this file)
- **Contents:** Setup guide, usage instructions, project explanation
- **How to use:** Read this before running anything!

## Assignment Requirements Met

This project completes my Formative 2 assignment for Advanced Linear Algebra. I made sure to follow all the requirements:

✓ **Individual work** - This is entirely my own implementation
✓ **African data** - Used meaningful agricultural survey data, not generic datasets
✓ **Missing values** - Dataset contains NaN values that I properly handled
✓ **Non-numeric columns** - Categorical data that I encoded correctly
✓ **10+ columns** - 1,753 features far exceeds the minimum requirement
✓ **From-scratch PCA** - Implemented using only NumPy, no sklearn shortcuts
✓ **Visible outputs** - All code cell results are displayed in my notebook
✓ **GitHub repo** - Professional repository with documentation

## Important Notes

- **No Shortcuts:** I implemented everything using NumPy to show I understand the math
- **Formula Used:** Standardization follows (Data - Mean) / Standard Deviation as taught in class
- **Error Handling:** My code handles missing values and edge cases properly
- **Clean Output:** I removed unnecessary print statements to keep output focused
- **Proper Visualization:** Before/after plots clearly show the PCA transformation
- **Math Understanding:** Comments explain what each step does mathematically
- **Large Files:** Used .gitignore to exclude the 35MB data file from GitHub

## Data Source
African Agricultural dataset from Kaggle: https://www.kaggle.com/datasets/crawford/agricultural-survey-of-african-farm-households

**Submission:** https://github.com/ARIIK-ANTHONY/Formative-2---Principle-Component-Analysis
