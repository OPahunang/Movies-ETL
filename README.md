# Movies-ETL

## Overview:

Amazing Prime Video is a largest online retailer for streaming movies and TV shows. The company wants to develop an algorithm that enable to predict which low budget movies will become popular so that they can buy the streaming rights at a bargain price. 

The requirement is to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. The existing code need to refactor to takes the following files - Wikipedia data, Kaggle metadata, and the MovieLens rating data. After the Extract Transform Load process, the data will be loaded to PostgreSQL database.


## Results:

### Deliverable 1: Write an ETL Function to Read Three Data Files

-	 An ETL function is written to read in the three data files.

![delivery1_ETL_function.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery1_ETL_function.png)


-	The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.

![delivery1_wiki_movies_df_dataframe.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery1_wiki_movies_df_dataframe.png)


-	The function converts the Kaggle metadata file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.

![delivery1_kaggle_metadata_dataframe.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery1_kaggle_metadata_dataframe.png)


-	The function converts the MovieLens ratings data file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.

![delivery1_ratings_dataframe.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery1_ratings_dataframe.png)


### Deliverable 2: Extract and Transform the Wikipedia Data

-	The TV shows are filtered out, and the wiki_movies_df DataFrame is created.

![delivery2_TV_shows_filtered_out.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery2_TV_shows_filtered_out.png)


-	A try-except block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs.

![delivery2_try_except.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery2_try_except.png)


-	The extraction and transformation of the Wikipedia data in the ETL function does the following:

    1) A list comprehension is used to keep columns with non-null values. 
    2) The non-null box office data is converted to string values using the lambda and join functions.
    3) A regular expression is used to match the six elements of "form_one" of the box office data.
    4) A regular expression is used to match the three elements of "form_two" of the box office data.
    5) The following columns are cleaned in the Wikipedia DataFrame: 
  
     	- The box office column
       	- The budget column
      	- The release date column
     	- The running time column


![delivery2_extraction_transformation.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery2_extraction_transformation.png)


-	The cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file.

![delivery2_wiki_movies_dataframe.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery2_wiki_movies_dataframe.png)


![delivery2_wiki_movies_columns.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery2_wiki_movies_columns.png)


### Deliverable 3: Extract and Transform the Kaggle data

-	The extraction and transformation of the Kaggle metadata using the ETL function does the following:

    1) The Kaggle metadata is cleaned. 
    2) The Wikipedia and Kaggle DataFrames are merged. 
    3) The following is performed on the merged Wikipedia and Kaggle DataFrames to create the movies_df: 

	- Unnecessary columns are dropped.
	- A function is used to fill in the missing Kaggle data.
	- The movies_df DataFrame is filtered to keep specific columns.
	- The movies_df DataFrame columns are renamed.

![delivery3_extraction_kaggle.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery3_extraction_kaggle.png)


-	The extraction and transformation of the MovieLens ratings data using the ETL function does the following:

    1) The ratings counts are cleaned. 
    2) The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the movies_with_ratings_df DataFrame. 
    3) The empty values in the movies_with_ratings_df DataFrame are filled with “0”. 


![delivery3_extraction_movielens.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery3_extraction_movielens.png)


-	The movies_with_ratings_df and the movies_df DataFrames are displayed in the ETL_clean_kaggle_data.ipynb file.

![delivery3_movies_with_ratings_df.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery3_movies_with_ratings_df.png)


![delivery3_movies_df.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery3_movies_df.png)


### Deliverable 4: Create the Movie Database

-	The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png. 

![movies_query.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/movies_query.png)


-	The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png. 

![ratings_query.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/ratings_query.png)


-	The elapsed time to add the data to the database is displayed in the ETL_create_database.ipynb file.

![delivery4_elapsed_time_to_add_to_database.png](https://github.com/OPahunang/Movies-ETL/blob/main/Resources/delivery4_elapsed_time_to_add_to_database.png)






