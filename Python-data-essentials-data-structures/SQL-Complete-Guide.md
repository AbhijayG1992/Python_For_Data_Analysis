# 🗄️ SQL for Data Analysis - Complete Guide

## 📅 SQL Course Schedule (Days 8-12)

| Day            | Module                                     | Chapter                        | Topic                                                                                                                        |
|----------------|--------------------------------------------|--------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| Day 8          | Module 1: Fundamentals of Programming      | SQL                            | Introduction to Databases, Why SQL?                                                                                          |
| Day 8          | Module 1: Fundamentals of Programming      | SQL                            | Execution of an SQL statement, IMDB dataset, Installing MySQL, Load IMDB data, USE, DESCRIBE, SHOW TABLES, SELECT            |
| Day 9          | Module 1: Fundamentals of Programming      | SQL                            | LIMIT, OFFSET, ORDER BY, DISTINCT, WHERE                                                                                     |
| Day 10         | Module 1: Fundamentals of Programming      | SQL                            | Comparison operators, NULL, Logical Operators, Aggregate Functions: COUNT, MIN, MAX, AVG, SUM                                |
| Day 11         | Module 1: Fundamentals of Programming      | SQL                            | GROUP BY, HAVING, ORDER BY keywords, Join and Natural Join, Inner, Left, Right and Outer joins                               |
| Day 12         | Module 1: Fundamentals of Programming      | SQL                            | Sub Queries/Nested Queries/Inner Queries, DML: INSERT, UPDATE, DELETE, DDL: CREATE TABLE, ALTER: ADD, MODIFY, DROP,          |
| Day 12         | Module 1: Fundamentals of Programming      | SQL                            | DDL: DROP TABLE, TRUNCATE, DELETE, Data Control Language: GRANT, REVOKE                                                      |

---

# Day 8: Introduction to Databases and MySQL

## Introduction to Databases

### What is a Database?

A **database** is an organized collection of structured data stored electronically in a computer system. Databases allow for efficient storage, retrieval, and management of data.

#### Key Concepts:

- **Data**: Raw facts and figures (e.g., names, numbers, dates)
- **Information**: Processed data that has meaning and context
- **Database**: Organized collection of data
- **DBMS (Database Management System)**: Software to manage databases (e.g., MySQL, PostgreSQL, Oracle)

### Types of Databases:

1. **Relational Databases (RDBMS)**
   - Data stored in tables with rows and columns
   - Uses SQL (Structured Query Language)
   - Examples: MySQL, PostgreSQL, Oracle, SQL Server

2. **NoSQL Databases**
   - Non-relational databases
   - Examples: MongoDB, Cassandra, Redis

3. **Cloud Databases**
   - Hosted on cloud platforms
   - Examples: Amazon RDS, Google Cloud SQL, Azure SQL

### Database Terminology:

```
Table (Relation)
├── Columns (Attributes/Fields)
│   ├── Column Name
│   ├── Data Type
│   └── Constraints
└── Rows (Records/Tuples)
    └── Individual data entries
```

**Example Table: Students**

| student_id | name      | age | grade | city       |
|------------|-----------|-----|-------|------------|
| 1          | Alice     | 20  | A     | New York   |
| 2          | Bob       | 22  | B     | London     |
| 3          | Charlie   | 21  | A     | Paris      |

- **Table Name**: Students
- **Columns**: student_id, name, age, grade, city
- **Rows**: 3 records
- **Primary Key**: student_id (unique identifier)

---

## Why SQL?

### What is SQL?

**SQL (Structured Query Language)** is a standard programming language specifically designed for managing and manipulating relational databases.

### Why Learn SQL?

1. **Universal Language**: Works with all major relational databases
2. **Data Analysis**: Essential for data scientists and analysts
3. **High Demand**: One of the most sought-after skills in tech
4. **Easy to Learn**: Readable syntax similar to English
5. **Powerful**: Can handle millions of records efficiently
6. **Industry Standard**: Used by companies worldwide

### SQL Use Cases:

- **Data Retrieval**: Query and fetch specific data
- **Data Manipulation**: Insert, update, delete records
- **Data Analysis**: Aggregate, filter, and analyze data
- **Reporting**: Generate business reports
- **Database Administration**: Create and manage database structures

### SQL vs Other Languages:

| Feature | SQL | Python/Java |
|---------|-----|-------------|
| Purpose | Database operations | General programming |
| Syntax | Declarative | Imperative |
| Learning Curve | Easy | Moderate to Hard |
| Use Case | Data management | Application development |

---

## Installing MySQL

### What is MySQL?

**MySQL** is one of the most popular open-source relational database management systems. It's fast, reliable, and widely used in web applications.

### Installation Steps:

#### **Windows:**

1. **Download MySQL Installer**
   - Visit: https://dev.mysql.com/downloads/installer/
   - Download MySQL Installer for Windows

2. **Run the Installer**
   - Double-click the downloaded `.msi` file
   - Choose "Developer Default" or "Server only"

3. **Configuration**
   - Set root password (remember this!)
   - Configure MySQL Server
   - Choose port (default: 3306)

4. **Verify Installation**
   ```cmd
   mysql --version
   ```

#### **macOS:**

1. **Using Homebrew** (Recommended)
   ```bash
   # Install Homebrew if not installed
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   
   # Install MySQL
   brew install mysql
   
   # Start MySQL service
   brew services start mysql
   
   # Secure installation
   mysql_secure_installation
   ```

2. **Using DMG Package**
   - Download from: https://dev.mysql.com/downloads/mysql/
   - Install the `.dmg` file
   - Follow installation wizard

3. **Verify Installation**
   ```bash
   mysql --version
   ```

#### **Linux (Ubuntu/Debian):**

```bash
# Update package index
sudo apt update

# Install MySQL Server
sudo apt install mysql-server

# Start MySQL service
sudo systemctl start mysql

# Enable MySQL to start on boot
sudo systemctl enable mysql

# Secure installation
sudo mysql_secure_installation

# Verify installation
mysql --version
```

### Connecting to MySQL:

```bash
# Connect as root user
mysql -u root -p

# Enter password when prompted
```

### MySQL Command Line Basics:

```sql
-- Show MySQL version
SELECT VERSION();

-- Show current date and time
SELECT NOW();

-- Show current user
SELECT USER();

-- Exit MySQL
EXIT;
-- or
QUIT;
```

---

## Execution of an SQL Statement

### How SQL Statements are Executed:

```
User Query → Parser → Optimizer → Execution Engine → Storage Engine → Result
```

1. **Parser**: Checks syntax and validates the query
2. **Optimizer**: Determines the most efficient way to execute
3. **Execution Engine**: Executes the optimized query plan
4. **Storage Engine**: Retrieves/modifies data from disk
5. **Result**: Returns the output to the user

### SQL Statement Structure:

```sql
SELECT column1, column2
FROM table_name
WHERE condition
ORDER BY column1
LIMIT 10;
```

**Execution Order:**
1. FROM - Identify the table
2. WHERE - Filter rows
3. SELECT - Choose columns
4. ORDER BY - Sort results
5. LIMIT - Restrict number of rows

---

## IMDB Dataset

### About the IMDB Dataset:

The **IMDB (Internet Movie Database)** dataset contains information about movies, actors, directors, ratings, and more. It's perfect for learning SQL!

### Dataset Structure:

**Main Tables:**

1. **movies**
   - movie_id, title, year, genre, rating, duration

2. **actors**
   - actor_id, name, birth_year, nationality

3. **directors**
   - director_id, name, birth_year, nationality

4. **movie_cast**
   - movie_id, actor_id, role

5. **ratings**
   - movie_id, rating, votes

### Sample Data:

**movies table:**
```
+----------+----------------------+------+--------+--------+----------+
| movie_id | title                | year | genre  | rating | duration |
+----------+----------------------+------+--------+--------+----------+
| 1        | The Shawshank Red... | 1994 | Drama  | 9.3    | 142      |
| 2        | The Godfather        | 1972 | Crime  | 9.2    | 175      |
| 3        | The Dark Knight      | 2008 | Action | 9.0    | 152      |
+----------+----------------------+------+--------+--------+----------+
```

---

## Loading IMDB Data into MySQL

### Step 1: Create Database

```sql
-- Create a new database
CREATE DATABASE imdb_db;

-- Verify database creation
SHOW DATABASES;

-- Use the database
USE imdb_db;
```

### Step 2: Create Tables

```sql
-- Create movies table
CREATE TABLE movies (
    movie_id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(255) NOT NULL,
    year INT,
    genre VARCHAR(100),
    rating DECIMAL(3,1),
    duration INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Create actors table
CREATE TABLE actors (
    actor_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    birth_year INT,
    nationality VARCHAR(100)
);

-- Create directors table
CREATE TABLE directors (
    director_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    birth_year INT,
    nationality VARCHAR(100)
);

-- Create movie_cast table (junction table)
CREATE TABLE movie_cast (
    cast_id INT PRIMARY KEY AUTO_INCREMENT,
    movie_id INT,
    actor_id INT,
    role VARCHAR(255),
    FOREIGN KEY (movie_id) REFERENCES movies(movie_id),
    FOREIGN KEY (actor_id) REFERENCES actors(actor_id)
);
```

### Step 3: Insert Sample Data

```sql
-- Insert movies
INSERT INTO movies (title, year, genre, rating, duration) VALUES
('The Shawshank Redemption', 1994, 'Drama', 9.3, 142),
('The Godfather', 1972, 'Crime', 9.2, 175),
('The Dark Knight', 2008, 'Action', 9.0, 152),
('Pulp Fiction', 1994, 'Crime', 8.9, 154),
('Forrest Gump', 1994, 'Drama', 8.8, 142),
('Inception', 2010, 'Sci-Fi', 8.8, 148),
('The Matrix', 1999, 'Sci-Fi', 8.7, 136),
('Goodfellas', 1990, 'Crime', 8.7, 146),
('The Silence of the Lambs', 1991, 'Thriller', 8.6, 118),
('Interstellar', 2014, 'Sci-Fi', 8.6, 169);

-- Insert actors
INSERT INTO actors (name, birth_year, nationality) VALUES
('Morgan Freeman', 1937, 'American'),
('Tim Robbins', 1958, 'American'),
('Marlon Brando', 1924, 'American'),
('Al Pacino', 1940, 'American'),
('Christian Bale', 1974, 'British'),
('Heath Ledger', 1979, 'Australian'),
('Leonardo DiCaprio', 1974, 'American'),
('Tom Hanks', 1956, 'American'),
('Keanu Reeves', 1964, 'Canadian'),
('Matthew McConaughey', 1969, 'American');

-- Insert directors
INSERT INTO directors (name, birth_year, nationality) VALUES
('Frank Darabont', 1959, 'American'),
('Francis Ford Coppola', 1939, 'American'),
('Christopher Nolan', 1970, 'British'),
('Quentin Tarantino', 1963, 'American'),
('Robert Zemeckis', 1951, 'American');
```

### Step 4: Load Data from CSV (Alternative Method)

```sql
-- Load data from CSV file
LOAD DATA INFILE '/path/to/movies.csv'
INTO TABLE movies
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
```

---

## Basic SQL Commands

### USE - Select Database

```sql
-- Switch to a database
USE imdb_db;

-- Verify current database
SELECT DATABASE();
```

### DESCRIBE - Show Table Structure

```sql
-- Show table structure
DESCRIBE movies;
-- or
DESC movies;

-- Output:
-- +------------+--------------+------+-----+---------+----------------+
-- | Field      | Type         | Null | Key | Default | Extra          |
-- +------------+--------------+------+-----+---------+----------------+
-- | movie_id   | int          | NO   | PRI | NULL    | auto_increment |
-- | title      | varchar(255) | NO   |     | NULL    |                |
-- | year       | int          | YES  |     | NULL    |                |
-- | genre      | varchar(100) | YES  |     | NULL    |                |
-- | rating     | decimal(3,1) | YES  |     | NULL    |                |
-- | duration   | int          | YES  |     | NULL    |                |
-- +------------+--------------+------+-----+---------+----------------+
```

### SHOW TABLES - List All Tables

```sql
-- Show all tables in current database
SHOW TABLES;

-- Output:
-- +-------------------+
-- | Tables_in_imdb_db |
-- +-------------------+
-- | actors            |
-- | directors         |
-- | movie_cast        |
-- | movies            |
-- +-------------------+

-- Show tables from specific database
SHOW TABLES FROM imdb_db;

-- Show table creation statement
SHOW CREATE TABLE movies;
```

### SELECT - Retrieve Data

```sql
-- Select all columns from a table
SELECT * FROM movies;

-- Select specific columns
SELECT title, year, rating FROM movies;

-- Select with column alias
SELECT 
    title AS movie_name,
    year AS release_year,
    rating AS imdb_rating
FROM movies;

-- Select distinct values
SELECT DISTINCT genre FROM movies;

-- Select with calculations
SELECT 
    title,
    duration,
    duration / 60 AS duration_hours
FROM movies;

-- Select current date and time
SELECT NOW(), CURDATE(), CURTIME();

-- Select with string functions
SELECT 
    UPPER(title) AS uppercase_title,
    LOWER(genre) AS lowercase_genre,
    LENGTH(title) AS title_length
FROM movies;
```

### Practical Examples:

```sql
-- Example 1: Get all movie titles
SELECT title FROM movies;

-- Example 2: Get movies with their ratings
SELECT title, rating 
FROM movies;

-- Example 3: Get movie count
SELECT COUNT(*) AS total_movies 
FROM movies;

-- Example 4: Get unique genres
SELECT DISTINCT genre 
FROM movies;

-- Example 5: Get movies released after 2000
SELECT title, year 
FROM movies 
WHERE year > 2000;
```

---

## Summary: Day 8

### What We Learned:

1. **Database Fundamentals**
   - What databases are and why they're important
   - Types of databases (RDBMS, NoSQL, Cloud)
   - Database terminology (tables, columns, rows)

2. **Why SQL**
   - SQL is the standard language for databases
   - Essential for data analysis and manipulation
   - Universal and powerful

3. **MySQL Installation**
   - Installing on Windows, macOS, and Linux
   - Connecting to MySQL
   - Basic MySQL commands

4. **SQL Execution**
   - How SQL statements are processed
   - Query execution order

5. **IMDB Dataset**
   - Understanding the dataset structure
   - Creating tables
   - Loading sample data

6. **Basic Commands**
   - USE: Select database
   - DESCRIBE: Show table structure
   - SHOW TABLES: List tables
   - SELECT: Retrieve data

### Key Takeaways:

- Databases organize data into structured tables
- SQL is declarative and easy to learn
- MySQL is a popular open-source RDBMS
- SELECT is the most fundamental SQL command
- Always USE a database before querying tables

### Practice Exercises:

```sql
-- Exercise 1: Create your own database
CREATE DATABASE practice_db;
USE practice_db;

-- Exercise 2: Create a students table
CREATE TABLE students (
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    age INT,
    grade CHAR(1)
);

-- Exercise 3: Insert sample data
INSERT INTO students (name, age, grade) VALUES
('Alice', 20, 'A'),
('Bob', 22, 'B'),
('Charlie', 21, 'A');

-- Exercise 4: Query the data
SELECT * FROM students;
DESCRIBE students;
SHOW TABLES;
```

---

# Day 9: Filtering and Sorting Data

## LIMIT - Restrict Number of Rows

The `LIMIT` clause restricts the number of rows returned by a query.

### Basic LIMIT Syntax:

```sql
SELECT column1, column2
FROM table_name
LIMIT number_of_rows;
```

### Examples:

```sql
-- Get first 5 movies
SELECT * FROM movies
LIMIT 5;

-- Get top 3 highest-rated movies
SELECT title, rating
FROM movies
ORDER BY rating DESC
LIMIT 3;

-- Output:
-- +---------------------------+--------+
-- | title                     | rating |
-- +---------------------------+--------+
-- | The Shawshank Redemption  | 9.3    |
-- | The Godfather             | 9.2    |
-- | The Dark Knight           | 9.0    |
-- +---------------------------+--------+

-- Get 5 most recent movies
SELECT title, year
FROM movies
ORDER BY year DESC
LIMIT 5;
```

---

## OFFSET - Skip Rows

The `OFFSET` clause skips a specified number of rows before returning results. Often used with LIMIT for pagination.

### LIMIT with OFFSET Syntax:

```sql
SELECT column1, column2
FROM table_name
LIMIT number_of_rows OFFSET skip_rows;

-- Alternative syntax
SELECT column1, column2
FROM table_name
LIMIT skip_rows, number_of_rows;
```

### Pagination Examples:

```sql
-- Page 1: First 5 movies
SELECT title, year
FROM movies
ORDER BY year DESC
LIMIT 5 OFFSET 0;

-- Page 2: Next 5 movies (skip first 5)
SELECT title, year
FROM movies
ORDER BY year DESC
LIMIT 5 OFFSET 5;

-- Page 3: Next 5 movies (skip first 10)
SELECT title, year
FROM movies
ORDER BY year DESC
LIMIT 5 OFFSET 10;

-- Alternative syntax for Page 2
SELECT title, year
FROM movies
ORDER BY year DESC
LIMIT 5, 5;  -- LIMIT offset, count
```

### Practical Pagination:

```sql
-- Function to calculate offset
-- Page 1: OFFSET = (1-1) * 5 = 0
-- Page 2: OFFSET = (2-1) * 5 = 5
-- Page 3: OFFSET = (3-1) * 5 = 10

-- Get page 2 with 5 items per page
SET @page_number = 2;
SET @items_per_page = 5;
SET @offset = (@page_number - 1) * @items_per_page;

SELECT title, rating
FROM movies
ORDER BY rating DESC
LIMIT @items_per_page OFFSET @offset;
```

---

## ORDER BY - Sort Results

The `ORDER BY` clause sorts the result set by one or more columns.

### ORDER BY Syntax:

```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 [ASC|DESC], column2 [ASC|DESC];
```

- **ASC**: Ascending order (default)
- **DESC**: Descending order

### Single Column Sorting:

```sql
-- Sort by rating (ascending - lowest to highest)
SELECT title, rating
FROM movies
ORDER BY rating ASC;

-- Sort by rating (descending - highest to lowest)
SELECT title, rating
FROM movies
ORDER BY rating DESC;

-- Sort by title alphabetically
SELECT title, year
FROM movies
ORDER BY title;

-- Sort by year (newest first)
SELECT title, year
FROM movies
ORDER BY year DESC;
```

### Multiple Column Sorting:

```sql
-- Sort by genre, then by rating within each genre
SELECT title, genre, rating
FROM movies
ORDER BY genre ASC, rating DESC;

-- Output:
-- +---------------------------+----------+--------+
-- | title                     | genre    | rating |
-- +---------------------------+----------+--------+
-- | The Dark Knight           | Action   | 9.0    |
-- | Goodfellas                | Crime    | 8.7    |
-- | The Godfather             | Crime    | 9.2    |
-- | Pulp Fiction              | Crime    | 8.9    |
-- | The Shawshank Redemption  | Drama    | 9.3    |
-- | Forrest Gump              | Drama    | 8.8    |
-- +---------------------------+----------+--------+

-- Sort by year DESC, then rating DESC
SELECT title, year, rating
FROM movies
ORDER BY year DESC, rating DESC;
```

### Sorting with Expressions:

```sql
-- Sort by duration in hours
SELECT title, duration, duration/60 AS hours
FROM movies
ORDER BY duration/60 DESC;

-- Sort by title length
SELECT title, LENGTH(title) AS title_length
FROM movies
ORDER BY LENGTH(title) DESC;

-- Sort by calculated field
SELECT 
    title,
    rating * duration AS weighted_score
FROM movies
ORDER BY weighted_score DESC;
```

---

## DISTINCT - Remove Duplicates

The `DISTINCT` keyword returns only unique values, eliminating duplicates.

### DISTINCT Syntax:

```sql
SELECT DISTINCT column1, column2
FROM table_name;
```

### Examples:

```sql
-- Get unique genres
SELECT DISTINCT genre
FROM movies;

-- Output:
-- +----------+
-- | genre    |
-- +----------+
-- | Drama    |
-- | Crime    |
-- | Action   |
-- | Sci-Fi   |
-- | Thriller |
-- +----------+

-- Get unique years
SELECT DISTINCT year
FROM movies
ORDER BY year DESC;

-- Get unique combinations of genre and year
SELECT DISTINCT genre, year
FROM movies
ORDER BY genre, year;

-- Count unique genres
SELECT COUNT(DISTINCT genre) AS unique_genres
FROM movies;
```

### DISTINCT vs GROUP BY:

```sql
-- Using DISTINCT
SELECT DISTINCT genre
FROM movies;

-- Using GROUP BY (same result)
SELECT genre
FROM movies
GROUP BY genre;

-- DISTINCT with multiple columns
SELECT DISTINCT genre, year
FROM movies;
```

---

## WHERE - Filter Rows

The `WHERE` clause filters rows based on specified conditions.

### WHERE Syntax:

```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

### Basic WHERE Examples:

```sql
-- Movies with rating greater than 9.0
SELECT title, rating
FROM movies
WHERE rating > 9.0;

-- Movies released in 1994
SELECT title, year
FROM movies
WHERE year = 1994;

-- Movies in Drama genre
SELECT title, genre
FROM movies
WHERE genre = 'Drama';

-- Movies longer than 150 minutes
SELECT title, duration
FROM movies
WHERE duration > 150;
```

### WHERE with Multiple Conditions:

```sql
-- Movies from 1994 with rating > 8.5
SELECT title, year, rating
FROM movies
WHERE year = 1994 AND rating > 8.5;

-- Movies that are either Drama or Crime
SELECT title, genre
FROM movies
WHERE genre = 'Drama' OR genre = 'Crime';

-- Movies NOT in Sci-Fi genre
SELECT title, genre
FROM movies
WHERE genre != 'Sci-Fi';
-- or
SELECT title, genre
FROM movies
WHERE genre <> 'Sci-Fi';

-- Movies between 1990 and 2000
SELECT title, year
FROM movies
WHERE year >= 1990 AND year <= 2000;
```

### WHERE with BETWEEN:

```sql
-- Movies released between 1990 and 2000
SELECT title, year
FROM movies
WHERE year BETWEEN 1990 AND 2000;

-- Movies with rating between 8.5 and 9.0
SELECT title, rating
FROM movies
WHERE rating BETWEEN 8.5 AND 9.0;

-- Movies with duration between 120 and 150 minutes
SELECT title, duration
FROM movies
WHERE duration BETWEEN 120 AND 150;
```

### WHERE with IN:

```sql
-- Movies from specific years
SELECT title, year
FROM movies
WHERE year IN (1994, 1999, 2008, 2010);

-- Movies in specific genres
SELECT title, genre
FROM movies
WHERE genre IN ('Drama', 'Crime', 'Thriller');

-- Movies NOT in specific genres
SELECT title, genre
FROM movies
WHERE genre NOT IN ('Sci-Fi', 'Action');
```

### WHERE with LIKE (Pattern Matching):

```sql
-- Movies starting with 'The'
SELECT title
FROM movies
WHERE title LIKE 'The%';

-- Movies containing 'God'
SELECT title
FROM movies
WHERE title LIKE '%God%';

-- Movies ending with 'ion'
SELECT title
FROM movies
WHERE title LIKE '%ion';

-- Movies with exactly 11 characters
SELECT title
FROM movies
WHERE title LIKE '___________';  -- 11 underscores

-- Case-insensitive search
SELECT title
FROM movies
WHERE LOWER(title) LIKE '%the%';
```

### Combining Everything:

```sql
-- Complex query with all clauses
SELECT title, year, genre, rating, duration
FROM movies
WHERE rating >= 8.5 
  AND year BETWEEN 1990 AND 2010
  AND genre IN ('Drama', 'Crime', 'Sci-Fi')
ORDER BY rating DESC, year DESC
LIMIT 5;

-- Pagination with filtering
SELECT title, rating
FROM movies
WHERE rating > 8.5
ORDER BY rating DESC
LIMIT 5 OFFSET 0;
```

---

## Practical Examples

### Example 1: Top 10 Movies

```sql
SELECT 
    title,
    year,
    rating,
    duration
FROM movies
ORDER BY rating DESC
LIMIT 10;
```

### Example 2: Recent High-Rated Movies

```sql
SELECT title, year, rating
FROM movies
WHERE year >= 2000 AND rating >= 8.5
ORDER BY year DESC, rating DESC;
```

### Example 3: Movies by Genre

```sql
-- Drama movies sorted by rating
SELECT title, rating
FROM movies
WHERE genre = 'Drama'
ORDER BY rating DESC;

-- Count movies per genre
SELECT 
    genre,
    COUNT(*) AS movie_count
FROM movies
GROUP BY genre
ORDER BY movie_count DESC;
```

### Example 4: Search Functionality

```sql
-- Search for movies with 'Dark' in title
SELECT title, year, rating
FROM movies
WHERE title LIKE '%Dark%'
ORDER BY rating DESC;

-- Search across multiple fields
SELECT title, year, genre
FROM movies
WHERE title LIKE '%God%'
   OR genre LIKE '%Crime%'
ORDER BY year DESC;
```

### Example 5: Pagination System

```sql
-- Page 1 (items 1-5)
SELECT title, rating
FROM movies
ORDER BY rating DESC
LIMIT 5 OFFSET 0;

-- Page 2 (items 6-10)
SELECT title, rating
FROM movies
ORDER BY rating DESC
LIMIT 5 OFFSET 5;

-- Page 3 (items 11-15)
SELECT title, rating
FROM movies
ORDER BY rating DESC
LIMIT 5 OFFSET 10;
```

---

## Summary: Day 9

### What We Learned:

1. **LIMIT**: Restrict number of rows returned
2. **OFFSET**: Skip rows for pagination
3. **ORDER BY**: Sort results by one or more columns
4. **DISTINCT**: Remove duplicate values
5. **WHERE**: Filter rows based on conditions

### Key Concepts:

- LIMIT is essential for performance with large datasets
- OFFSET enables pagination
- ORDER BY can sort by multiple columns
- DISTINCT removes duplicates
- WHERE filters data before processing
- Combine clauses for powerful queries

### SQL Execution Order:

```
FROM → WHERE → SELECT → DISTINCT → ORDER BY → LIMIT/OFFSET
```

### Practice Exercises:

```sql
-- Exercise 1: Get top 5 oldest movies
SELECT title, year
FROM movies
ORDER BY year ASC
LIMIT 5;

-- Exercise 2: Get movies from page 2 (items 6-10)
SELECT title, rating
FROM movies
ORDER BY rating DESC
LIMIT 5 OFFSET 5;

-- Exercise 3: Get unique genres sorted alphabetically
SELECT DISTINCT genre
FROM movies
ORDER BY genre;

-- Exercise 4: Get Crime movies with rating > 8.5
SELECT title, rating
FROM movies
WHERE genre = 'Crime' AND rating > 8.5
ORDER BY rating DESC;

-- Exercise 5: Search for movies with 'The' in title
SELECT title, year
FROM movies
WHERE title LIKE '%The%'
ORDER BY year DESC;
```

---

# Day 10-12: Advanced SQL - Operators, Functions, Joins, and Data Manipulation

## Day 10: Comparison Operators, NULL, Logical Operators, and Aggregate Functions

### Comparison Operators

Comparison operators are used in WHERE clauses to filter data.

| Operator | Description | Example |
|----------|-------------|---------|
| = | Equal to | `rating = 9.0` |
| != or <> | Not equal to | `genre != 'Drama'` |
| > | Greater than | `year > 2000` |
| < | Less than | `duration < 120` |
| >= | Greater than or equal | `rating >= 8.5` |
| <= | Less than or equal | `year <= 1995` |

```sql
-- Movies with exact rating
SELECT title, rating FROM movies WHERE rating = 9.0;

-- Movies not in Drama genre
SELECT title, genre FROM movies WHERE genre <> 'Drama';

-- Movies after 2000
SELECT title, year FROM movies WHERE year > 2000;

-- Movies 2 hours or longer
SELECT title, duration FROM movies WHERE duration >= 120;
```

### NULL Values

NULL represents missing or unknown data.

```sql
-- Find movies with NULL rating
SELECT title, rating FROM movies WHERE rating IS NULL;

-- Find movies with rating (not NULL)
SELECT title, rating FROM movies WHERE rating IS NOT NULL;

-- Count NULL values
SELECT COUNT(*) - COUNT(rating) AS null_ratings FROM movies;

-- Handle NULL with COALESCE
SELECT title, COALESCE(rating, 0) AS rating FROM movies;

-- Handle NULL with IFNULL
SELECT title, IFNULL(rating, 'Not Rated') AS rating FROM movies;
```

### Logical Operators

Combine multiple conditions.

**AND Operator:**
```sql
-- Movies from 1994 with high rating
SELECT title, year, rating
FROM movies
WHERE year = 1994 AND rating > 8.5;

-- Sci-Fi movies longer than 140 minutes
SELECT title, genre, duration
FROM movies
WHERE genre = 'Sci-Fi' AND duration > 140;
```

**OR Operator:**
```sql
-- Movies from 1994 or 1999
SELECT title, year
FROM movies
WHERE year = 1994 OR year = 1999;

-- Drama or Crime movies
SELECT title, genre
FROM movies
WHERE genre = 'Drama' OR genre = 'Crime';
```

**NOT Operator:**
```sql
-- Movies NOT in Sci-Fi genre
SELECT title, genre
FROM movies
WHERE NOT genre = 'Sci-Fi';

-- Movies NOT from the 1990s
SELECT title, year
FROM movies
WHERE NOT (year BETWEEN 1990 AND 1999);
```

**Combining Operators:**
```sql
-- Complex condition
SELECT title, year, genre, rating
FROM movies
WHERE (genre = 'Drama' OR genre = 'Crime')
  AND rating >= 8.5
  AND year BETWEEN 1990 AND 2000;
```

### Aggregate Functions

Perform calculations on multiple rows.

**COUNT() - Count Rows:**
```sql
-- Total number of movies
SELECT COUNT(*) AS total_movies FROM movies;

-- Count non-NULL ratings
SELECT COUNT(rating) AS rated_movies FROM movies;

-- Count distinct genres
SELECT COUNT(DISTINCT genre) AS unique_genres FROM movies;

-- Count movies per genre
SELECT genre, COUNT(*) AS movie_count
FROM movies
GROUP BY genre;
```

**MIN() - Minimum Value:**
```sql
-- Lowest rating
SELECT MIN(rating) AS lowest_rating FROM movies;

-- Earliest year
SELECT MIN(year) AS earliest_year FROM movies;

-- Shortest movie
SELECT title, MIN(duration) AS shortest_duration
FROM movies;
```

**MAX() - Maximum Value:**
```sql
-- Highest rating
SELECT MAX(rating) AS highest_rating FROM movies;

-- Most recent year
SELECT MAX(year) AS latest_year FROM movies;

-- Longest movie
SELECT title, duration
FROM movies
WHERE duration = (SELECT MAX(duration) FROM movies);
```

**AVG() - Average Value:**
```sql
-- Average rating
SELECT AVG(rating) AS average_rating FROM movies;

-- Average duration
SELECT AVG(duration) AS avg_duration FROM movies;

-- Average rating by genre
SELECT genre, AVG(rating) AS avg_rating
FROM movies
GROUP BY genre
ORDER BY avg_rating DESC;
```

**SUM() - Sum of Values:**
```sql
-- Total duration of all movies
SELECT SUM(duration) AS total_duration FROM movies;

-- Total duration by genre
SELECT genre, SUM(duration) AS total_duration
FROM movies
GROUP BY genre;
```

**Combining Aggregate Functions:**
```sql
-- Comprehensive statistics
SELECT 
    COUNT(*) AS total_movies,
    MIN(rating) AS min_rating,
    MAX(rating) AS max_rating,
    AVG(rating) AS avg_rating,
    SUM(duration) AS total_duration
FROM movies;
```

---

## Day 11: GROUP BY, HAVING, and Joins

### GROUP BY Clause

Groups rows with same values into summary rows.

```sql
-- Count movies by genre
SELECT genre, COUNT(*) AS movie_count
FROM movies
GROUP BY genre;

-- Average rating by genre
SELECT genre, AVG(rating) AS avg_rating
FROM movies
GROUP BY genre
ORDER BY avg_rating DESC;

-- Movies per year
SELECT year, COUNT(*) AS movies_released
FROM movies
GROUP BY year
ORDER BY year DESC;

-- Multiple grouping columns
SELECT genre, year, COUNT(*) AS count
FROM movies
GROUP BY genre, year
ORDER BY genre, year;
```

### HAVING Clause

Filters groups (used with GROUP BY).

```sql
-- Genres with more than 2 movies
SELECT genre, COUNT(*) AS movie_count
FROM movies
GROUP BY genre
HAVING COUNT(*) > 2;

-- Genres with average rating > 8.5
SELECT genre, AVG(rating) AS avg_rating
FROM movies
GROUP BY genre
HAVING AVG(rating) > 8.5;

-- Years with multiple high-rated movies
SELECT year, COUNT(*) AS count, AVG(rating) AS avg_rating
FROM movies
WHERE rating >= 8.5
GROUP BY year
HAVING COUNT(*) >= 2;
```

**WHERE vs HAVING:**
```sql
-- WHERE filters rows before grouping
-- HAVING filters groups after grouping

SELECT genre, AVG(rating) AS avg_rating
FROM movies
WHERE year >= 2000  -- Filter rows first
GROUP BY genre
HAVING AVG(rating) > 8.0  -- Filter groups after
ORDER BY avg_rating DESC;
```

### Joins

Combine rows from multiple tables.

**Sample Tables for Joins:**
```sql
-- Assume we have these tables:
-- movies (movie_id, title, year, genre, rating)
-- movie_cast (movie_id, actor_id, role)
-- actors (actor_id, name, birth_year)
```

**INNER JOIN:**
```sql
-- Get movies with their actors
SELECT m.title, a.name, mc.role
FROM movies m
INNER JOIN movie_cast mc ON m.movie_id = mc.movie_id
INNER JOIN actors a ON mc.actor_id = a.actor_id;

-- Movies with actors (simplified)
SELECT m.title, a.name
FROM movies m
JOIN movie_cast mc ON m.movie_id = mc.movie_id
JOIN actors a ON mc.actor_id = a.actor_id
WHERE m.rating > 9.0;
```

**LEFT JOIN (LEFT OUTER JOIN):**
```sql
-- All movies, with actors if available
SELECT m.title, a.name
FROM movies m
LEFT JOIN movie_cast mc ON m.movie_id = mc.movie_id
LEFT JOIN actors a ON mc.actor_id = a.actor_id;

-- Movies without cast information
SELECT m.title
FROM movies m
LEFT JOIN movie_cast mc ON m.movie_id = mc.movie_id
WHERE mc.movie_id IS NULL;
```

**RIGHT JOIN (RIGHT OUTER JOIN):**
```sql
-- All actors, with movies if available
SELECT a.name, m.title
FROM movies m
RIGHT JOIN movie_cast mc ON m.movie_id = mc.movie_id
RIGHT JOIN actors a ON mc.actor_id = a.actor_id;
```

**CROSS JOIN:**
```sql
-- Cartesian product (all combinations)
SELECT m.title, a.name
FROM movies m
CROSS JOIN actors a
LIMIT 10;
```

**SELF JOIN:**
```sql
-- Find movies from the same year
SELECT m1.title AS movie1, m2.title AS movie2, m1.year
FROM movies m1
JOIN movies m2 ON m1.year = m2.year AND m1.movie_id < m2.movie_id
ORDER BY m1.year;
```

---

## Day 12: Subqueries and Data Manipulation

### Subqueries (Nested Queries)

A query within another query.

**Subquery in WHERE:**
```sql
-- Movies with above-average rating
SELECT title, rating
FROM movies
WHERE rating > (SELECT AVG(rating) FROM movies);

-- Movies from the same year as 'Inception'
SELECT title, year
FROM movies
WHERE year = (SELECT year FROM movies WHERE title = 'Inception');
```

**Subquery with IN:**
```sql
-- Movies with actors born after 1970
SELECT title
FROM movies
WHERE movie_id IN (
    SELECT mc.movie_id
    FROM movie_cast mc
    JOIN actors a ON mc.actor_id = a.actor_id
    WHERE a.birth_year > 1970
);
```

**Subquery in SELECT:**
```sql
-- Show rating difference from average
SELECT 
    title,
    rating,
    (SELECT AVG(rating) FROM movies) AS avg_rating,
    rating - (SELECT AVG(rating) FROM movies) AS difference
FROM movies;
```

**Subquery in FROM (Derived Table):**
```sql
-- Average rating by genre, then filter
SELECT genre, avg_rating
FROM (
    SELECT genre, AVG(rating) AS avg_rating
    FROM movies
    GROUP BY genre
) AS genre_stats
WHERE avg_rating > 8.5;
```

### DML: Data Manipulation Language

**INSERT - Add Data:**
```sql
-- Insert single row
INSERT INTO movies (title, year, genre, rating, duration)
VALUES ('New Movie', 2024, 'Action', 8.5, 135);

-- Insert multiple rows
INSERT INTO movies (title, year, genre, rating, duration) VALUES
('Movie 1', 2024, 'Drama', 8.0, 120),
('Movie 2', 2024, 'Comedy', 7.5, 110),
('Movie 3', 2024, 'Thriller', 8.2, 125);

-- Insert from SELECT
INSERT INTO archived_movies
SELECT * FROM movies WHERE year < 1980;
```

**UPDATE - Modify Data:**
```sql
-- Update single row
UPDATE movies
SET rating = 9.5
WHERE movie_id = 1;

-- Update multiple columns
UPDATE movies
SET rating = 8.8, duration = 145
WHERE title = 'Inception';

-- Update with calculation
UPDATE movies
SET duration = duration + 10
WHERE genre = 'Drama';

-- Update with condition
UPDATE movies
SET genre = 'Classic'
WHERE year < 1980;
```

**DELETE - Remove Data:**
```sql
-- Delete specific rows
DELETE FROM movies
WHERE rating < 5.0;

-- Delete with condition
DELETE FROM movies
WHERE year < 1950 AND rating IS NULL;

-- Delete all rows (keep table structure)
DELETE FROM movies;
```

### DDL: Data Definition Language

**CREATE TABLE:**
```sql
-- Create new table
CREATE TABLE reviews (
    review_id INT PRIMARY KEY AUTO_INCREMENT,
    movie_id INT,
    user_name VARCHAR(100),
    rating INT CHECK (rating BETWEEN 1 AND 10),
    comment TEXT,
    review_date DATE DEFAULT CURRENT_DATE,
    FOREIGN KEY (movie_id) REFERENCES movies(movie_id)
);

-- Create table from existing table
CREATE TABLE movies_backup AS
SELECT * FROM movies;
```

**ALTER TABLE:**
```sql
-- Add column
ALTER TABLE movies
ADD COLUMN director VARCHAR(100);

-- Modify column
ALTER TABLE movies
MODIFY COLUMN rating DECIMAL(3,1);

-- Drop column
ALTER TABLE movies
DROP COLUMN director;

-- Add constraint
ALTER TABLE movies
ADD CONSTRAINT chk_rating CHECK (rating BETWEEN 0 AND 10);

-- Rename table
ALTER TABLE movies
RENAME TO films;
```

**DROP TABLE:**
```sql
-- Delete table completely
DROP TABLE IF EXISTS old_movies;

-- Drop multiple tables
DROP TABLE table1, table2, table3;
```

**TRUNCATE:**
```sql
-- Remove all rows (faster than DELETE)
TRUNCATE TABLE movies;
```

**DELETE vs TRUNCATE:**
```sql
-- DELETE: Can use WHERE, slower, can rollback
DELETE FROM movies WHERE year < 1950;

-- TRUNCATE: No WHERE, faster, cannot rollback
TRUNCATE TABLE movies;
```

### DCL: Data Control Language

**GRANT - Give Permissions:**
```sql
-- Grant SELECT permission
GRANT SELECT ON imdb_db.movies TO 'user1'@'localhost';

-- Grant multiple permissions
GRANT SELECT, INSERT, UPDATE ON imdb_db.* TO 'user2'@'localhost';

-- Grant all permissions
GRANT ALL PRIVILEGES ON imdb_db.* TO 'admin'@'localhost';
```

**REVOKE - Remove Permissions:**
```sql
-- Revoke SELECT permission
REVOKE SELECT ON imdb_db.movies FROM 'user1'@'localhost';

-- Revoke all permissions
REVOKE ALL PRIVILEGES ON imdb_db.* FROM 'user2'@'localhost';
```

---

## Complete SQL Reference Summary

### Query Execution Order:
```
FROM → JOIN → WHERE → GROUP BY → HAVING → SELECT → DISTINCT → ORDER BY → LIMIT
```

### Essential Commands Cheat Sheet:

```sql
-- Database Operations
CREATE DATABASE db_name;
DROP DATABASE db_name;
USE db_name;
SHOW DATABASES;

-- Table Operations
CREATE TABLE table_name (...);
ALTER TABLE table_name ...;
DROP TABLE table_name;
TRUNCATE TABLE table_name;
DESCRIBE table_name;
SHOW TABLES;

-- Data Retrieval
SELECT columns FROM table WHERE condition;
SELECT DISTINCT column FROM table;
SELECT * FROM table ORDER BY column;
SELECT * FROM table LIMIT n OFFSET m;

-- Filtering
WHERE column = value;
WHERE column IN (value1, value2);
WHERE column BETWEEN value1 AND value2;
WHERE column LIKE 'pattern%';
WHERE column IS NULL;

-- Aggregation
COUNT(*), MIN(), MAX(), AVG(), SUM()
GROUP BY column;
HAVING condition;

-- Joins
INNER JOIN, LEFT JOIN, RIGHT JOIN, CROSS JOIN

-- Data Manipulation
INSERT INTO table VALUES (...);
UPDATE table SET column = value WHERE condition;
DELETE FROM table WHERE condition;

-- Subqueries
SELECT * FROM table WHERE column IN (SELECT ...);
```

### Practice Exercises:

```sql
-- Exercise 1: Find top 5 highest-rated movies
SELECT title, rating FROM movies ORDER BY rating DESC LIMIT 5;

-- Exercise 2: Count movies by genre
SELECT genre, COUNT(*) FROM movies GROUP BY genre;

-- Exercise 3: Movies with above-average rating
SELECT title, rating FROM movies 
WHERE rating > (SELECT AVG(rating) FROM movies);

-- Exercise 4: Update all Drama movies
UPDATE movies SET genre = 'Classic Drama' WHERE genre = 'Drama' AND year < 1980;

-- Exercise 5: Create a view
CREATE VIEW high_rated_movies AS
SELECT title, year, rating FROM movies WHERE rating >= 9.0;
```

---

## Summary: Days 8-12

### Complete Learning Path:

**Day 8**: Database fundamentals, MySQL installation, basic commands
**Day 9**: Filtering (WHERE, LIKE, IN, BETWEEN), Sorting (ORDER BY), Pagination (LIMIT, OFFSET)
**Day 10**: Operators, NULL handling, Aggregate functions
**Day 11**: GROUP BY, HAVING, Joins (INNER, LEFT, RIGHT)
**Day 12**: Subqueries, DML (INSERT, UPDATE, DELETE), DDL (CREATE, ALTER, DROP), DCL (GRANT, REVOKE)

### Key Takeaways:

1. SQL is declarative - you specify WHAT you want, not HOW to get it
2. Always use WHERE to filter before GROUP BY for better performance
3. Joins combine data from multiple tables
4. Aggregate functions work on groups of rows
5. Subqueries enable complex queries
6. Use transactions for data integrity
7. Always backup before DELETE/UPDATE/DROP

---

**SQL Complete Guide - End of Course**
