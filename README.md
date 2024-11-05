# To-Do List REST API Flask

## Project Description

The To-Do List REST API is an application built with Flask that allows users to manage tasks in the form of a list. Users can create, view, update, and delete tasks. The application uses SQLite (or PostgreSQL, depending on the configuration) as the database for storing data.

## Features

- **Create Task**: Allows users to add new tasks to the list.
- **List Tasks**: Retrieves all tasks from the list.
- **Update Task**: Enables the modification of an existing task (e.g., changing the title or completion status).
- **Delete Task**: Allows users to remove a task from the list.

## REST API Endpoints

| Method | URL               | Description                       |
|--------|------------------|-----------------------------------|
| GET    | `/tasks`         | Retrieve all tasks                |
| POST   | `/tasks`         | Create a new task                 |
| PUT    | `/tasks/<task_id>` | Update a task by ID              |
| DELETE | `/tasks/<task_id>` | Delete a task by ID              |

## Installation

To install and run the application locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone <REPOSITORY_URL>
   cd <FOLDER_NAME>
   ```

2. **Create a virtual environment (optional but recommended):**
    ```bash
    python -m venv venv

    source venv/bin/activate
    # on Windows: venv\Scripts\activate
    ```

3. **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```
4. **Run the application:**
   ```bash
   python app.py
    ```

## Usage
The application is now accessible at http://127.0.0.1:5000/tasks. You can use tools like Postman or curl to test the API.

## Example Requests
Create Task:
```bash
curl -X POST http://127.0.0.1:5000/tasks -H "Content-Type: application/json" -d '{"title": "Task 1"}'
```
Get All Tasks:
```bash
curl -X GET http://127.0.0.1:5000/tasks
```
Update Task:
```bash
curl -X PUT http://127.0.0.1:5000/tasks/1 -H "Content-Type: application/json" -d '{"title": "Updated Task", "completed": true}'
```
Delete Task:
```bash
curl -X DELETE http://127.0.0.1:5000/tasks/1
```

## Database
The application uses SQLite by default. To use PostgreSQL, change the SQLALCHEMY_DATABASE_URI in the app.py file to the appropriate PostgreSQL database URI.

