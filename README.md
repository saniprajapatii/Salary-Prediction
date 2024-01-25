# DataScience_glassdoor_salary_project: Project Overview
* Created a tool that estimates data science salaries (MAE ~ $ 11K) to help data scientists and data analyst negotiate their income when they get a job.
* Scraped over 1000 job descriptions from glassdoor using python and selenium
* Performed Feature Engineering from the text of each job description to quantify the value companies put on python, excel, aws, and spark using different encoding 
  techniques.
* Performed Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model and finally gone with Random Forest Regressor.

# Code and tools Used
* Python Version: 3.7
* Packages: pandas, numpy, sklearn, matplotlib, seaborn

 # over 1000 job postings from glassdoor.com
 # Job title
 * Salary Estimate
 * Job Description
 * Rating
 * Company
 * Location
 * Company Headquarters
 * Company Size
 * Company Founded Date
 * Type of Ownership
 * Industry
 * Sector
 * Revenue
 * Competitors

# Data Cleaning(Amazing Part)

After scraping the data, I needed to clean it up so that it was usable for our model. I made the following changes and created different variables according to the usecase:

* Parsed numeric data out of salary
* Made columns for employer provided salary,hourly wages,minimum salary,maximum salary and average salary.
* Removed rows without salary
* Parsed rating out of company text
* Made a new column for company state
* Added a column for if the job was at the company’s headquarters
* Added a column to check whether the job posting location is same as headquarter location as it plays an important role in salary prediction.
* Transformed founded date into age of company
* Made columns for if different skills were listed in the job description:
  * Python
  * Excel
* Column for simplified job title and Seniority
* Column for description length

# EDA

I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables.


# Model Building

First, I transformed the categorical variables into dummy variables using encoding technique. I also split the data into train and tests sets with a test size of 20%.

I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.

* I tried three different models:
* Multiple Linear Regression – Baseline for the model
* Lasso Regression – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.
* Random Forest – Again, with the sparsity associated with the data, I thought that this would be a good fit and it is a good fit after performing hyperparameter 
   optimization using grid search CV.





























