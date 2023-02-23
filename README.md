# YaMDb API

## Description
YaMDb (Yet another Movie database) is a web service for creating reviews and rating movies, books and music.

This project represents the API of the YaMDb application. The API interacts with a PostgreSQL database and provides endpoints for getting and modifying data about users, titles, categories, genres, reviews and comments.

The project was developed using Django and Django REST Framework, and deployed using Docker on Yandex.Cloud.

## Stack
- Python
- Django
- Django REST Framework
- PostgreSQL
- Docker
- Yandex.Cloud

## API Endpoints
The following endpoints are available for working with the API:

### AUTH
- `/api/v1/auth/token/` - get a JWT token
- `/api/v1/auth/email/` - send an email with a confirmation code for registration
- `/api/v1/auth/token/refresh/` - refresh a JWT token

### USERS
- `/api/v1/users/` - get a list of all users (admin only)
- `/api/v1/users/{username}/` - get, update or delete a user (admin only)
- `/api/v1/users/me/` - get the current user's profile
- `/api/v1/users/activate/{email}/{activation_code}/` - activate a user account with the provided email and activation code
- `/api/v1/users/refresh_email/` - send an email with a new confirmation code to update the user's email address
- `/api/v1/users/set_password/` - set a new password for the current user

### TITLES
- `/api/v1/titles/` - get a list of all titles, create a new title (admin only)
- `/api/v1/titles/{title_id}/` - get, update or delete a title (admin only)
- `/api/v1/titles/{title_id}/reviews/` - get a list of all reviews for a title, create a new review
- `/api/v1/titles/{title_id}/reviews/{review_id}/` - get, update or delete a review
- `/api/v1/titles/{title_id}/reviews/{review_id}/comments/` - get a list of all comments for a review, create a new comment
- `/api/v1/titles/{title_id}/reviews/{review_id}/comments/{comment_id}/` - get, update or delete a comment

### CATEGORIES
- `/api/v1/categories/` - get a list of all categories (admin only)
- `/api/v1/categories/{slug}/` - get, update or delete a category (admin only)

### GENRES
- `/api/v1/genres/` - get a list of all genres (admin only)
- `/api/v1/genres/{slug}/` - get, update or delete a genre (admin only)

### COMMENTS
- `/api/v1/comments/` - get a list of all comments (admin only)
- `/api/v1/comments/{comment_id}/` - get, update or delete a comment (admin only)

1. Clone this repository to your local machine:
```bash
git clone https://github.com/PavelFil98/yamdb_final.git
```
2. Navigate to the project directory:
```bash
cd yamdb_final
```
3 . 
```bash
docker-compose build && docker-compose up
```
4. Create a superuser to access the Django admin panel:
```bash
docker-compose exec web python manage.py createsuperuser
```
5. Access the web application at http://localhost:8000/

# API Documentation:

1. The API documentation can be found at http://localhost:8000/redoc/. 
2 .You can also use the browsable API at http://localhost:8000/api/v1/.
