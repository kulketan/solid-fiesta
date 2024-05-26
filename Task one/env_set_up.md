Briefly describe the steps taken to configure your Hasura GraphQL Engine. 

I've used Hasura Cloud to set-up this environment. Explored two methods:

1. Using Chinook Music Library in Hasura Hub:  https://hasura.io/hub/schema-share-data-model-chinook/ 
This has everything set-up and ready to go except the permissions. 

2. Setting up the Project in Hasura and then connecting with Neon Postgres SQL. Here to load the database, Copied postgres.sql from Chinook's github page, used Neon's UI to load the .sql file. 

After setting-up initial environment, as per below technical details we need to set-up some additional permissions.

Assume the client will use the header x-hasura-artist-id for identifying the Artist.
Artists should not be allowed to access albums that do not belong to them.

For this two, I've used Row Select Permission feature of Hasura at table level granularity.
1. Added Artist as a Role in all the tables
2. Used Custom checks for artist_id equals x-hasura-artist-id in album and artist tables, which will prevent unauthorized access.

