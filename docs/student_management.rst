Overview

The Python RESTX Student Management API is a web application that allows users to perform CRUD (Create, Read, Update, Delete) operations on a student database. The API is built using the Flask-RESTX framework, and supports both JSON and XML formats for data exchange.
API Endpoints

GET /students

Retrieves a list of all students in the database.
Query Parameters

    limit (optional, default=50): The maximum number of results to return.
    offset (optional, default=0): The offset of the first result to return.

Response

    200 OK: Returns a list of student objects, where each object contains the following fields:
        id (int): The unique identifier of the student.
        name (str): The name of the student.
        email (str): The email address of the student.
        address (str): The address of the student.
        phone_number (str): The phone number of the student.

POST /students

Creates a new student in the database.
Request Body

    name (str, required): The name of the student.
    email (str, required): The email address of the student.
    address (str, required): The address of the student.
    phone_number (str, required): The phone number of the student.

Response

    201 Created: Returns the newly created student object, which contains the same fields as described in the GET /students endpoint.

GET /students/{id}

Retrieves a single student by their ID.
Path Parameters

    id (int, required): The unique identifier of the student.

Response

    200 OK: Returns the student object with the specified ID, which contains the same fields as described in the GET /students endpoint.
    404 Not Found: If no student with the specified ID exists in the database.

PUT /students/{id}

Updates an existing student in the database.
Path Parameters

    id (int, required): The unique identifier of the student.

Request Body

    name (str, optional): The new name of the student.
    email (str, optional): The new email address of the student.
    address (str, optional): The new address of the student.
    phone_number (str, optional): The new phone number of the student.

Response

    200 OK: Returns the updated student object, which contains the same fields as described in the GET /students endpoint.
    404 Not Found: If no student with the specified ID exists in the database.

DELETE /students/{id}

Deletes a single student by their ID.
Path Parameters

    id (int, required): The unique identifier of the student.

Response

    204 No Content: If the student is successfully deleted.
    404 Not Found: If no student with the specified ID exists in the database.

Error Handling

The API will return the following error messages if an error occurs:

    400 Bad Request: If the request is malformed or missing required parameters.
    404 Not Found: If the requested resource does not exist in the database.
    500 Internal Server Error: If an unexpected error occurs on the server.
