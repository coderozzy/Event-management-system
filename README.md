# Event Management System

## Overview

This project is an Event Management System built in PHP that allows users to register, log in, and manage events. It demonstrates the use of object-oriented programming in PHP, MySQL database interactions, and secure password management.

## Project Structure

- `classes/` - Contains class files for database interaction, user management, event management, and session management.
- `views/` - Contains header and footer files for the HTML structure.
- `config/` - Contains the configuration file for the database connection.
- `index.php` - The home page of the application.
- `register.php` - Handles user registration.
- `login.php` - Handles user login.
- `logout.php` - Handles user logout.
- `events.php` - Interface to create, view, edit, and delete events.
- `style.css` - Basic CSS for styling the application.

## Requirements

- XAMPP (or any other PHP and MySQL environment)
- Web browser

## Setup

1. Clone the repository or download the zip file.
2. Move the project folder to your web server directory (e.g., `htdocs` for XAMPP).
3. Start Apache and MySQL from the XAMPP control panel.
4. Create a database named `event_management`.
5. Import the SQL script to create necessary tables:
    - Download the SQL file from (https://drive.google.com/file/d/1M1lwCHTmhv_WLIkiis8u_6I6xMWZBQ7s/view?usp=drive_link).
    - Open phpMyAdmin and select the `event_management` database.
    - Click on the `Import` tab and choose the downloaded SQL file.
    - Click `Go` to import the database schema and data.
6. Update the `config/config.php` file with your database credentials:
    ```php
    <?php
    define('DB_HOST', 'localhost');
    define('DB_USER', 'root');
    define('DB_PASS', '');
    define('DB_NAME', 'event_management');
    ?>
    ```
7. Open your web browser and navigate to `http://localhost/event-management/`.

## Usage

- Register a new user.
- Log in with your credentials.
- Create, view, edit, and delete events.

---
