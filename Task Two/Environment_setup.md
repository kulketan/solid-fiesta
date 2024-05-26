Followed Below Steps to set-up the environment:
1. Installed Docker, Hasura CLI
2. extracted zip file content
3. executed `docker compose up -d` to start the environment. Got the Below Error: 
    Error: graphql-engine Error manifest for hasura/graphql-engine:v2.48.2-pro not found: manifes...                       3.8s
Error response from daemon: manifest for hasura/graphql-engine:v2.48.2-pro not found: manifest unknown: manifest unknown 

hasura/graphql-engine:v2.48.2-pro does not exist which is used in the docker-compose.yaml file. Replaced it with the latest graphql-engine from https://hub.docker.com/r/hasura/graphql-engine/tags 

Re-Executed the docker compose command however localhost:8080 wasn't reachable.
Updated the ports to 8080:8080 in the docker file.
Correct few Environment Variables as well.
set up the password for HASURA_GRAPHQL_ADMIN_SECRET so that we can authenticate. 

set-up Chinook Database from Link: https://github.com/lerocha/chinook-database/blob/master/ChinookDatabase/DataSources/Chinook_PostgreSql.sql

Now we need to use the metadata provided in the .zip file. Noticed that UI only allows import in the .json format but .zip file contains directory structure. 
Using hasura CLI is easiest way to apply metadata in this scenario using command `hasura metadata apply`
After this I noticed couple of Metadata is inconsistent warnings due to different table name (ex. artists vs artist in the chinook db) in the metadata and id names in the permission section. Updated the yaml files to reflect changes according to the Chinook database.

Here is the PR of changes made in the metadata: 
