**This project purpose was to create an ETL Pipeline on AWS for analyzing Spotify Top 50 Globally Popular Songs.**

The ETL process involves extracting data using Python and spotipy library, then cleaning it, converting it into CSV format, loading it into Snowflake for further analysis, and making a Power BI dashboard on top of it.

**Project Flow:**
1. Created a S3 bucket to store the Spotify data which is further classified into 2 folders ( raw_data ) and ( transformed_data ).
2. Now building 2 lambda functions, 
    (i) spotify_api_data_extract: This function will extract the data by using  python and spotipy library and then store it into the raw_data folder of the   s3 bucket.
   (ii) spotify_transformation_data: This function will transform the raw data , clean it, and load it into the transformed_data folder of the s3 bucket. It will have three categories (artist,album, songs).
3. Now created 2 triggers for automating the process,
   (i) First one will trigger the spotify_api_data_extract function every day for   extracting the top 50 popular songs and store it.
  (ii) Second one will trigger the spotify_transformation_data function which will be executed whenever data is available in the raw_folder of the s3 bucket.
4. Now after getting the transformed data, it is loaded into Snowflake for further analysis. 
5. Then used the Snowflake ODBC driver to import the data from Snowflake database to Power BI and make a dashboard on top of it for generating insights.

Dashboard Link:https://project.novypro.com/jxD4Dj
**Architecure Diagram**:
![architecture](https://github.com/user-attachments/assets/cdaf3c8b-bdde-495a-b6ce-caddffff75de)
