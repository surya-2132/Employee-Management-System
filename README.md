# Employee-Management-System


Step1 - create spring boot project

Step2 - create package structure(controller, entity, service, repository)

step3 - configure mysql database

step4 - create JPA entity 

step5 - create ResourceNotFoundException class

step6 - build Employee Rest API

step7 - build get all employees REST API

step8 - build get employee by id REST API

step9 - build update employee REST API

step10 - build delete employee REST API

created:

entity → employee and made as entity

repository → employeeRepository extended JPARepository

exception → create ResourceNotFoundException extends runtime and Response status(https status failed)

service → create employeeService interface and then ServiceIMPL 

then add methods (Save, add, update, delete) in Employee service interface and implement in employeeServiceImpl and do validation accordingly,

adding dependency injuction from repository,

3 main points here, 

- no need to @Transaction and @Repository (in employeeRepository interface) here because spring data JPA internally provides them,
- again no need of @Transaction in (employeeServiceImpl) class as well,
- no need of @Autowired, because only one constructor is there.

In getAllEmployee we used lambda expression instead of Optional<zEmployee> if/else

In get mapping we have used  @@GetMapping({”id”}) for dynamic purpose

Flow:

Control layer depends on service layer:

Employee Entity → Employee Repository →  Employee Service interface →  Employee Service Implementation class (save, update, delete things by using repository class as field(Composition) →  Employee Controller (Connects with EmployeeService interface by field) then create employee RESTAPI , and adding ResponseEntity return type in save, update, delete methods.
