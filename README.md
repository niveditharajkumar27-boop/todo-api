# Task API

A simple CRUD API for managing a to-do list, built with Python and FastAPI.
Data is stored in memory (a Python list) — it resets whenever the server restarts.

## How to run it

1. Clone this repo and open a terminal in the folder.
2. Create and activate a virtual environment:

python -m venv venv
venv\Scripts\activate

3. Install dependencies:

pip install fastapi uvicorn

4. Start the server:

uvicorn main:app --reload

5. Visit `http://127.0.0.1:8000` in your browser, or `http://127.0.0.1:8000/docs` for interactive Swagger UI.

## Endpoints

| Method | Path            | Description                    |
|--------|-----------------|--------------------------------|
| GET    | /               | API info                       |
| GET    | /health         | Health check                   |
| GET    | /tasks          | List all tasks                 |
| GET    | /tasks/{id}     | Get a single task by id        |
| POST   | /tasks          | Create a new task               |
| PUT    | /tasks/{id}     | Update a task's title/done      |
| DELETE | /tasks/{id}     | Delete a task                   |

## Example request

curl -i http://127.0.0.1:8000/tasks/1

Response:

HTTP/1.1 200 OK
content-type: application/json

{"id":1,"title":"Buy groceries and milk","done":true}

## Swagger UI

Screenshot below shows all endpoints available at `/docs`:

(screenshot added separately after pushing)

## Note on in-memory storage

Since tasks live only in a Python list, all data is lost when the server restarts — this is expected at this stage; a database comes in a later assignment.