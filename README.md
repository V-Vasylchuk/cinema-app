# ![logo.png](img%2Flogo.png) Cinema-Service ![logo.png](img%2Flogo.png)
This is a web application project is an imitation of the operation a cinema. 
Service based on Hibernate and Spring frameworks using general REST principles.

# ![gears_logo.png](img%2Fgears_logo.png) Features ![gears_logo.png](img%2Fgears_logo.png)
###### Before use the system, users need to log in:
* register and log in as a user/administrator;
###### Registered as USER role:
* find movies and cinema halls
* find available movie sessions
* create shopping cart
* add tickets to shopping cart
* view shopping cart
* make an order
* view order history
###### Registered as ADMIN role:
* create and find movies and cinema halls
* create and find available movie sessions
* find user by email
# ![start_logo.png](img%2Fstart_logo.png) Getting Started 
* Clone repository from GitHub
* Create an empty database
* In `db.properties` replace the values of the properties with the appropriate values for your database setup
* Build the project using Maven: `mvn clean install`
* Configure Apache Tomcat Artifact: war-exploded artifact, Application context: "/";
* When the program starts, two users are added to the database, you can log in both:
1. **ADMIN**: `username`: admin@i.ua, `password`: admin123
2. **USER**: `username`: user@i.ua, `password`: user123 
3. Use `Postman` to send some http requests;
4. Also, you can use my Postman request collection: [LINK](https://www.postman.com/vasylchuk/workspace/cinema-service/collection/3329996-3cf6002f-e5b9-42c5-93c6-dab9bca42c02?action=share&creator=3329996)
5. Video tutorial how to work with Postman and the collection of requests that I created. [VIDEO](https://komododecks.com/recordings/oGdIveZwNmb3kZqf0vH2)

# ![layer_logo.png](img%2Flayer_logo.png)Structure description:
* `config`: classes for configuration of application operation
* `controller`: controllers for endpoints:

  * AuthenticationController - `POST` `/register` - register new user
  * CinemaHallController - `POST` `/cinema-halls` - add cinema-hall
  * CinemaHallController - `GET` `/cinema-halls` - get all cinema-halls
  * MovieController - `POST` `/movies` - add movie
  * MovieController - `GET` `/movies` - get all movies
  * MovieSessionController - `POST` `/movie-sessions` - add movie-session
  * MovieSessionController - `GET` `/movie-sessions/available` - get available movie-session
  * MovieSessionController - `PUT` `/movie-sessions/{id}` - update movie-session
  * MovieSessionController - `DELETE` `/movie-sessions/{id}` - delete movie-session
  * UserController - `GET` `/users/by-email` - get user by username
  * ShoppingCartController - `GET` `/shopping-carts/by-user` - get all movie-session in current user shopping cart
  * ShoppingCartController - `PUT` `/shopping-carts/movie-sessions` - add movie-session to current user shopping cart
  * OrderController - `POST` `/orders/complete` - complete user order
  * OrderController - `GET` `/orders` - show all order history for current user

* `dao`: Data Access Objects are responsible for correct CRUD operations with DB;
* `dto`: Data Transfer Objects are representing communication objects for customer requests and responses;
* `exception`: custom exception;
* `lib`: contains custom annotations and logic for email and password validation;
* `model`: Plain Old Java Objects are defining operational data (objects) type and structure;
* `service`: provides business logic, includes `mappers` for dto;
* `util`: utility class used to determine DateTime pattern;
* `resources`: contains configuration file with MySQL and Hibernate params.

# ![DB_logo.png](img%2FDB_logo.png) Database structure:
![DB_structure.png](img%2FDB_structure.png)

# Used technologies: 
* Java `v.17.0.5`
* Maven `v.3.8.7`
* Spring `v.5.3.20`
* Spring Security `5.6.10`
* Hibernate `v.5.6.14.Final`
* Hibernate Validator `6.1.6.Final`
* MySql `v.8.0.22`
* Java Servlets `v.4.0.1`
* Jackson core `v.2.14.1`
* Javax annotation `v.1.3.2`
* Tomcat `v.9.0.50`

# Author
_[Vasyl Vasylchuk](https://www.linkedin.com/in/vasyl-vasylchuk-632303273/)_