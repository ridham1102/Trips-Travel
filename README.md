# Trips-Travel
 # **Problem Statement:**

The notebook starts by outlining the problem: "Trips & Travel.Com" wants to predict which customers are likely to purchase a new Wellness Tourism Package to make their marketing efforts more efficient.

 # **Data Collection:**

This section focuses on loading the dataset.

*   **Import Libraries:** Imports all the necessary Python libraries for data manipulation (pandas, numpy), visualization (matplotlib, seaborn, plotly), and machine learning (sklearn). It also includes settings to ignore warnings and display plots inline in the notebook.
*   **Load Data:** Loads the `Travel.csv` file into a pandas DataFrame named `df`.

 # **Data Cleaning:**

This section focuses on preparing the data for modeling by handling inconsistencies and missing values.

*   **Display Head:** Displays the first two rows of the DataFrame to give a quick look at the data structure and columns.
*   **Display Info:** Provides a summary of the DataFrame, including the column names, non-null counts, and data types. This helps identify columns with missing values and understand the data types.
*   **ProductPitched Value Counts:** Checks the distribution of values in the 'ProductPitched' column.
*   **Gender Value Counts:** Checks the distribution of values in the 'Gender' column and identifies an inconsistency ('Fe Male').
*   **MaritalStatus Value Counts:** Checks the distribution of values in the 'MaritalStatus' column and identifies inconsistencies ('Single' and 'Unmarried').
*   **Clean MaritalStatus:** Replaces the inconsistent values in the 'MaritalStatus' column by combining 'Single' and 'Unmarried' into a single category 'Single'.
*   **Clean Gender:** Replaces the inconsistent value 'Fe Male' in the 'Gender' column with 'Female'.
*   **Verify MaritalStatus:** Verifies that the inconsistencies in 'MaritalStatus' have been corrected by displaying the value counts again.
*   **Check Null Values:** Calculates and displays the number of missing values in each column.
*   **Missing Value Percentage:** Calculates and prints the percentage of missing values for columns that have them.
*   **Describe Numerical Missing Features:** Provides descriptive statistics (count, mean, std, min, max, quartiles) for the numerical columns that have missing values.
*   **TypeofContact Value Counts:** Checks the distribution of values in the 'TypeofContact' column.
*   **Fill Missing Values:** Fills the missing values in various columns using appropriate strategies: mean for 'Age', mode for 'TypeofContact', median for 'DurationOfPitch', mode for 'NumberOfFollowups', mode for 'PreferredPropertyStar', mode for 'NumberOfTrips', mode for 'NumberOfChildrenVisiting', and median for 'MonthlyIncome'.
*   **Verify No Nulls:** Verifies that all missing values have been successfully handled by checking the null counts again.
*   **Display Head after Cleaning:** Displays the first row of the DataFrame after completing the missing value handling.

 # **Feature Engineering:**

This section creates a new feature and drops redundant ones.

*   **Create TotalVisiting:** Creates a new column 'TotalVisiting' by summing the values from 'NumberOfPersonVisiting' and 'NumberOfChildrenVisiting', and then drops the original two columns as they are no longer needed.
*   **Display Head after Feature Engineering:** Displays the first two rows of the DataFrame to show the new 'TotalVisiting' column and the removal of the original columns.
*   **Display Info after Feature Engineering:** Provides information about the DataFrame after feature engineering to show the updated column list and data types.

 # **Feature Identification:**

This section identifies the types of features in the dataset.

*   **Identify Numerical Features:** Identifies and prints the number of numerical features.
*   **Identify Categorical Features:** Identifies and prints the number of categorical features.
*   **Identify Discrete Features:** Identifies and prints the number of discrete numerical features (columns with 25 or fewer unique values).
*   **Identify Continuous Features:** Identifies and prints the number of continuous numerical features.

 # **Data Splitting:**

This section prepares the data for model training and evaluation.

*   **Separate Features and Target:** Separates the features (all columns except 'ProdTaken') into DataFrame `x` and the target variable ('ProdTaken') into Series `y`.
*   **Train-Test Split:** Splits the data into training and testing sets using `train_test_split` from scikit-learn, with a test size of 20% and a random state for reproducibility.

 # **Preprocessing:**

This section prepares the data for the machine learning model.

*   **Identify Feature Types for Preprocessing:** Identifies categorical and numerical feature names from the `x` DataFrame.
*   **ColumnTransformer:** Sets up a `ColumnTransformer` to apply different preprocessing steps to different column types. In this case, it's configured to apply One-Hot Encoding to the categorical features. A `StandardScaler` for numerical features is commented out but included as an option.
*   **Apply Preprocessing:** Applies the defined preprocessing steps to the training and testing feature sets (`x_train` and `x_test`).

 # **Random Forest Implementation:**

This section focuses on building and evaluating the Random Forest model.

*   **Import RandomForestClassifier:** Imports the `RandomForestClassifier` model from scikit-learn.
*   **Initialize and Train Model:** Initializes a `RandomForestClassifier` model and trains it using the preprocessed training data (`x_train`, `y_train`).
*   **Make Predictions:** Makes predictions on the preprocessed test set (`x_test`).
*   **Import Metrics:** Imports the `accuracy_score` and `classification_report` metrics from scikit-learn.
*   **Print Accuracy:** Calculates and prints the accuracy score of the model on the test set.
*   **Print Classification Report:** Prints the classification report, which includes precision, recall, and F1-score for each class, as well as overall accuracy, macro average, and weighted average.
