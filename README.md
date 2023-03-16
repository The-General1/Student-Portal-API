# Student-Portal-API

This is a Flask-Restx based API for managing student records.

Features

    Add new students
    Retrieve list of all students
    Retrieve details of a specific student
    Update an existing student
    Delete a student

Requirements

    Python 3.x
    Flask
    Flask-Restx
    SQLAlchemy
    SQLite (or any other database of your choice)

Setup

    Clone this repository to your local machine.
    Create a virtual environment and activate it:

      python3 -m venv venv
      source venv/bin/activate

    Install the required packages:

      pip install -r requirements.txt

    Set up the database:

      python manage.py db init
      python manage.py db migrate
      python manage.py db upgrade

    Start the server:

      python app.py

    The server will be available at http://localhost:5000.

Endpoints
GET /students

Retrieves a list of all students.

Response:

Status code: 200 OK
[
    {
        "id": 1,
        "name": "John Doe",
        "age": 25,
        "gender": "male",
        "email": "johndoe@example.com"
    },
    {
        "id": 2,
        "name": "Jane Smith",
        "age": 22,
        "gender": "female",
        "email": "janesmith@example.com"
    }
]

POST /students

Adds a new student to the database.

Request:

{
    "name": "John Doe",
    "age": 25,
    "gender": "male",
    "email": "johndoe@example.com"
}

Response:

Status code: 201 Created
{
    "id": 1,
    "name": "John Doe",
    "age": 25,
    "gender": "male",
    "email": "johndoe@example.com"
}

GET /students/{id}

Retrieves details of a specific student.

Response:

Status code: 200 OK
{
    "id": 1,
    "name": "John Doe",
    "age": 25,
    "gender": "male",
    "email": "johndoe@example.com"
}

PUT /students/{id}

Updates an existing student.

Request:

{
    "name": "John Doe",
    "age": 26,
    "gender": "male",
    "email": "johndoe@example.com"
}

Response:

Status code: 200 OK
{
    "id": 1,
    "name": "John Doe",
    "age": 26,
    "gender": "male",
    "email": "johndoe@example.com"
}

DELETE /students/{id}

Deletes a student.

Response:

Status code: 204 No Content
