# Project Report: Complete Social Media Platform

## 1. Project Overview

The Complete Social Media Platform is a Django-based web application designed to demonstrate full-stack web development using Django's MTV architecture. The platform allows users to register, create profiles, publish posts, like content, comment on posts, follow other users, receive notifications, and access data through REST API endpoints.

The project focuses on clean architecture, reusable apps, database relationships, secure authentication, file uploads, and a responsive user interface.

## 2. Objectives

- Build a functional social media web application using Django.
- Implement authentication and authorization using Django's built-in user system.
- Create models for profiles, posts, comments, follows, and notifications.
- Use Django ORM for database operations.
- Provide a responsive frontend using Bootstrap.
- Implement REST API endpoints using Django REST Framework.
- Add real-time-ready notification support using Django Channels.
- Organize code into reusable apps.
- Provide clear documentation and setup instructions.

## 3. System Architecture

The project follows Django's MTV architecture:

- **Model:** Defines database structure and relationships.
- **Template:** Handles the user interface.
- **View:** Handles business logic and request/response flow.

### Main Apps

| App | Responsibility |
|---|---|
| `users` | Registration, profile management, user details |
| `posts` | Posts, likes, comments, feed |
| `friends` | Follow and unfollow functionality |
| `notifications` | Notification creation and listing |
| `api` | REST API endpoints |
| `social_platform` | Project settings and main URL routing |

## 4. Database Design

### UserProfile

Extends Django's built-in User model using a one-to-one relationship.

Fields:

- user
- bio
- profile_picture
- cover_photo
- location
- website
- joined_date

### Post

Stores user-created posts.

Fields:

- author
- content
- image
- created_at
- updated_at
- likes

### Comment

Stores comments for posts.

Fields:

- post
- author
- content
- created_at

### Follow

Stores follower and following relationships.

Fields:

- follower
- following
- created_at

### Notification

Stores user notifications.

Fields:

- recipient
- sender
- verb
- target_url
- unread
- created_at

## 5. Key Features

### User Authentication

The platform supports registration, login, and logout using Django's secure authentication system.

### Profile System

Each user automatically receives a profile after registration. Users can edit their bio, location, website, and images.

### Post Management

Users can create text posts and upload images. Posts appear in the home feed ordered by newest first.

### Likes and Comments

Users can like and unlike posts. Users can add comments to posts. These actions generate notifications.

### Follow System

Users can follow or unfollow other users. Follower and following counts are displayed on profile pages.

### Notifications

Notifications are created for likes, comments, and follows. A Channels consumer is included to support WebSocket-based real-time notification delivery.

### REST API

The project includes API endpoints for posts, comments, and profiles using Django REST Framework.

## 6. Security Considerations

- Passwords are handled by Django's built-in authentication system.
- CSRF protection is enabled for forms.
- User actions require login using `login_required`.
- Users can delete only their own posts.
- File uploads are handled through Django media settings.
- Sensitive configuration is separated using environment variables.

## 7. Testing

Basic tests are included for:

- Profile creation
- Post creation
- Like count
- Comment creation
- Follow relationship creation

Run tests using:

```bash
python manage.py test
```

## 8. Future Enhancements

- Real-time chat system
- Groups and community pages
- Advanced search
- Content moderation dashboard
- Hashtags and trending topics
- Infinite scrolling feed
- Cloud storage for uploaded media
- Production database such as PostgreSQL

## 9. Conclusion

This project demonstrates a complete Django social media platform with practical full-stack features. It includes authentication, database relationships, file uploads, user interactions, notifications, API support, and clean documentation. The structure is suitable for GitHub submission, portfolio presentation, and further development.
