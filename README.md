# onDemand backend

# Requirements

For building and running the application you need:

- [JDK 1.8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [Maven 3](https://maven.apache.org)
- [MYSQL] (https://dev.mysql.com/doc/mysql-installation-excerpt/5.7/en/)

# Running the application locally

The steps below will take you through cloning the repository and running the application on your local machine:

1. Clone the repository.

```bash
git clone git clone https://aya_kilani@bitbucket.org/aya_kilani/ondemand_backend.git
```
2. Create a new database on phpMyAdmin named "ondemand"
3. Open your copied repo folder and change ....to set the configurations for the database connection
    spring.datasource.url=jdbc:mysql://[HOST]:[PORT]/[BD_NAME]?serverTimezone=UTC
    spring.datasource.username=[MYSQL_USERNAME]
    spring.datasource.password=[MYSQL_PASSWORD]

4. To run the application ; you can use the [Spring Boot Maven plugin](https://docs.spring.io/spring-boot/docs/current/reference/html/build-tool-plugins-maven-plugin.html) like so:

```shell
mvn spring-boot:run --DskipTests

# Actuator
To monitor and manage your application

|  URL |  Method |
|----------|--------------|
|`http://localhost:8080/commands`  						| GET |
|`http://localhost:8080/newcommand`    (BODY : {"type": "delivery",
"taskId": "my-task-06",
"taskReference": "task-ref-007-d",
"date": "2019-03-13T12:34:56.012Z"
})         | POST   |
|`http://localhost:8080/commands/taskId/my-task-00`    	| GET |

## packages

- `Command` — to hold our entities;
- `CommandRepository` — to communicate with the database;
- `services` — to hold our business logic;
- `CommandController` — to listen to the client;

- `resources/` - Contains all the static resources, templates and property files.
- `resources/public` - Contains the dist on the front-end application.
- `resources/application.properties` - It contains application-wide properties. Spring reads the properties defined in this file to configure your application. You can define server’s default port, server’s context path, database URLs etc, in this file.

- `test/` - contains unit and integration tests

- `pom.xml` - contains all the project dependencies
