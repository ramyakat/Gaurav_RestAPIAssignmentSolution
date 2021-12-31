# Gaurav_RestAPIAssignmentSolution
Graded Coding Assignment 6 (Spring Boot - RESTful APIs)

-----
APIs:
-----
	> CredentialsController
		This API gives all operations related to users and roles.
		
		Mapping = /sign-up
		Endpoints : {listRoles, newRole, newUser}
		
		listRoles : GET  : Lists all available roles 
		
		newRole   : POST : Adds new role to DB. We need to provide name of the role. The server checks if 
				   a role with given name exists. If not, then it adds to the DB.
						   
		newUser   : POST : Adds new user along with its roles. Takes 3 params: username, password and name 
				   of role. It checks if role exists, otherwise adds it. Then it adds the user to 
				   DB with encrypted password.
						   
		Note: There is no option to get list of all users as that would be undesirable for security aspect.
		
		
	> EmployeeController
		This API provides all the endpoints for the CRUD operations.
		
		Mapping = /employees
		Endpoints : {list, add, get, search, update, delete, sortlist}
		
		list  	 : GET    : Lists all employees in the DB 
		
		add 	 : POST   : Adds new employee to DB. Takes 3 params: firstName, lastName, email
		
		get 	 : GET    : Fetches an employee by given Id. Takes one param: id
		
		search 	 : GET    : Fetched an employee by given first name. Takes one param: firstname
		
		update 	 : POST   : Updates the given record in DB. Takes 4 params: id, firstName, lastName, email
		
		delete 	 : DELETE : Deletes the record with given Id. Takes 1 param: id 
		
		sortlist : GET    : Lists all employees in sorted order. Takes 1 param: direction (ASC/DESC)



------------
Permissions:
------------
	> The application has one admin credentials added to the DB at runtime using Commandline runner. 
	(username : admin1)
	
	> All endpoints of CredentialsController require ADMIN role to run.
	
	> In EmployeeController, add endpoint is accessible to ADMIN only. Other endpoints can be used by 
	both ADMIN and USER.
	

	
------------
Screenshots: 
------------
	> Please find the screenshots in 'Screenshot' folder. The names are self explanatory.
	> Screenshots numbered 1 to 17 show operations done by ADMIN role. So all operations are successful.
	> Screenshots 18 & 19 are for USER role (temp). As we can see in 19 we get respose 403 Forbidden.


