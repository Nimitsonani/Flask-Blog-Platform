# Flask Blog Platform

A blog platform built with Flask, supporting authentication, role-based admin control, commenting, and relational database management using SQLAlchemy.

---

## Features

### User Authentication
- User registration and login
- Secure password hashing using Werkzeug
- Session management with Flask-Login
- Protected routes for authenticated users

### Admin System
- The first registered user (ID = 1) becomes the Admin
- Admin can:
  - Create new blog posts
  - Edit existing posts
  - Delete posts
- Admin-only buttons are conditionally displayed in the UI

### Comment System
- Only logged-in users can post comments
- Comments are linked to specific posts
- Each comment is associated with the user who posted it
- User profile image is displayed via Gravatar

### Gravatar Integration
- Email-based avatar generation
- Unique profile image automatically displayed next to comments

### Database
- SQLAlchemy ORM
- SQLite database
- Relational structure between Users, Posts, and Comments

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

## Environment Variables

This project uses environment variables for configuration.

Create a `.env` file in the root directory of the project with the following:

```
SECRET_KEY=your_secret_key_here
DB_URI=sqlite:///posts.db
```

### What to Add

- SECRET_KEY → A random secure string used for session security  
- DB_URI → Database connection string (default uses SQLite)

---

## Project Structure

```
main.py        # Application routes and logic
forms.py       # Form definitions
templates/     # HTML templates
static/        # CSS and assets
```

---

## Screenshots

### Home Page

<img width="1902" height="882" src="https://github.com/user-attachments/assets/4e492c31-231a-4793-8002-3d9a9384db5d" />

### Admin View

<img width="1895" height="879" src="https://github.com/user-attachments/assets/0510c664-39e7-4775-a2ee-d222da94c519" />

### Comment Section with Gravatar

<img width="1893" height="462" src="https://github.com/user-attachments/assets/4482c1db-c93c-4cec-aa38-bf36d095387a" />

---

## Setup Instructions


1. Install dependencies

```
pip install -r requirements.txt
```

2. Create `.env` file and add required variables (see above)

3. Run the application

```
python main.py
```

---

## How It Works

- The first registered user automatically becomes Admin.
- Admin can manage posts.
- Regular users can register, log in, and comment.
- Non-logged-in users cannot comment.
- Passwords are securely hashed.
- Data is stored in a relational SQLite database.
