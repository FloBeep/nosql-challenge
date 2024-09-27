# nosql-challenge

### Background

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine,  *Eat Safe, Love* , to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

##### Part 1: Database and Jupyter Notebook Set Up

We used the NoSQL_setup_starter.ipynb file to complete this challenge. 

First, we imported the data from establishments.json into MongoDB via the Terminal, creating a database named uk_food and a collection called establishments. We included the import command in a markdown cell. In the notebook, we imported the necessary libraries: PyMongo and pprint. 

Then we created a Mongo Client instance, and then verified the data import by listing the databases to confirm uk_food is present, listing its collections to verify establishments, and using find_one to display a document with pprint. 

Finally, we assigned the establishments collection to a variable for future operations.

##### Part 2: Update the Database

We used [NoSQL_setup_starter.ipynb](https://github.com/FloBeep/nosql-challenge/blob/main/NoSQL_setup_starter.ipynb) for this section of the challenge. The magazine editors had requested modifications to the database before we could perform any queries or analysis. 

First, we added a new halal restaurant in Greenwich that hadn’t been rated yet, after finding the BusinessTypeID for "Restaurant/Cafe/Canteen" and updating the restaurant with this information. Next, we identified the number of documents related to Dover and removed all establishments within the Dover Local Authority. 

Finally, we corrected data types in the database by using update_many to convert latitude and longitude to decimal numbers, and the RatingValue to integers.

##### Part 3: Exploratory Analysis

We used [NoSQL_analysis_starter.ipynb](https://github.com/FloBeep/nosql-challenge/blob/main/NoSQL_analysis_starter.ipynb) to address specific questions from Eat Safe, Love, aimed at identifying locations they wish to visit or avoid. We noted that RatingValue refers to ratings from 1 to 5, but some non-numeric values, like 'Pass,' were coerced to nulls before converting ratings to integers. We also considered that higher scores in Hygiene, Structural, and ConfidenceInManagement indicate worse conditions. 

To answer the questions, we used count_documents to find document counts, displayed the first result with pprint, and converted results to a Pandas DataFrame for further analysis. We investigated establishments with a hygiene score of 20, those in London with a RatingValue of 4 or higher, the top 5 establishments near "Penang Flavours" with a RatingValue of 5 sorted by hygiene score, and counted establishments with a hygiene score of 0 in each Local Authority area, sorted from highest to lowest.

The result of our analysis showed that the Thanet Local Authority have the highest number of 0 hygiene scores.
