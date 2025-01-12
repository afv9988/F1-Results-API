# F1 Results API 

![CC0 Public Domain](https://raw.githubusercontent.com/afv9988/F1-Results-API/main/src/main/resources/RB19.jpg)
![Coverage](.github/badges/jacoco.svg)
![Branch](.github/badges/branches.svg)
![Test](https://github.com/afv9988/F1-Results-API/actions/workflows/docker-push.yaml/badge.svg)
![Test](https://github.com/afv9988/F1-Results-API/actions/workflows/tests-embedded.yaml/badge.svg)

This is a simple API Code Example for consume F1 historical results 

Features:
- Spring Boot
- Swagger
- PostgreSQL
- Mockito
- Pagination
- JWT
- JaCoCo
- mvn Profiles
- GitHub Actions
- GitHub Secrets
- GitHub Badges
- Unit testing with embedded DB (h2 engine)
- Docker build and push to Docker Hub
- Docker compose files for API and DB Only
- Updated until Saudi Arabian Grand Prix *

# Steps to install

## 1.- Install all dependences
* Java 8
* Maven
* Docker
* (Optional) PostgreSQL Server
  * This is only necesary only if you want to create your DB from scratch

## 2.- Clone this repo
```
git clone https://github.com/afv9988/F1-Results-API.git
mvn clean install
```

## 3.- Execute DB instance 
* Init docker compose for only db (This can take a long)
```
docker-compose -f docker/run_only_db.yml up
```
* Or use my public db on your properties file
```
jdbc:postgresql://afdev.ddns.net:5432/f1_db
username=f1_user
passw=a912072
```
## 4.- Init Spring Boot
```
.\mvnw.cmd spring-boot:run
```

# Run all in docker
```
docker-compose -f docker/run_API_and_postgres.yml up
```

# Demo Swagger
## [Enter Here](http://afdev.ddns.net/swagger-ui.html#/results-controller)

For access the Demo you need to generate a token [here](http://afdev.ddns.net/token?password=PASSWORD&username=USER) or
```
curl -X GET "http://afdev.ddns.net/token?password=NEW_USER&username=NEW_PASSWORD" -H "accept: */*"
```
Then authenticate in Swager on JWT apiKey
For external use of token add -H "Authorization: YOUR-TOKEN-GENERATED"

## Resources
* [Import Datasets](https://hasura.io/docs/latest/schema/postgres/postgres-guides/import-data-from-csv/)

* [Spring Initializr](https://start.spring.io/#!type=maven-project&language=java&platformVersion=2.7.9&packaging=war&jvmVersion=1.8&groupId=com.apex&artifactId=demo&name=demo&description=F1%20API%20using%20GraphQL%20-%20Spring%20Boot%20-%20Mockito&packageName=com.apex.demo&dependencies=web,data-jpa,postgresql,graphql)

* [F1 Datasets](https://ergast.com/mrd/db/)

## Resources

* [Terms & Conditions](https://raw.githubusercontent.com/afv9988/F1-Results-API/main/src/main/resources/TNC.txt)
