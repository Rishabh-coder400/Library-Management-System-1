# Library-Management-System
A JavaFX-based Library Management System with SQLite
Java-project: Library Management System

A Java Swing-based Library Management System that stores and manages books and users in a MySQL database, featuring:

➕ Add, edit, and delete book records

🔍 Search books by title or author

✅ Issue and return books

📆 Track issue/return dates

💾 Persistent storage with MySQL



---

🛠 Prerequisites

System Requirements

Java JDK 8 or later

MySQL Server 5.7 or later

MySQL Connector/J (included in lib/)


Software Setup

Install Java:

Download from Oracle JDK

Verify installation:

java -version


Install MySQL:

Download from MySQL Community Server

Set root password during installation



---

🚀 Installation & Setup

Database Configuration

CREATE DATABASE library_db;
USE library_db;

CREATE TABLE books (
  id INT AUTO_INCREMENT PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  author VARCHAR(255),
  publisher VARCHAR(255),
  issue_date DATE,
  return_date DATE,
  is_issued BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE users (
  user_id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

Save the above SQL as setup.sql in the database/ folder and run it using MySQL Workbench or command line.


---

▶ Running the Application

Windows (CMD):

java -cp .;lib/mysql-connector-java-8.0.xx.jar src/Main

Linux / Mac (Bash):

java -cp .:lib/mysql-connector-java-8.0.xx.jar src/Main


---

🖥 Application Walkthrough

Main Interface:

Displays list of books in table format

Input fields for adding/editing books

Action buttons for issue/return/delete/search


Managing Books:

➕ Add new books with title, author, publisher

❌ Delete books

✅ Mark books as issued/returned

📅 Update issue/return dates

🔄 Refresh book list



---

🔧 Troubleshooting

Issue	Solution

Database connection failed	Ensure MySQL service is running and credentials are correct
ClassNotFoundException	Place MySQL Connector/J in lib/ and add to classpath
Date format errors	Use YYYY-MM-DD format for issue/return dates
Table not found	Run the setup.sql script to create required tables



---

📂 Project Structure

library-management-system/
├── src/
│   ├── Main.java                   # Entry point
│   ├── controllers/               # GUI controllers
│   │   └── BookController.java
│   ├── models/                    # Data models
│   │   ├── Book.java
│   │   └── User.java
│   └── database/                  # DB connection helper
│       └── DBConnector.java
├── lib/
│   └── mysql-connector-java-8.0.xx.jar  # JDBC Driver
├── database/
│   └── setup.sql                  # Database schema
└── README.md


---

📬 Contact

For support or questions:
email: rishabhkesae01@gmail.com
