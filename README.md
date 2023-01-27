# What we are Building?

This is the application architecture we will build:

1) Spring Boot exports REST Apis using Spring Web MVC & interacts with embedded Database using Spring Data JPA.

2) Angular Client sends HTTP Requests and retrieve HTTP Responses using axios, shows data on the components. We also use Angular Router for navigating to pages.

# Architecture Overview :

 ![angular-spring-boot-jpa-crud-example-architecture](https://user-images.githubusercontent.com/93249038/215018036-163637b5-c34f-442b-9af5-84f42a72a6e8.png)


# How to Run the Application?
# Run Spring Boot application

1) mvn spring-boot:run

2)The Spring Boot Server will export API at port 8081.

# Run Angular Client

1) npm install

2)ng serve --port 8081
