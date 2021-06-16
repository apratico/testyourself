# Keethings: Test yourself

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Development](#development) 
- [Release](#release)

## About <a name = "about"></a>
This docker-compose.yml file will start an instance of Postgres Database (https://www.postgresql.org/) and Keycloak Identity and Access Management (https://www.keycloak.org/).
You have to set-up Keycloak using the web interface at http://localhost:8080/auth/ accessing by following credentials admin/Pa55w0rd.
One time you are logged in KC admin console you have to create a new Realm with a client (access-type: confidential) and two users who have different roles ADMIN and USER.
Create a light ER (2 or 3 tables) on Postgres with users' information (populate the tables data by yourself).


## Getting Started <a name = "getting_started"></a>
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

### Prerequisites
docker and docker-compose is required.

### Installing

Please, you build the docker-compose file and run it on you local machine.
If you need you can change ports or other params in docker-compose.yml file.

```
docker-compose build
docker-compose up -d
```


## Development <a name = "development"></a>

Provide a spring-boot jar connected with Keycloak and that exposes at least the following endpoints (REST API) paying attention to roles:
```
method: /GET
authorized roles: ADMIN
path: /admin/users  
return:  list of users (data will be provided by Postgres using JPA/Hibernate module )
```

```
method: /GET
authorized roles: USER
path: /user/{id)}  
return:   user details by ID
```

## Release <a name = "release"></a>
Please, follow the pull requests flow to submit your work.