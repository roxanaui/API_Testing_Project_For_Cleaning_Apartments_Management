# API testing project for **Cleaning Apartments Management**

The scope of this project is to use API knowledge gained through the Software Testing course and apply them in practice, using a prototype application.

Application under test: **Cleaning Apartments Management**

Tool used: Postman

Collection link: **https://66ba11cbfa763ff550fab0e9.mockapi.io/api/apartamente**


## Tests performed

**1. List that initially there are no apartments**

HTTP method for request: **GET**

Request description: **We validate that there are no apartments listed in our database**

Test types / techniques used: **Positive testing**

Response status code: **200 OK**

Below you can find a picture of the API request and the JavaScript tests from Postman:

![GET](/rrGET_request.png)


**2. Add an apartment**

HTTP method for request: **POST**

Request description: **We create / add a new object - apartment - in our database**

Test types / techniques used: **Positive testing**

Response status code: **201 Created**

Below you can find a picture of the API request from Postman:

![POST](/rrPOST_request_body.png)

JavaScript Tests:

![POST](/rrPOST_request_tests.png)


**3. Modifying the name of the apartment's owner**

HTTP method for request: **PATCH**

Request description: **We modify only the name of the apartment's owner**

Test types / techniques used: **Positive testing**

Response status code: **200 OK**

Below you can find a picture of the API request from Postman:

![PATCH](/rrPATCH_request_body.png)

JavaScript Tests:

![PATCH](/rrPATCH_request_tests.png)


**4. Deleting an apartment**

HTTP method for request: **DELETE**

Request description: **We delete the apartment marked with id: "1"**

Test types / techniques used:  - 

Response status code: **200 OK**

Below you can find a picture of the API request from Postman:

![DELETE](/rrDELETE_request.png)


## Execution report for the created API collection

Below you can find the execution report that was generated through the Postman collection runner. 

![COLLECTION_RUNNER](/rrCOLLECTION_RUNNER.png)

![RUN_SUMMARY](/rrRUN_SUMMARY.png)


## Defects found

The following issues were identified while running the Postman tests:

**1. Assigning unregistered apartment to an employee should not be possible**

**Preconditions:** the endpoint for the apartments must have at least one apartment with id 1;

**Reproduction steps:** an employee must be added and must have allocated apartments: one apartment with id 1 and another apartment with a missing id ( eq: 1234567 );

**Expected result:** response code must be error code 404 and the apartment is not added;

**Actual result:** response code is error code 404 and the apartment is added.


**2. Adding employees without allocated apartment should not be possible**

**Preconditions:** -;

**Reproduction steps:** an employee must be added and must not have any allocated apartment;

**Expected result:** response code must be an error client code (4xx);

**Actual result:** response code is 201 and the employee is added without having had allocated an apartment ( we validate using GET request for employees and checking the list we received ).

Below you can find a picture of the API request from Postman:

![employee_etc](/rremployee_with_allocated_apt_none.png)


## Conclusions

Given that the project under test is a prototype, the found bugs are expected and fixing them will help improve the project. The current tests will help maintain stability while increasing the feature scope.

