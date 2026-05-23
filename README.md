# Cirrhosis-Patient-Outcome-Prediction-Using-Data-Mining-Techniques


This project is a Data Mining course project focused on applying the full data mining workflow to a public cirrhosis patient dataset. The project follows a structured process that includes problem definition, data understanding, preprocessing, exploratory data analysis, classification modeling, model comparison, clustering, and interpretation.

The goal of the project is not to provide medical diagnosis, but to practice data mining techniques on a real-world medical dataset and understand how patient characteristics can be analyzed using classification and clustering methods.

## Project Workflow

The project was completed through the following main phases:

1. Problem definition  
2. Data collection and understanding  
3. Data preprocessing  
4. Exploratory data analysis  
5. Decision tree modeling  
6. Model evaluation and comparison  
7. Clustering analysis  
8. Cluster interpretation  
9. Final reporting  

## Dataset

The project uses the UCI Cirrhosis dataset, which contains patient-level information related to cirrhosis progression.

The dataset includes:

- Demographic variables
- Laboratory test variables
- Medical condition indicators
- Treatment-related variables
- Patient outcome status

The target variable is **Status**, which represents the patient outcome category.

## Problem Definition

The project begins by defining the data mining problem: analyzing patient characteristics and building models that can predict patient status based on the available features.

The project also investigates how disease stage, treatment information, laboratory measurements, and class imbalance may affect prediction and interpretation.

## Data Understanding

The dataset was first explored to understand:

- Number of observations and variables
- Attribute types
- Target variable categories
- Numeric and categorical variables
- Missing values
- General value ranges
- Class distribution

Variables were categorized into different data types, such as:

- Numeric / interval variables
- Nominal variables
- Binary variables
- Ordinal variables
- ID variable
- Target variable

This step was important to decide how each variable should be handled before modeling.

## Data Preprocessing

Data preprocessing was performed before building the models.

The preprocessing process included:

### 1. Missing Value Identification

The dataset was checked for missing values across all variables. Missing values were found in several laboratory and treatment-related variables.

### 2. Stage-Based Imputation

Because cirrhosis has multiple disease stages, missing values were handled using a stage-aware approach.

For numeric variables:

- Missing values were filled using the median value within the same patient stage.

For categorical variables:

- Missing values were filled using the mode value within the same patient stage.

This approach was used to reduce imputation bias by considering differences between disease stages.

### 3. Drug Variable Handling

The Drug variable was treated separately because some patients were not part of the clinical trial. Instead of filling these missing values using the most frequent drug value, a separate category was created for patients outside the trial.

### 4. Age Transformation

The Age variable was originally recorded in days. It was converted into years to make the variable easier to interpret during analysis and reporting.

### 5. Outlier Handling

Extreme values were reviewed during preprocessing. Since the dataset represents medical cases, extreme laboratory values were not automatically removed. These values may represent real severe patient conditions rather than data-entry errors.

## Exploratory Data Analysis

Exploratory Data Analysis was used to better understand the structure of the dataset before modeling.

The EDA phase included:

- Distribution of patient sex
- Distribution of treatment groups
- Distribution of disease stages
- Distribution of patient status
- Relationship between stage and status
- Age distribution
- Boxplots for selected laboratory variables
- Correlation analysis between numeric variables

The purpose of EDA was to identify patterns, class imbalance, possible relationships between variables, and variables that may be useful in later modeling steps.

## Decision Tree Modeling

Decision tree models were used for classification.

The modeling phase followed the course project requirements by building multiple decision tree models using different parameter settings.

The models were compared using variations in:

- Splitting criterion
- Minimum leaf size
- Maximum number of branches

The purpose of this phase was to test different decision tree structures and compare their predictive performance.

## Model Evaluation

Each decision tree model was evaluated using multiple criteria instead of relying on accuracy alone.

The evaluation criteria included:

- Accuracy
- Simplicity
- Lift
- Stability

A weighted scoring formula was used to combine the evaluation measures into one overall score.

```text
Overall Score = 0.6 × Accuracy + 0.05 × Simplicity + 0.2 × Lift + 0.15 × Stability
```

This helped select the best decision tree model based on both predictive performance and interpretability.

## Clustering Phase

After classification modeling, clustering was applied to explore hidden patient groupings in the dataset.

K-means clustering was used with different numbers of clusters:

- 2 clusters
- 3 clusters
- 4 clusters
- 5 clusters

During clustering, the target variable was excluded because clustering is an unsupervised learning task.

The clustering phase focused on:

- Comparing cluster sizes
- Identifying small or possible outlier clusters
- Exploring whether patients form meaningful groups
- Understanding which variables may separate clusters

A cluster was considered a potential outlier cluster if it contained less than 10% of the original dataset.

## Cluster Interpretation

After generating clusters, a decision tree was used to explain the cluster assignments.

The goal was not to predict the original patient status, but to understand which variables were most useful in separating the clusters.

This phase helped interpret the clustering results by identifying important variables that influenced cluster membership.

## Final Analysis

The final analysis combined the classification and clustering results.

The classification phase focused on predicting patient status using decision trees.

The clustering phase focused on grouping patients based on similar characteristics and interpreting those groups using a decision tree.

Together, these methods supported a broader understanding of the dataset from both supervised and unsupervised learning perspectives.

## Tools Used

- SAS Studio / SAS Viya
- Python
- Data Mining methods
- Decision Trees
- K-means Clustering
- Exploratory Data Analysis
- Model Evaluation

## Repository Contents

```text
FinalDataMiningProject.pdf        # Final project report
README.md                         # Project documentation
```

## Learning Outcomes

This project helped practice the following data mining concepts:

- Understanding real-world datasets
- Identifying data types
- Handling missing values
- Applying preprocessing strategies
- Performing exploratory data analysis
- Building decision tree models
- Comparing models using multiple evaluation measures
- Applying clustering for segmentation
- Interpreting classification and clustering outputs

## Disclaimer

This project is for educational purposes only as part of a Data Mining course. It is not intended for clinical diagnosis, medical decision-making, or real-world patient treatment recommendations.
