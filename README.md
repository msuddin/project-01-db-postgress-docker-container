# sample-postgress-docker

## Purpose

Question:
What is the purpose of this project

Answer:
* To create a postgres db inside a docker container
* To run a start-up script automatically once the container is running

## Instructions
From the root directory of the project, run the following command to create the postgres container and run the scripts:
```
docker-compose up -d
```
Take a look at the logs to confirm the scripts have run:
```
docker logs postgres
```
You should also be able to connect to the database:
```
psql -h localhost -U postgres
```
And should be able to run a simple query on it:
```
select * from account;
```

## Notes
* Scripts are mounted under volume
* Any mounted scripts are automatically executed in alphabetical order