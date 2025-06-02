# java-database-capstone

# Data flow
- User Interface Layer
  - Users can access the application through REST API Clients and thymeleaf-based web dashboards(AdminDashboard and DoctorDashboard)
- Controller Layer
  - When user interacts with the application, the request is routed to a backend controller based on the URL path and the HTTP method
  - Requests for server-rendered views are handled by Thymeleaf controllers whilst requests from API consumers are handled by Rest Controllers
- Service Layer
  - All controller logic are mapped to the service layer where business rules and validations are applied.
- Repository Layer
  - Service layer communicates with the Repository to perform data access operations.
  - MySQL Repo use Spring Data JPA, and MongoDB repo uses Spring Data MongoDB to manage document-based records like prescriptions
- Database Access
  - MySQL stores all core entities such as users, roles, and appointments
  - MongoDB stores flexible and nested data structures such as prescriptions
- Model Binding
  - Once data is retrieved from the database, it is mapped into the Java model classes that the application can work with
- Application models in use
  - In MVC flows, models are passed from controller to thymeleaf templates where they are rendered as dynamic HTML for browser
  - In Rest flows, same models are serialized into JSON and sent back to the client as http response
 
