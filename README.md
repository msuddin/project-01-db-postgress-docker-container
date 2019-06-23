# project-01-db-postgress-docker-container

## Purpose

Question:
What is the purpose of this project

Answer:
* To create a postgres db inside a docker container
* To run start-up scripts automatically once the container is running
* To serve as a db for project-01

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
You now need to switch to the correct db:
```
\c db
```
And should be able to run a simple query on it:
```
select * from account;
```

## Notes
* Scripts are mounted under volume
* Any mounted scripts are automatically executed in alphabetical order
* Scripts always run on postgres database by default.
* If a new database is created, each script must switch to the new database before it is executed (done by '\c <db_name>'')