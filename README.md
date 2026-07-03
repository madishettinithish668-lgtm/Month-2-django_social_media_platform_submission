# Complete Social Media Platform

A submission-ready Django social media platform with user profiles, posts, comments, likes, follow system, notifications, REST API endpoints, responsive frontend, and documentation.

## Features

- User registration, login, logout, and authentication
- User profile page with bio, location, website, profile picture, and cover photo
- Create, view, like, comment, and delete posts
- Image upload support for posts and profiles
- Follow and unfollow users
- Followers and following counters
- Notification system for likes, comments, and follows
- WebSocket-ready notification consumer using Django Channels
- REST API using Django REST Framework
- Bootstrap-based responsive interface
- SQLite database for local development
- Environment variable support
- Organized Django app structure
- Basic unit tests
- Docker Compose starter file

## Project Structure

```text
social_media_platform_submission/
├── manage.py
├── requirements.txt
├── README.md
├── PROJECT_REPORT.md
├── SUBMISSION_CHECKLIST.md
├── docker-compose.yml
├── .env.example
├── social_platform/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
├── users/
│   ├── models.py
│   ├── forms.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── posts/
│   ├── models.py
│   ├── forms.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── friends/
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── notifications/
│   ├── models.py
│   ├── consumers.py
│   ├── routing.py
│   ├── utils.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── api/
│   ├── serializers.py
│   ├── views.py
│   └── urls.py
├── templates/
├── static/
├── media/
├── tests/
├── docs/
└── examples/
```

## Installation and Setup

### 1. Open the Project in VS Code

Open VS Code, then choose:

```text
File → Open Folder → django_social_media_platform_submission
```

### 2. Create a Virtual Environment

Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Mac/Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Create Database Tables

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Create Admin User

```bash
python manage.py createsuperuser
```

### 6. Run the Server

```bash
python manage.py runserver
```

Open this in your browser:

```text
http://127.0.0.1:8000/
```

Admin panel:

```text
http://127.0.0.1:8000/admin/
```

API root:

```text
http://127.0.0.1:8000/api/
```

## Main Pages

| Page | URL |
|---|---|
| Home feed | `/` |
| Register | `/accounts/register/` |
| Login | `/accounts/login/` |
| Logout | `/accounts/logout/` |
| Profile | `/accounts/profile/<username>/` |
| Edit profile | `/accounts/profile/edit/` |
| Notifications | `/notifications/` |
| API | `/api/` |

## REST API Endpoints

| Endpoint | Purpose |
|---|---|
| `/api/posts/` | List and create posts |
| `/api/posts/<id>/` | Retrieve, update, delete post |
| `/api/comments/` | List and create comments |
| `/api/profiles/` | View user profiles |
| `/api/my-profile/` | View logged-in user's profile |

## Running Tests

```bash
python manage.py test
```

## Sample Workflow

1. Register a new account.
2. Create a post from the home page.
3. Upload an image with the post if needed.
4. Like another user's post.
5. Add a comment.
6. Follow another user from their profile page.
7. Check the notifications page.
8. Open the API endpoints to view JSON data.

## Deployment Notes

For production, update these values in `.env`:

```text
DEBUG=False
SECRET_KEY=your-production-secret-key
ALLOWED_HOSTS=yourdomain.com,www.yourdomain.com
```

Then collect static files:

```bash
python manage.py collectstatic
```

Recommended deployment platforms: Render, Railway, PythonAnywhere, DigitalOcean, or VPS.

## Technologies Used

- Python
- Django
- Django REST Framework
- Django Channels
- Bootstrap
- SQLite
- HTML/CSS/JavaScript

## Author

Prepared as a complete Django web development project submission.
