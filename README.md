# Project Overview

This repository documents my analysis of the **‘Life Expectancies by Multiple Deprivation’ dataset**, obtained from the Office for National Statistics. The project builds on an undergraduate dissertation exploring health and economic status, aiming to predict life expectancy using linear regression within the PySpark framework.

## Approach

### **1. Data Preparation**

1. **Initial Setup**:
   - Imported the necessary libraries to access full functionality.
   - Initialized a Spark session to facilitate data processing within PySpark.

2. **Dataset Loading and Inspection**:
   - Loaded the dataset and inspected its structure for potential issues.
   - Dropped null values to maintain data integrity.
   - Adjusted the datatype of the `Decile` column from integer to string, recognizing that it represents categorical data.
   - Used domain knowledge and cross-validation techniques to validate preprocessing choices, ensuring robustness and avoiding overfitting.

### **2. Feature Engineering**

1. **Categorical Encoding**:
   - Converted categorical columns into numerical representations using `StringIndexer`.
   - Applied `OneHotEncoder` to transform numerical indices into binary vectors, preventing the model from misinterpreting the indices as ordinal data.

2. **Combining Features**:
   - Combined all independent variables into a single vector column using `VectorAssembler` for PySpark compatibility.

### **3. Pipeline and Data Splitting**

1. **Pipeline Creation**:
   - Built a pipeline to automate preprocessing, ensuring consistency across training and test datasets.

2. **Data Splitting**:
   - Split the dataset into training (70%) and test (30%) subsets.
   - Ensured random splitting to prevent data leakage and promote reproducibility.

### **4. Model Training and Evaluation**

1. **Model Training**:
   - Trained a linear regression model on the preprocessed training data.

2. **Performance Metrics**:
   - Evaluated the model using diverse metrics:
     - **Mean Absolute Error (MAE)**: Provided insights into average prediction deviations.
     - **Root Mean Squared Error (RMSE)** and **Mean Squared Error (MSE)**: Highlighted sensitivity to larger errors.
   - Results:
     - **Training Set**: MAE = 0.5928, RMSE = 0.8769, MSE = 0.7689.
     - **Test Set**: MAE = 0.6390, RMSE = 0.9619, MSE = 0.9253.

3. **Visualization**:
   - Plotted 10% of the test dataset results for clarity.
   - Used confusion matrices and other visual tools to evaluate prediction accuracy.

### **5. Limitations and Refinements**

1. **Challenges**:
   - Assumptions such as a linear x-y relationship, observational independence, and absence of outliers may introduce biases.
   - Secondary dataset limitations, such as potential biases in data collection, impact analysis robustness.

2. **Future Improvements**:
   - Leverage PySpark MLlib tools and hyperparameter tuning for optimization.
   - Apply feature engineering techniques to capture nonlinear relationships and improve generalization.
   - Iteratively refine the model to enhance test set performance.

## Tools and Libraries Used

- **PySpark**: For data preprocessing and linear regression.
- **MLlib**: For machine learning pipelines and metrics.

---

Happy coding!
