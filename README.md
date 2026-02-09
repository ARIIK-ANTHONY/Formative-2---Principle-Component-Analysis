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

**Step 1: Clone my repository**
```bash
git clone https://github.com/ARIIK-ANTHONY/Formative-2---Principle-Component-Analysis.git
cd Formative-2---Principle-Component-Analysis
```

**Step 2: Download the dataset**
You need to download the data file separately because it's too large for GitHub:
- Go to [Kaggle - Agricultural Survey of African Farm Households](https://www.kaggle.com/datasets/crawford/agricultural-survey-of-african-farm-households)
- Download `data.csv` (35MB file)
- Put it in the same folder as my notebook

**Step 3: Install required packages**
```bash
pip install -r requirements.txt
```

**Step 4: Open and run my notebook**
```bash
jupyter notebook "Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb"
```

**Important:** Make sure you download the data file first - my code won't work without it!

## Installation Requirements

**What You Need:**
- Python 3.7 or higher
- pip (usually comes with Python)

**Required Python Packages:**
I only used three packages to keep it simple:
```bash
pip install numpy pandas matplotlib
```

Or use my requirements file:
```bash
pip install -r requirements.txt
```

**Test Your Installation:**
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
print("Ready to run PCA!")
```

**Download the Dataset:**
This is crucial - you MUST download the data file separately:

1. Go to [Kaggle](https://www.kaggle.com/datasets/crawford/agricultural-survey-of-african-farm-households)
2. Download `data.csv` (it's about 35MB)
3. Save it in the same folder as my notebook
4. The file is too big for GitHub, so I excluded it using .gitignore

Open Python and verify the packages are correctly installed:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
print("All packages installed successfully")
```

## What My Code Does

**Important:** Don't forget to download `data.csv` first!

**Running My Analysis:**
1. Clone my repository 
2. Download the data file and put it in the same folder
3. Open my notebook:
```bash
jupyter notebook "Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb"
```

**What Happens When You Run It:**

I structured my notebook to follow the assignment requirements step by step:

1. **Load and Explore Data** - I load the CSV and show you the dataset structure
2. **Handle Missing Values** - I identify and fix all the NaN values (required by rubric)
3. **Encode Non-Numeric Data** - I properly convert categorical columns to numbers (required by rubric)
4. **Standardize Features** - I manually apply standardization using the exact formula from class
5. **Calculate Covariance Matrix** - I compute covariances to understand feature relationships
6. **Perform Eigendecomposition** - I extract eigenvalues and eigenvectors using np.linalg.eig()
7. **Sort by Explained Variance** - I sort eigenvalues in descending order (required by rubric)
8. **Select Optimal Components** - I dynamically choose components for 90% variance retention
9. **Transform the Data** - I project original data onto principal components
10. **Create Visualizations** - I show before/after plots with proper axis labels (required by rubric)

**What You'll See:**
- Clean data preprocessing with status updates
- Explained variance percentages for each component
- Automatic selection of ~627 components (from original 1,708 features)
- Side-by-side plots showing original features vs. principal components
- Clear demonstration that PC1 has highest variance, PC2 has second highest
- Evidence that data structure is preserved but rotated to maximize variance

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

## My Project Files

```
Formative-2---Principle-Component-Analysis/
│
├── Template_PCA_Formative_1[Peer_Pair_Number] 2.ipynb  # My main PCA notebook
├── data.csv                                           # Dataset (you need to download this!)
├── requirements.txt                                   # Required Python packages
├── README.md                                          # This file
├── .gitignore                                         # Excludes large data file
└── .git/                                              # Git repository
```

**What Each File Does:**
- **My Notebook:** Contains all my PCA code with visible outputs (as required by assignment)
- **Data File:** 9,597 African households with 1,753 features - download separately from Kaggle
- **Requirements:** Just numpy, pandas, matplotlib - kept it simple
- **README:** Instructions on how to run my project

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
African Agricultural Survey: https://www.kaggle.com/datasets/crawford/agricultural-survey-of-african-farm-households

**Submission:** https://github.com/ARIIK-ANTHONY/Formative-2---Principle-Component-Analysis