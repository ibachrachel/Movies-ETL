### Movies-ETL

## Module 8: ETL; PostgreSQL

# Overview

*Background* 

As the main data analyst for a company, Amazing Prime, the next task is to create a single, clean dataset that can be used for an upcoming hackathon. In data analysis, a hackathon is an event where teams of analysts collaborate to work intensively on a project, using data to solve a problem. Hackathons generally last several days, and teams work around the clock on their projects.The company wants users to predict future hit movies and shows, so that the company can buy the rights and have them available for watchers. This algorithm will need a clean dataset that can be presented to the company. 

*Purpose* 

The dataset is assembled and Amazing Prime loves the dataset and wants to keep it updated on a daily basis. A coworker needs your help to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. You’ll need to refactor the code from this module to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.

*Programs Used*

Jupyter Notebook
Pg Admin 4
PostgreSQL 12

# Summary 

*Deliverable 1:*

- An ETL function is written to read in the three data files.

- The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.

- The function converts the Kaggle metadata file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.

- The function converts the MovieLens ratings data file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.

*Deliverable 2:*

- The TV shows are filtered out, and the wiki_movies_df DataFrame is created.

-  try-except block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs.

- Extraction and transformation of the Wikipedia data in the ETL function does the following:
* list comprehension is used to keep columns with non-null values. 
* The non-null box office data is converted to string values using the lambda and join functions.
* A regular expression is used to match the six elements of "form_one" of the box office data.
* A regular expression is used to match the three elements of "form_two" of the box office data.
- The following columns are cleaned in the Wikipedia DataFrame: (8 pt)
 a. The box office column
 b. The budget column
 c. The release date column
 d. The running time column
- Cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file. 
