# nosql-challenge

## Module 12 Challenge

For this challenge, I used a database of various food establishments in the United Kingdom to evaluate some of the ratings for each place. To do this, I leveraged MongoDB, PyMongo, and Pandas to query the database and generate results to display in DataFrames.

### Setup

Using MongoClient, I established a connection to the database and set a variable to the collection 'establishments' to use for querying. After, I added a new restaurant to the database and updated the BusinessType field to be consistent with the rest. Moving forward, restaurants in Dover were removed by querying the LocalAuthorityName for Dover. Finally, the latitude and longitude fields' data types were updated to be decimal numbers, while RatingValues were changed to integers after replacing documents containing text for this field with None.

### Analysis

For this part, I answered questions about the database. For each question, a DataFrame was created for each query's result, and some of the questions require the use of the 'count_documents' function to obtain the number of documents from each query.

The questions included querying for hygiene scores equal to 20 and finding establishments in London and with a RatingValue greater than or equal to 4. The following question required searching for the top 5 establishments near the new restaurant added from the previous part. The query involved searching within the latitudes and longitudes calculated, while also having a RatingValue of 5. The results were limited to 5 and sorted in ascending order on the hygiene score. The last question involved creating an aggregation pipeline for establishments with a 0 hygiene score. The pipeline matched hygiene scores of 0, grouped the matches by the LocalAuthorityName and aggregated by counting the values, and then sorted in descending order by the value counts.