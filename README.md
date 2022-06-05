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

- The following columns are cleaned in the Wikipedia DataFrame: 

 a. The box office column
 
 b. The budget column
 
 c. The release date column
 
 d. The running time column
 
- Cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file. 

*Deliverable 3*

- The extraction and transformation of the Kaggle metadata using the ETL function does the following:

-- The Kaggle metadata is cleaned.

-- The Wikipedia and Kaggle DataFrames are merged. 

-- The following is performed on the merged Wikipedia and Kaggle DataFrames to create the movies_df:

a. Unnecessary columns are dropped.

b. A function is used to fill in the missing Kaggle data.

c.The movies_df DataFrame is filtered to keep specific columns.

d. The movies_df DataFrame columns are renamed.

- The extraction and transformation of the MovieLens ratings data using the ETL function does the following

-- The ratings counts are cleaned.

-- The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the movies_with_ratings_df DataFrame.
-- The empty values in the movies_with_ratings_df DataFrame are filled with “0”. 

- The movies_with_ratings_df and the movies_df DataFrames are displayed in the ETL_clean_kaggle_data.ipynb file

*Deliverable 4*

- The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png
- The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png.
- The elapsed time to add the data to the database is displayed in the ETL_create_database.ipynb file.
