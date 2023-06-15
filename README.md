# nosql-challenge
Mongo is leveraged to create, update, and analyze a database of UK dining options. Parts 1 and 2 can be found in the NoSQL_setup file and Part 3 can be found in the NOSQL_analysis file. Original dataset titled establishments.json is located in Resources folder.

### Tools Used
* Mongo DB
* Regular Expressions
* Python
* Pandas

## Part 1: Database and Jupyter Notebook Set-Up
1. At the beginning of the NoSQL_setup file, you will find the mongoimport command text I used to import establishments.json. I converted the cell to Markdown to preserve a record of the code while avoiding unecessary recreating/dropping of the database. 
2. The database and collection used for the rest of the challenge are named uk_food and establishments, respectively. They are both assigned to variables of the same name.
3.  I used find_one() and pprint to display one document - resaurant called The Pavilion - in the establishments collection to confirm that documents were properly uploaded. 

## Part 2: Updating the Database
1. I created a dictionary for Penang Flavours and inserted it into the establishments collection. I converted the cells containing these actions to Markdown to avoid duplicating Penang Flavours entries. 
2. I queried "'BusinessType': 'Restaurant/Cafe/Canteen'" to find its 'BusinessTypeID' is 1. Penang Flavours was missing the Business Type ID, so I updated the document with the value 1.
3. Number of Documents with LocalAuthorityName as Dover:994
4. Total Number of Documents Before Deleting Dover: 39780, Total Number of Documents After Deleting Dover: 38786.
5. I used update_many to change geocode.latitude and geocode.longitude fields to Doubles and RatingValue field to Integer.
6. I used find_one to confirm the field data types had been properly changed.

## Part 3: Exploratory Analysis
For this section, I explored the database using pymongo querying, regular expressions, and aggregation pipeline building. All results were loaded into Pandas Dataframes. 
1. 41 establishments have a hygiene score of 20.
2. 33 establishments have London as their Local Authority and RatingValue of greater than or equal to 4.
3. The top five establishments with a RatingValue of 5, sorted by lowest hygiene score, geographically nearest to Penang Flavours, are: The Old Mill, Best Halal Meat Limited, Conway Primary School, Chick Chicken, and Plumstead Manor Nursery.
4. The "answer" to this question is a bit long to summarize here. But in terms of process, I created a $match query operator to find establishments with hygiene scores of 0, a $group query operator to group those matches by Local Authority, and a $sort operator to arrange the groups from most documents to least. I put these operators together into a pipeline and ran it through the aggregate method to save to a list called "results." The list contained 55 documents.
