Task Management System

This Django-based task management system allows users to register, authenticate, and manage tasks. It supports CRUD operations for tasks and uses JWT authentication for secure access.

Project Setup
Prerequisites
Python: Ensure Python is installed. You can download it from python.org.

Virtual Environment: Using a virtual environment is recommended to manage dependencies.

Steps to Set Up the Project
Clone the Repository:

bash
Copy code
git clone <repository-url>
cd task_management
Create and Activate a Virtual Environment:

bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install Required Packages:
Make sure you're in the virtual environment and run:

bash
Copy code
pip install -r requirements.txt
Configure PostgreSQL Database:

Make sure PostgreSQL is installed and running.
Create a database named task_db and a user with appropriate permissions (e.g., postgres with password password).
Update Database Settings:
In task_management/settings.py, configure your PostgreSQL database settings:

python
Copy code
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'task_db',
        'USER': 'postgres',
        'PASSWORD': 'password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
Apply Migrations:

bash
Copy code
python manage.py migrate
Run the Development Server:

bash
Copy code
python manage.py runserver
You can now access the application at http://127.0.0.1:8000/.

Project Structure
markdown
Copy code
task_management/
├── manage.py
├── requirements.txt
├── task_management/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
└── tasks/
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── models.py
    ├── serializers.py
    ├── urls.py
    ├── views.py
    └── tests.py
Features
User Registration and Authentication:

Register: /api/register/
Login: /api/login/
JWT Authentication: Secured API endpoints
Task Management:

List Tasks: /api/tasks/
Create Task: /api/tasks/
Retrieve Task: /api/tasks/<id>/
Update Task: /api/tasks/<id>/
Delete Task: /api/tasks/<id>/
API Endpoints
User Registration
URL: /api/register/
Method: POST
Body:
json
Copy code
{
  "username": "your_username",
  "password": "your_password"
}
User Login
URL: /api/login/
Method: POST
Body:
json
Copy code
{
  "username": "your_username",
  "password": "your_password"
}
Response:
json
Copy code
{
  "refresh": "refresh_token",
  "access": "access_token"
}
Task Management
List Tasks:

URL: /api/tasks/
Method: GET
Create Task:

URL: /api/tasks/
Method: POST
Body:
json
Copy code
{
  "title": "Task title",
  "description": "Task description",
  "status": "Todo",
  "priority": "High",
  "due_date": "2024-12-31"
}
Retrieve Task:

URL: /api/tasks/<id>/
Method: GET
Update Task:

URL: /api/tasks/<id>/
Method: PUT
Body:
json
Copy code
{
  "title": "Updated task title",
  "description": "Updated task description",
  "status": "In Progress",
  "priority": "Medium",
  "due_date": "2024-12-31"
}
Delete Task:

URL: /api/tasks/<id>/
Method: DELETE
Requirements
Django: >=5.1,<6.0
djangorestframework
djangorestframework-simplejwt
psycopg2-binary
Running Tests
Install Test Dependencies:

bash
Copy code
pip install pytest
Run Tests:

bash
Copy code
pytest


License
This project is licensed under the MIT License.

Contributing
Feel free to fork the repository and make improvements. Submit pull requests for any significant changes.
