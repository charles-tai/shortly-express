This application will allow users to login and store urls.

User interaction:

  Register:
    - create new account:
      - username
      - password

  Login:
    - enter username and password

  Store URL:
    - enter url

Client/Server:

  Registering User
    - create new account
      - check valid characters/password
      - check if user already exists:
        - if exists:
          - alert user
          - show link to login page
          - forgot password
        - if doesn't exist:
          - hash password
          - insert username/hashed password into user table

  Validating username and password
      - check valid characters
      - find user in database:
        - if doesn't exist:
            - alert user
            - show link to register page
        - if exists:
            - check if hashed password matches
            - set SESSION credentials to user
            - redirect to URL page

  Redirecting to Private URL storage
    - GET request from client to server for URLs:
      - Retrieve user's URLs from database using user's id from session

  Storing User URL:
    - check valid characters
    - POST request from client to server
      - Insert into database using user's id from session

  Generate shortened URL
    - ???
    - Can other people use their links?
    - Should shortened links be publicly available?

  Redirecting to URL
    - GET requests using shortened links uses URL table


Create Tables:

  1. User has many URLs
  2. URLs have one User

  Efficiency questions:
  - How to avoid duplication of URLs?

Technologies:

  Backbone - client-side:
    - Views:
      - links
    - Collection:
      - list of links
      - list of users
    - Models
      - user
      - links
      - click

    Backbone - updates models based on information from database

  Node - server-side
    - Handles logic concerning with database
    - Routes POST and GET requests

  ORM - database
    - used by Node to retrieve and insert information into database