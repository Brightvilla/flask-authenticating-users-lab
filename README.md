# Flask Authenticating Users

A full-stack blog application with session-based user authentication, built with a Flask REST API backend and a React frontend.

## Description

Users can log in by username, stay logged in across page refreshes via server-side sessions, and log out. Articles are fetched from the API and displayed in the browser.

## Installation

```bash
pipenv install && pipenv shell
npm install --prefix client
cd server
flask db upgrade
python seed.py
```

## Usage

Start the Flask server:

```bash
python app.py
```

Start the React frontend in a separate terminal:

```bash
npm start --prefix client
```

Visit `http://localhost:3000`. Log in with any seeded username to browse articles.

## API Endpoints

| Method | Route | Description |
|--------|-------|-------------|
| POST | `/login` | Log in by username; sets `session['user_id']` |
| DELETE | `/logout` | Clears `session['user_id']`; returns 204 |
| GET | `/check_session` | Returns current user (200) or 401 if not logged in |
| GET | `/articles` | Returns all articles |
| GET | `/articles/<id>` | Returns a single article (max 3 page views) |

## Running Tests

```bash
pytest
```

## Tech Stack

- Python / Flask / Flask-RESTful / Flask-Migrate / SQLAlchemy / Marshmallow
- React (frontend, no changes required)
- SQLite
