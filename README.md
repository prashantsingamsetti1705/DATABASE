Sure, I can help you format this content for a GitHub README file and correct any mistakes. Here's a cleaned-up version with improved formatting and corrections:

```markdown
# Database Operations

## Show Databases
```sql
SHOW DATABASES;
```

## Create Database
```sql
CREATE DATABASE prash;
```

## Drop Database
```sql
DROP DATABASE prash;
```

## Use Database
```sql
USE prash;
```

## Table Operations

### Create Table
```sql
CREATE TABLE GAMES (
    name VARCHAR(50),
    rating INT
);
```

### Show Tables
```sql
SHOW TABLES;
```

### Show Columns from Table
```sql
SHOW COLUMNS FROM GAMES;
```

### Describe Table
```sql
DESC GAMES;
```

### Drop Table
```sql
DROP TABLE GAMES;
```

### Create Table with Default Values
```sql
CREATE TABLE GAMES (
    name VARCHAR(50) DEFAULT 'anonymous',
    rating INT DEFAULT 2025
);
```

### Describe Table
```sql
DESC GAMES;
```

### Drop Table
```sql
DROP TABLE GAMES;
```

## Data Types
- **INT**: Used to store integer values.
- **DECIMAL**: Used to store floating-point values.
- **DATE**: Used to store date values in 'YYYY-MM-DD' format.
- **TIME**: Used to store time values in 'HH:MM:SS' format.
- **DATETIME**: Used to store date and time values in 'YYYY-MM-DD HH:MM:SS' format.
- **CHAR**: Used to store fixed-length strings.

### Create Table with Various Data Types
```sql
CREATE TABLE MOVIES (
    title VARCHAR(50),
    release_year INT,
    rating DECIMAL,
    comment CHAR(10),
    comment_date DATE DEFAULT '2025-04-02',
    comment_time TIME DEFAULT '22:22:33'
);
```

## Insert Data
```sql
INSERT INTO GAMES (name, rating) VALUES ('gta6', 12);
```

## Primary Key
```sql
CREATE TABLE MOVIES (
    id INT PRIMARY KEY,
    title VARCHAR(50),
    genre VARCHAR(50),
    director VARCHAR(50),
    cast_count INT,
    languages INT,
    release_year INT,
    imdb_rating DOUBLE,
    duration INT
);
```

### Insert Data with Primary Key
```sql
INSERT INTO MOVIES (id, title, genre, director, cast_count, languages, release_year, imdb_rating, duration) VALUES (1, 'The Witcher', 'Horror', 'Timur', 5, 5, 2025, 5.0, 120);
```

### Drop Table
```sql
DROP TABLE MOVIES;
```

### Create Table with Auto Increment Primary Key
```sql
CREATE TABLE MOVIES (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(50),
    genre VARCHAR(50),
    director VARCHAR(50),
    cast_count INT,
    languages INT,
    release_year INT,
    imdb_rating DOUBLE,
    duration INT
);
```

### Insert Data
```sql
INSERT INTO MOVIES (title, genre, director, cast_count, languages, release_year, imdb_rating, duration) VALUES ('The Witcher', 'Horror', 'Timur', 5, 5, 2025, 5.0, 120);
INSERT INTO MOVIES (title, genre, director, cast_count, languages, release_year, imdb_rating, duration) VALUES ('Excretion', 'Horror', 'Timur', 5, 5, 2025, 5.0, 120);
```

### Select Data
```sql
SELECT * FROM MOVIES;
```

### Filter Data with WHERE Clause
```sql
SELECT * FROM MOVIES WHERE genre = 'Horror';
SELECT title AS movie_title FROM MOVIES WHERE genre = 'Horror';
```

## Update Data
```sql
UPDATE MOVIES SET genre = 'Thriller' WHERE id = 1;
```

## Delete Data
```sql
DELETE FROM MOVIES WHERE id = 1;
```

## Order By
```sql
SELECT * FROM MOVIES ORDER BY release_year DESC;
```

## Limit
```sql
SELECT * FROM MOVIES ORDER BY release_year DESC LIMIT 5;
```

## Like Operator
```sql
SELECT * FROM MOVIES WHERE title LIKE '%a%';
```

## Aggregation Functions
```sql
SELECT COUNT(id) FROM MOVIES;
SELECT MAX(release_year) FROM MOVIES;
SELECT AVG(imdb_rating) FROM MOVIES;
SELECT SUM(duration) FROM MOVIES;
```

## Create Users Table
```sql
CREATE TABLE USERS (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    age INT
);
```

### Insert Data into Users Table
```sql
INSERT INTO USERS (first_name, last_name, email, password, age) VALUES ('Jane', 'Doe', 'jane@example.com', 'password4', 10);
-- Add more entries as needed
```

### Select Data with Conditions
```sql
SELECT first_name, last_name, age FROM USERS WHERE age != 30;
SELECT first_name, last_name, age FROM USERS WHERE age > 30;
SELECT first_name, last_name, age FROM USERS WHERE age < 30;
SELECT first_name, last_name, age FROM USERS WHERE LENGTH(first_name) > 5;
SELECT first_name, last_name, age FROM USERS WHERE age != 30 AND LENGTH(first_name) > 4;
SELECT first_name, last_name, age FROM USERS WHERE age != 30 OR LENGTH(first_name) > 4;
SELECT first_name, last_name, age FROM USERS WHERE age BETWEEN 30 AND 40;
SELECT first_name, last_name, age FROM USERS WHERE age IN (30, 40);
```

## Alter Table
```sql
ALTER TABLE USERS DROP COLUMN age;
ALTER TABLE USERS CHANGE COLUMN email mail VARCHAR(25);
ALTER TABLE USERS MODIFY COLUMN mail VARCHAR(30);
```

## Relationships in Database
- **One to One**: A single record in one table corresponds to exactly one record in another table.
- **One to Many**: A single record in one table corresponds to multiple records in another table.
- **Many to Many**: Multiple records in one table correspond to multiple records in another table.

## Foreign Key
```sql
CREATE TABLE ENGINEER (
    engineer_id INT AUTO_INCREMENT PRIMARY KEY,
    engineer_name VARCHAR(255) NOT NULL,
    profession VARCHAR(255)
);

CREATE TABLE TASKS (
    task_id INT AUTO_INCREMENT PRIMARY KEY,
    task_name VARCHAR(255),
    text_description TEXT,
    engineer_id INT,
    FOREIGN KEY (engineer_id) REFERENCES ENGINEER (engineer_id)
);
```

Feel free to add more sections or modify the content as needed. This should give your README file a nice look and clear structure. If you need further assistance, let me know!
