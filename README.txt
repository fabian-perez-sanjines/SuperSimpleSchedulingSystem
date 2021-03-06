
Container: 					Google App Engine 1.8.4
JAX-RS implementation: 		Jersey 1.1.5
JSON MAPPER:				JACKSON 2.3.2
Data-interchange format: 	JSON
Persistence: 				GAE Datastore with Objectify 5.1.13
Test: 						JUnit 4.10
Mocking: 					Mockito 1.9.0
Logging:  					GAE with java.util.logging.Logger
Maven to manage the project.


API
SERVICES
*Student
	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/student
	Returns all the students.
		[{
		    "id": 5096363633147904,
		    "lastname": "Amstrong",
		    "firstname": "Jack"
		}, {
		    "id": 5644406560391168,
		    "lastname": "Smith",
		    "firstname": "John"
		}, {
		    "id": 5654313976201216,
		    "lastname": "Amstrong",
		    "firstname": "Jack"
		}, {
		    "id": 5720147234914304,
		    "lastname": "Smith",
		    "firstname": "Mary"
		}]

	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/student?lastname=Smith
	Returns all the students that have lastname smith.
		[{
		    "id": 5644406560391168,
		    "lastname": "Smith",
		    "firstname": "John"
		}, {
		    "id": 5720147234914304,
		    "lastname": "Smith",
		    "firstname": "Mary"
		}]

	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/student/5644406560391168
	Returns the student that have id 5644406560391168.
		{
		    "id": 5644406560391168,
		    "lastname": "Smith",
		    "firstname": "John"
		}

	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/student/5096363633147904/classes	
	Returns all the classes for the student with id 5096363633147904
		[{
		    "code": 5629499534213120,
		    "title": "Compilers",
		    "description": "compile description"
		}, {
		    "code": 5649391675244544,
		    "title": "Algorithms",
		    "description": "algo description"
		}]

	POST http://1-dot-supersimpleschedulingsystem.appspot.com/api/student
	Content
		{
		    "lastname": "Amstrong",
		    "firstname": "Jac"
		}
	Returns the student with the generated ID
		{
		    "id":5096363633147904,
		    "lastname": "Amstrong",
		    "firstname": "Jac"
		}

	PUT http://1-dot-supersimpleschedulingsystem.appspot.com/api/student/5096363633147904
	Content
		{
		    "lastname": "Amstrong",
		    "firstname": "Jack"
		}
	Returns the updated student 
		{
		    "id":5096363633147904,
		    "lastname": "Amstrong",
		    "firstname": "Jack"
		}	

	DELETE http://1-dot-supersimpleschedulingsystem.appspot.com/api/student/5096363633147904
	Returns DELETED if the student with the id 5096363633147904 was deleted
		DELETED

	POST http://1-dot-supersimpleschedulingsystem.appspot.com/api/student/5654313976201216/register/5649391675244544	
	Register de user with the id 5654313976201216 to the class with the code 5649391675244544
		REGISTERED

*Class
	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/class
	Returns all the classes.
		[{
		    "code": 5629499534213120,
		    "title": "Compilers",
		    "description": "compile description"
		}, {
		    "code": 5649391675244544,
		    "title": "Algorithms",
		    "description": "algo description"
		}]

	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/class?title=Algorithms
	Returns all the classes that have title Algorithms.
		[{
		    "code": 5649391675244544,
		    "title": "Algorithms",
		    "description": "algo description"
		}]

	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/class/5649391675244544
	Returns the class that have id 5649391675244544.
		{
		    "code": 5649391675244544,
		    "title": "Algorithms",
		    "description": "algo description"
		}

	GET http://1-dot-supersimpleschedulingsystem.appspot.com/api/class/5649391675244544/students	
	Returns all the students for the class with id 5649391675244544
		[{
		    "id": 5096363633147904,
		    "lastname": "Amstrong",
		    "firstname": "Jack"
		}, {
		    "id": 5654313976201216,
		    "lastname": "Lawrence",
		    "firstname": "Peter"
		}]

	POST http://1-dot-supersimpleschedulingsystem.appspot.com/api/class
	Content
		{
		    "title": "Algorithms",
		    "description": "algo description"
		}
	Returns the class with the generated code
		{
		    "code": 5649391675244544,
		    "title": "Algorithms",
		    "description": "algo description"
		}

	PUT http://1-dot-supersimpleschedulingsystem.appspot.com/api/class/5649391675244544
	Content
		{
		    "title": "Algorithms",
		    "description": "algorithm description"
		}
	Returns the updated class
		{
		    "code": 5649391675244544,
		    "title": "Algorithms",
		    "description": "algorithm description"
		}	

	DELETE http://1-dot-supersimpleschedulingsystem.appspot.com/api/class/5649391675244544
	Returns DELETED if the student with the id 5649391675244544 was deleted
		DELETED


