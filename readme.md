# Build

## Command Line
- First create database with psql (Postgres):
	```
	$ psql -U postgres
	```
	```
	postgres=#
	postgres=# create database parking;
	```
- Navigate to _**core**_ root folder module folder and run:
	```
	$ mvn compile && mvn install
	```
	This command will compile and install core lib inside your local .m2 repository.
	
- Then navigate to **_service_** root folder module and run:
	```
	$ mvn compile && mvn spring-boot:run
	```
	This will generate JPA Metadata files used in some Criteria Specification queries (type safe) and service going to start.	
- Any custom configuration like database password can be defined in _**application.properties**_ inside **_resources_** folder on module *service*. Eg.:
	```
	spring.datasource.driverClassName                           = org.postgresql.Driver
	spring.datasource.platform                                  = postgres
	spring.datasource.url                                       = jdbc:postgresql://localhost:5432/parking
	spring.datasource.username                                  = postgres
	spring.datasource.password                                  = postgres
	spring.jpa.properties.hibernate.default_schema              = public
	```
- Service will run on (set inside **_application.properties_**):
	```
	http://localhost:8080/parking/
	```
- Angular Web Application can be put together inside **_static_** folder on **_resources_** folder.