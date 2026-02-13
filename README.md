# Flask Blog Platform

A blog platform built with Flask, supporting user authentication with Flask-Login, session management, admin-controlled post management, and a relational database powered by SQLAlchemy and SQLite.

---

## Features

### User Authentication
- User registration and login  
- Password hashing using Werkzeug  
- Session handling with Flask-Login  
- Protected routes for logged-in users  

### Admin System
- The first registered user (ID = 1) is treated as the admin  
- The admin can:
  - Create new blog posts  
  - Edit existing posts  
  - Delete posts  
- Admin-only buttons (such as "New Post", "Edit", and delete options) are visible only to the admin user  

### Comment System
- Only logged-in users can leave comments  
- Comments are linked to specific posts  
- Each comment is associated with the user who posted it  

### Gravatar Integration
- Each user’s email is used to generate a Gravatar profile image  
- Gravatar provides a unique avatar image based on the user’s email  
- The profile image is automatically displayed next to each comment  

### Database
- Built using SQLAlchemy ORM  
- SQLite used for storage  
- Relational database structure between Users, Posts, and Comments  

---

## Tech Stack

- Flask  
- Flask-Login  
- Flask-WTF  
- Flask-Bootstrap5  
- SQLAlchemy  
- SQLite  
- Bootstrap  
- Jinja2  

---

## Project Structure

- `main.py` – Routes and application logic  
- `forms.py` – Form definitions  
- `templates/` – HTML templates  
- `static/` – CSS and assets  

---

## Screenshots

### Home Page

<img width="1902" height="882" alt="Home Page" src="https://github.com/user-attachments/assets/4e492c31-231a-4793-8002-3d9a9384db5d" />

### Admin View

<img width="1895" height="879" alt="Admin View" src="https://github.com/user-attachments/assets/0510c664-39e7-4775-a2ee-d222da94c519" />

### Gravatar Profile Picture in Comments

<img width="1893" height="462" alt="Gravatar Comment Section" src="https://github.com/user-attachments/assets/4482c1db-c93c-4cec-aa38-bf36d095387a" />

---
## How It Works

- The first registered user automatically becomes the admin (ID = 1).
- Only the admin can see and use post management buttons.
- Regular users can register, log in, and comment on posts.
- If a user is not logged in, they cannot leave comments.
- Passwords are stored securely in hashed format.
- All data is stored in a relational SQLite database.

---

## Run the Project

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
python main.py
```
