# nosql-challenge
Mongo is leveraged to create, update, and analyze a database of UK dining options. Parts 1 and 2 can be found in the NoSQL_setup file and Part 3 can be found in the NOSQL_analysis file. Original dataset titled establishments.json is located in Resources folder.

## Part 1: Database and Jupyter Notebook Set-Up
1. At the beginning of the NoSQL_setup file, you will find the mongoimport command text I used to import establishments.json. I converted the cell to Markdown to preserve a record of the code while avoiding unecessary recreating/dropping of the database. 
2. The database and collection used for the rest of the challenge are named uk_food and establishments, respectively. They are both assigned to variables of the same name.
3.  I used find_one() and pprint to display one document - resaurant called The Pavilion - in the establishments collection to confirm that documents were properly uploaded. 

## Part 2: Updating the Database
1. I created a dictionary for Penang Flavours and inserted it into the establishments collection. I converted the cells containing these actions to Markdown to avoid duplicating Penang Flavours entries. 
2. I queried "'BusinessType': 'Restaurant/Cafe/Canteen'" to find its 'BusinessTypeID' is 1. Penang Flavours was missing the Business Type ID, so I updated the document with the value 1.
Number of Documents with LocalAuthorityName as Dover:994 *****count docs before and after

## Part 3: Exploratory Analysis
1. 41 restaurants have a hygiene score of 20.
2. ******need to use regex
3. The top five establishments with a RatingValue of 5, sorted by lowest hygiene score, geographically nearest to Penang Flavours, are: The Old Mill, Best Halal Meat Limited, Conway Primary School, Chick Chicken, and Plumstead Manor Nursery.
4. 
