Overview
This project is an Event Management System built in PHP that allows users to register, log in, and manage events. It demonstrates the use of object-oriented programming in PHP, MySQL database interactions, and secure password management.

Project Structure
classes/ - Contains class files for database interaction, user management, event management, and session management.
views/ - Contains header and footer files for the HTML structure.
config/ - Contains the configuration file for the database connection.
index.php - The home page of the application.
register.php - Handles user registration.
login.php - Handles user login.
logout.php - Handles user logout.
events.php - Interface to create, view, edit, and delete events.
style.css - Basic CSS for styling the application.
Requirements
XAMPP (or any other PHP and MySQL environment)
Web browser
Setup
Clone the repository or download the zip file.

Move the project folder to your web server directory (e.g., htdocs for XAMPP).

Start Apache and MySQL from the XAMPP control panel.

Create a database named event_management.
***************************************************
Import the SQL script to create necessary tables:
-- phpMyAdmin SQL Dump
-- version 5.2.1
-- https://www.phpmyadmin.net/
--
-- Host: localhost
-- Generation Time: Jun 07, 2024 at 10:42 AM
-- Server version: 10.4.28-MariaDB
-- PHP Version: 8.2.4

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `event_management`
--

-- --------------------------------------------------------

--
-- Table structure for table `events`
--

CREATE TABLE `events` (
  `id` int(11) NOT NULL,
  `user_id` int(11) NOT NULL,
  `name` varchar(100) NOT NULL,
  `description` text NOT NULL DEFAULT '',
  `event_date` datetime NOT NULL,
  `location` varchar(255) NOT NULL DEFAULT ''
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `events`
--

INSERT INTO `events` (`id`, `user_id`, `name`, `description`, `event_date`, `location`) VALUES
(12, 22, 'Project Time!', 'Deadline of the project is 19th of June.', '2024-06-19 23:59:00', 'Warsaw');

-- --------------------------------------------------------

--
-- Table structure for table `Users`
--

CREATE TABLE `Users` (
  `id` int(11) NOT NULL,
  `username` varchar(50) NOT NULL,
  `password` varchar(255) NOT NULL,
  `email` varchar(100) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `Users`
--

INSERT INTO `Users` (`id`, `username`, `password`, `email`) VALUES
(21, 'homework', '$2y$10$8MnSXUAi2v/Tt0pSuJNZbeEyDhqwtHtjtKtFAgdQURg3b.Qz1I41e', 'homework@gmail.com'),
(22, 'myhomeworklogin', '$2y$10$Rkj7hHalImDAsLvr4I9XkeYdUpSxDcvi8ZOGrRuQ/7LDNUZKz8WDa', 'myhomeworklogin@gmail.com');

--
-- Indexes for dumped tables
--

--
-- Indexes for table `events`
--
ALTER TABLE `events`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `Users`
--
ALTER TABLE `Users`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `username` (`username`),
  ADD UNIQUE KEY `email` (`email`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `events`
--
ALTER TABLE `events`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=13;

--
-- AUTO_INCREMENT for table `Users`
--
ALTER TABLE `Users`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=23;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
******************************************************************
Update the config/config.php file with your database credentials:
<?php
define('DB_HOST', 'localhost');
define('DB_USER', 'root');
define('DB_PASS', '');
define('DB_NAME', 'event_management');
?>
****************************************************************************
Open your web browser and navigate to http://localhost/event-management/.
*****************************************************************************
Usage
Register a new user.
Log in with your credentials.
Create, view, edit, and delete events.
