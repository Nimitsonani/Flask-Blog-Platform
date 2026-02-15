# Flask Blog Platform

This is a full-stack blog application built with Flask.

It includes user authentication, an admin-controlled content system, a comment feature, and a relational database structure using SQLAlchemy.

The goal of this project was to build a complete CRUD-based web application with proper authentication and role control — not just static blog pages.

---

## What This Project Does

Users can:

- Register and log in
- View blog posts
- Post comments (only if authenticated)

The first registered user automatically becomes the Admin.

The Admin can:

- Create new blog posts
- Edit existing posts
- Delete posts

Regular users cannot modify posts — they can only comment.

---

## How It Works

### Authentication

- Users register with email and password
- Passwords are hashed using Werkzeug
- Flask-Login manages sessions
- Protected routes ensure only authenticated users can access certain actions
- Admin-only routes are restricted at the backend level

The admin is determined simply by checking if `user.id == 1`.

---

### Blog Post Management

Posts are stored in a relational database.

Each post includes:

- Title
- Subtitle
- Body content
- Author relationship
- Date

CRUD operations are handled through Flask routes and SQLAlchemy models.

Admin-only buttons are conditionally rendered in the templates.

---

### Comment System

- Only logged-in users can post comments
- Each comment is linked to:
  - A specific blog post
  - The user who created it
- Relationships are handled using SQLAlchemy ORM

Non-authenticated users are redirected if they attempt to comment.

---

### Gravatar Integration

User profile images are generated automatically using Gravatar.

The system hashes the user's email and retrieves the corresponding avatar image.

This avoids storing image files locally while still displaying user profile pictures.

---

## Database Design

The application uses SQLite with SQLAlchemy ORM.

There are three main models:

- **User**
- **BlogPost**
- **Comment**

Relationships:

- One user → many posts
- One user → many comments
- One post → many comments

This structure ensures referential integrity and proper ownership mapping.

---

## Screenshots

### Home Page

<img width="1902" height="882" src="https://github.com/user-attachments/assets/4e492c31-231a-4793-8002-3d9a9384db5d" />

### Admin View

<img width="1895" height="879" src="https://github.com/user-attachments/assets/0510c664-39e7-4775-a2ee-d222da94c519" />

### Comment Section with Gravatar

<img width="1893" height="462" src="https://github.com/user-attachments/assets/4482c1db-c93c-4cec-aa38-bf36d095387a" />

---

## Tech Stack

- Flask
- Flask-Login
- Flask-WTF
- Flask-Bootstrap5
- SQLAlchemy
- SQLite
- Jinja2
- Bootstrap

---

## Project Structure

```
main.py        # Application routes and logic
forms.py       # Form definitions
templates/     # HTML templates
static/        # CSS and assets
```

---

## Running Locally

1. Install dependencies:

```
pip install -r requirements.txt
```

2. Create a `.env` file in the root directory:

```
SECRET_KEY=your_secret_key_here
DB_URI=sqlite:///posts.db
```

- `SECRET_KEY` is required for session security.
- `DB_URI` defines the database connection (default uses SQLite).

3. Run the application:

```
python main.py
```

The database will be created automatically if it does not exist.

---

## Notes

- Passwords are never stored in plain text.
- Admin control is enforced at the route level.
- SQLite is used for simplicity, but the structure can be switched to PostgreSQL or MySQL with minimal changes.
