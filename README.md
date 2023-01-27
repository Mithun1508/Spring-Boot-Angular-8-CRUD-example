# What we are Building?

This is the application architecture we will build:

1) Spring Boot exports REST Apis using Spring Web MVC & interacts with embedded Database using Spring Data JPA.

2) Angular Client sends HTTP Requests and retrieve HTTP Responses using axios, shows data on the components. We also use Angular Router for navigating to pages.

3) We also take a look at client-server architecture for REST API using Spring Web MVC & Spring Data JPA, as well as Angular 8 project structure for building a front-end app to make HTTP requests and consume responses.

# Architecture Overview :

 ![angular-spring-boot-jpa-crud-example-architecture](https://user-images.githubusercontent.com/93249038/215018036-163637b5-c34f-442b-9af5-84f42a72a6e8.png)
 
 # Workflow:
 
– Spring Boot exports REST Apis using Spring Web MVC & interacts with H2 Database using Spring JPA

– Angular Client sends HTTP Requests and retrieve HTTP Responses using HttpClient Module, shows data on the components. We also use Angular Router for navigating to pages.

# Technology 

->Java 8

->Spring Boot 2.2.1 (with Spring Web MVC, Spring Data JPA)

->H2 Database

->Maven 3.6.1

#Implementation
# Create & Setup Spring Boot project
Use Spring web tool or your development tool (Spring Tool Suite, Eclipse, Intellij) to create a Spring Boot project.

# Then open pom.xml and add these dependencies:

<dependency>
 
	<groupId>org.springframework.boot</groupId>

	<artifactId>spring-boot-starter-data-jpa</artifactId>     
 
</dependency>

<dependency>
 
	<groupId>org.springframework.boot</groupId>
  
	<artifactId>spring-boot-starter-web</artifactId>
 
</dependency>

# We also need to add one more dependency for H2 database:

<dependency>  
	 
 <groupId>com.h2database</groupId> 
	
 <artifactId>h2</artifactId>
	
 <scope>runtime</scope>

</dependency>
Configure Spring Datasource, JPA, Hibernate
# Under src/main/resources folder, open application.properties and write these lines.

spring.datasource.url=jdbc:h2:mem:testdb

spring.datasource.driverClassName=org.h2.Driver

spring.datasource.username=sa

spring.datasource.password=
 
spring.jpa.show-sql=true

spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.H2Dialect


spring.jpa.hibernate.ddl-auto= update

spring.h2.console.enabled=true
# default path: h2-console
spring.h2.console.path=/h2-ui

spring.datasource.url: jdbc:h2:mem for In-memory database and jdbc:h2:file for disk-based database.

spring.datasource.username & spring.datasource.password properties are the same as your database installation.

Spring Boot uses Hibernate for JPA implementation, we configure H2Dialect for H2 Database

spring.jpa.hibernate.ddl-auto is used for database initialization. We set the value to update value so that a table will be created in the database automatically 

corresponding to defined data model. Any change to the model will also trigger an update to the table. For production, this property should be validate.

spring.h2.console.enabled=true tells the Spring to start H2 Database administration tool and you can access this tool on the browser: http://localhost:8080/h2-console.

spring.h2.console.path=/h2-ui is for H2 consol’’s url, so the default url http://localhost:8080/h2-console will change to http://localhost:8080/h2-ui.

Next have to do the following Steps

1) Define Data Model

2) Creating Repository Interface 

3)Create Spring Rest APIs Controller

# Angular 8 Front-end

->Technology

->Angular 8

->Angular HTTPClient

-> Angular Router


# Implementation
# Setup Angular 8 Project
Let’s open cmd and use Angular CLI to create a new Angular Project as following command:

# ng new Angular8ClientCrud
? Would you like to add Angular routing? Yes
? Which stylesheet format would you like to use? CSS
We also need to generate some Components and Services:

ng g s services/tutorial

ng g c components/add-tutorial
ng g c components/tutorial-details
ng g c components/tutorials-list
Now you can see that our project directory structure looks like this.

# Set up App Module
Open app.module.ts and import FormsModule, HttpClientModule:

...
import { FormsModule } from '@angular/forms';
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  declarations: [ ... ],
  imports: [
    ...
    FormsModule,
    HttpClientModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

1) Define Routes for Angular AppRoutingModule
2) Add Navbar and Router View to Angular CRUD App
3) Creating Data Service 
4) Creating Angular Components 

# How to Run the Application?
# Run Spring Boot application

1) mvn spring-boot:run

2)The Spring Boot Server will export API at port 8081.

# Run Angular Client

1) npm install

2)ng serve --port 8081
