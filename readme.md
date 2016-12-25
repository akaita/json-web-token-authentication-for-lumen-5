# Example of JSON web token authentication for Lumen 5 using tymon/jwt-auth

This repository was created as a support material for the instructional blog post http://www.akaita.com/post/json-web-token-authentication-for-lumen-5-tymon-jwt-auth 

Although I tried to keep this project as easy to understand as possible by itself, please refer to the blog post if you need any more explanation or have any suggestion.

## Features

  - Lumen 5.3
  - jwt-auth 1.0.0-beta.1
  - Authorization service using guards
  - User and Post model
  - Authorization policies for Post creation and update
  - Configured to use SQLite database and file-based caching (used for JWT tokens)
  - Ready to run

## API

### POST /auth/login

Authentication (form data or JSON):

  - *email*: user1@example.com, user2@example.com, user3@example.com)
  - *password*: 1234

Output (JSON):

  - JWT token

### GET /posts

Authentication:

  - *none*

Output (JSON):

  - List of all posts in database

### POST /posts

Authentication:

  - *JWT token*

Authorisation:

  - All authenticated users allowed

Input (JSON):

  - *subject*: string
  - *body*: string

Output (JSON):

  - Created post


### PUT /posts/:post_id

Authentication:

  - *JWT token*

Authorisation:

  - Only owner of the post

Input (JSON):

  - *subject*: string
  - *body*: string

Output (JSON):

  - Updated post