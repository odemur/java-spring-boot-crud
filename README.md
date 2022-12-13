# CRUD App built on Java, Spring Boot and Thymeleaf
A simple CRUD App built on Java, Spring Boot, Thymeleaf and H2, PostgreSQL or MySQL Server database.

## Live demo on Heroku
https://odemur-spring-boot-crud.herokuapp.com

## Screenshot

![CRUD App built on Java, Spring Boot and Thymeleaf - List users](https://odemur.com.br/wp-content/uploads/2022/12/java-spring-boot-crud-list.png)
![CRUD App built on Java, Spring Boot and Thymeleaf - Add user](https://odemur.com.br/wp-content/uploads/2022/12/java-spring-boot-crud-add-user.png)

## Technologies
  * Language: **Java**
  * Framework: **Spring Boot**
  * Build Automation Tool: **Apache Maven**
  * Database [default]: **H2**
  * Supported Database: **PostgreSQL and MySQL** 

## Getting Started
Clone this project and running on you local machine. <br />
Only for development and testing purposes.

## Prerequisites
   * Java SDK 8
   * Java IDE
   * Apache Maven (only for Command Line)


## Running Application
Please follow carefully step by step instructions below:

### Using Docker for database

   * For PostgreSQL:

   ```bash
   docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=123 -d postgres
   ```
   ```bash
   docker exec -it postgres psql -U postgres 
   ```

   * For MySQL:
   ```bash
   docker run --name=mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123 -d mysql/mysql-server:5.7
   ```
   ```bash
   docker exec -it mysql mysql -uroot -p 
   ```

   Please create a database with the name: **test** 
   ```
   CREATE DATABASE test;
   ````
   
### Open Terminal and clone this project
 ```
 git clone https://github.com/odemur/java-spring-boot-crud.git
 ```

## Notes to use PostgreSQL

1. Add PostgreSQL dependencies on file **pom.xml**

```
		<dependency>
			<groupId>org.postgresql</groupId>
			<artifactId>postgresql</artifactId>
			<scope>runtime</scope>
		</dependency>
```

2. Edit the file **"application.properties"** on the directory "src/main/resorces". <br />

**Parameters for PostgreSQL**
```
#spring.datasource.url = jdbc:postgresql://localhost:5432/test
#spring.datasource.username	= postgres
#spring.datasource.password	= 123
#spring.jpa.hibernate.ddl-auto = update
#spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.PostgreSQLDialect
```

## Notes to use MySQL

1. Add MySQL dependencies on file **pom.xml**

```
		<dependency>
			<groupId>com.mysql</groupId>
			<artifactId>mysql-connector-j</artifactId>
			<scope>runtime</scope>
		</dependency>
```
2. Edit the file **"application.properties"** on the directory "src/main/resorces". <br />

**Parameters for MySQL**
```
spring.datasource.url = jdbc:mysql://localhost:3306/test
spring.datasource.username = root
spring.datasource.password = 123
spring.jpa.hibernate.ddl-auto = update
spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQL5Dialect
```

There is a file called **users.json** in the src/main/resources/json directory with sample data.

#### Running this application with IDE:
   - Open this project folder with any Java IDE (IntelliJ IDEA, Eclipse, etc..)
   - Run the application using the IDE > Run Option
   
#### Running this application with Command Line:
   - Open Terminal
   - Change directory to the base project (spring-boot-rest-api)
   - Run the command
 ```
   mvn java-spring-boot-crud:run
 ```
 
 Open http://localhost:8080/ in your browser and enjoy!
 
 
