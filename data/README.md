# Data Directory Overview

This directory contains all data used for the performance analysis project comparing the DeepSeek and ChatGPT AI platforms. The data is organized into two main subdirectories:

## Folder Structure

### raw/
- **deepseek_vs_chatgpt.csv**  
  This is the original dataset downloaded from Kaggle ([Dataset URL](https://www.kaggle.com/datasets/khanaakif/deepseek-vs-chatgpt-ai-platform-comparison)). The file has not been modified and serves as the baseline data for the project.

### preprocessed/
This folder contains processed data derived from the original dataset using the preprocessing script located at `src/preprocessor.ipynb`. The following files are included:

- **preprocessed_data.csv**  
  Represents the complete dataset after undergoing cleaning and transformation. The preprocessing steps include:
    - **Data Inspection:** Initial preview, examination of data structure, and shape analysis.
    - **Data Cleaning:** Removal of duplicate records and dropping of rows with missing values.
    - **Data Type Conversion:** Conversion of specific columns (e.g., `Response_Accuracy`, `Response_Speed_sec`, `User_Rating`, `User_Experience_Score`) to numeric types. Rows containing non-convertible values (resulting in `NaN`) are removed.
    - **Summary Statistics Calculation:** Calculation of basic summary statistics (mean, standard deviation, minimum, maximum) for key numeric performance metrics, grouped by `AI_Model_Version` for evaluation purposes.

- **deepseek_data.csv**  
  A subset of the preprocessed data containing records exclusively for the "DeepSeek" AI platform. This file is created by filtering the preprocessed dataset based on the `AI_Platform` column.

- **chatgpt_data.csv**  
  A subset of the preprocessed data containing records exclusively for the "ChatGPT" AI platform. This file is also created by filtering the preprocessed dataset based on the `AI_Platform` column.

## Preprocessing Workflow

The preprocessing was performed using the script located at `src/preprocessor.ipynb`. Below is a summary of the steps executed in the script:

1. **Imports:**  
   The script imports necessary Python libraries such as `os`, `pandas`, `matplotlib`, and functions from `sklearn` for data processing and visualization.

2. **Dataset Loading:**  
   The script loads the original dataset from the `raw` directory using `pandas.read_csv()`.

3. **Initial Data Inspection:**  
   It prints the first few rows, data types, and the overall shape of the dataset to understand its structure and any potential issues (e.g., duplicates or missing values).

4. **Data Cleaning:**
    - **Duplicate Removal:** Identifies and drops duplicate rows.
    - **Missing Values Handling:** Drops rows with any missing values to simplify subsequent processing.

5. **Data Type Conversion:**  
   The script converts the following columns to numeric types:
    - `Response_Accuracy`
    - `Response_Speed_sec`
    - `User_Rating`
    - `User_Experience_Score`  
      Any conversion errors (that yield `NaN`) result in the affected rows being dropped.

6. **Summary Statistics Calculation:**  
   Summary statistics (mean, standard deviation, minimum, and maximum) are computed for the specified numeric columns, grouped by the `AI_Model_Version` column. This step aids in understanding the distribution of performance metrics across different model versions.

7. **Saving Processed Data:**  
   The final, cleaned dataset is saved as `preprocessed_data.csv`. Furthermore, based on the `AI_Platform` column, the data is split into two separate files:
    - `deepseek_data.csv` for the DeepSeek platform data.
    - `chatgpt_data.csv` for the ChatGPT platform data.

## How to Use This Data

- **Raw Data:**  
  The `raw` folder contains the unmodified original dataset. It is recommended to keep this file intact as a reference or backup.

- **Preprocessed Data:**  
  The files in the `preprocessed` folder have been cleaned and transformed for analysis. These files can be directly loaded into your analysis tools for further processing, such as exploratory data analysis, visualization, or model training.

This README is intended to guide you through the data organization and explain the preprocessing steps applied to derive the final datasets used in the project.