# nosql-challenge
module 12

## Introduction
This challenge focus on the UK Food Standards Agency. This agency evaluates different establishments across the UK and gives them a food hygiene rating. The editors have contacted you to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles. This challenge is divided up into three major parts. 
##### Resources provided:
- establishments.json

# Part 1: Database and Jupyter Notebook Set up
For this part, you will use the *NoSQL_setup_starter.ipynb*
  1. Import the data provided in the establishments.json file from your terminal. The database will be named uk_food and the collection establishments. *Copy the text you used to import your data from your Terminal to a markdown cell in your notebook*
  2. Within your notebook, *import* the libraries you need: *PyMongo and Pretty Print (pprint)*
  3. Create an instance of the Mongo Client
  4. Confirm that you created the database and loaded the data properly:
       - List the databases you have in MongoDB. Confirm that *uk_food* is listed
       - List the collection(s) in the database to ensure that *establishments* is there
       - Find and display one document in the *establishments* collection using *find_one* and                 display with *pprint*
  5. Assign the establishments collection to a variable to prepare the collection for use

# Part 2: Update the Database
For this part, use the *NoSQL_setup_starter.ipynb*
The editors requested that a new hala restaurant in Greenwich be added to the database. Use the following information for the database:
     * { 
    "BusinessName":"Penang Flavours",
    "BusinessType":"Restaurant/Cafe/Canteen",
    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
} *

1. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the *BusinessTypeID* and *BusinessType* fields.
2. Update the new restaurant with the *BusinessTypeID* you found
3. Remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
4. Use *update_many* to convert *latitude* and *longitude* to decimal numbers & Use *update_many* to convert *RatingValue* to *integer* numbers

## Part 3: Exploratory Analysis
Continue on the *NoSQL_analysis_starter.ipynb*
*Note*: 
  - Use *count_documents* to display the number of documents contained in the result.
  - Display the first document in the results using *pprint*.
  - Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display       the first 10 rows.
Use the following questions to explore the database:
  - Which establishments have a hygiene score equal to 20?
  - Which establishments in London have a RatingValue greater than or equal to 4?
        - you will need to use *$regex* as part of your search.
  - What are the top 5 establishments with a *RatingValue* of 5, sorted by lowest hygiene score,            nearest to the new restaurant added, "Penang Flavours"?
  - How many establishments in each Local Authority area have a hygiene score of 0? *Sort the results from highest to lowest, and print out the top ten local authority areas*.
      - you will need to use the *aggregation* method to answer this.
