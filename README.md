# EDA-Exploratory-Data-Analysis
This project analyzes a medical condition dataset to determine the top three medical conditions that contribute to hospital readmissions. The dataset contains 10,000 rows and 53 columns, with both categorical and numerical responses. Categorical responses include values like ‘Yes’ or ‘No’, while numerical responses include columns such as income, population, and age. The dataset features a column named "ReAdmis," which indicates whether a patient was readmitted to the hospital within a month after discharge. Other columns in the dataset detail medical conditions such as high blood pressure, stroke, obesity, arthritis, and diabetes, along with patient demographics (e.g., gender, age, job, education), services received, length of hospital stay, and type of initial admission. Additionally, there are eight columns with survey responses from patients.

The dataset, named Medical_raw_data.csv, was cleaned through several steps. After importing the data into Jupyter Notebook, the dtypes() function was used to verify the variable names and data types for each column. The unique() function was applied to display the unique values for each column.

The cleaning process involved handling duplicates, missing values, and outliers as follows:

Duplicates: The unique() function was first used to identify unique values in each variable. For ordinal categorical data types (e.g., education, marital status, income), the value_counts() function was used to count the occurrences of each unique value. Ordinal categorical variables with "Yes/No" values were then replaced with numerical values (0/1) to help the algorithm interpret them as ordered variables (Larose & Larose, 2019, p. 36). To detect duplicate values, the .duplicated() function was used, filtering for rows with duplicate entries:
data = med_data.loc[med_data.duplicated()].

Missing Values: The .isnull() function was applied to identify variables with missing values. For columns with a normal distribution, the missing values were replaced with the mean. For columns with a skewed distribution, the median was used instead (Webinar 2: "Getting Started with Missing Values and Outliers").

Outliers: To improve algorithm performance, the data was standardized using z-scores. Outliers were identified by looking for values with z-scores greater than 3 or less than -3. The .std() function was used to detect outliers by examining the standard deviation values for each column.

These steps were essential in preparing the dataset for further analysis and modeling.








