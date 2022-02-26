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


