# Student Management System – SQL Project

This project demonstrates how to design and query a **Student Management Database** using **MySQL**. It simulates a simple academic environment where students are enrolled in courses and receive marks, and various SQL queries are used to extract useful insights.

---

##  Project Objectives

- Design a normalized database with tables for students, courses, and marks.
- Insert and manage sample student data.
- Write SQL queries to:
  - View student records
  - Join tables for meaningful relationships
  - Calculate average marks
  - Filter students based on performance

---

##  Database Schema

- **`student`**: stores student details (ID, name, age, gender)
- **`courses`**: contains course IDs and names
- **`mark`**: records marks per student per course with foreign keys

##  Skills Demonstrated

- Relational database design
- Data normalization
- Use of JOINs, GROUP BY, aggregate functions, and WHERE clauses
- Data filtering and basic analysis
  
# Q&A

- create a table
- Insert Sample Data
- Write Queries**Get all students
- List students and their marks
- Find average marks per student
- Find students with marks > 80



## Code

 
``` sql

##create a table

CREATE DATABASE Student_Management_System;
USE Student_Management_System;

CREATE TABLE student
( student_id INT PRIMARY KEY,
Name_ VARCHAR(50),
Age INT ,
Gender VARCHAR (20));

CREATE TABLE courses
( Course_id INT PRIMARY KEY,
course_name VARCHAR(50));

CREATE TABLE mark
(mark_id INT PRIMARY KEY,
student_id INT ,
FOREIGN KEY(student_id) REFERENCES student(student_id),
Course_id INT,
FOREIGN KEY(Course_id) REFERENCES courses(Course_id ),
mark INT);


## 2. *Insert Sample Data*

INSERT INTO student
VALUES (1, 'Alice', 20, 'Female'),
		(2, 'Bob', 21, 'Male'),
	    (3, 'Charlie', 22, 'Male');
        
INSERT INTO courses
VALUES (101, 'Math'),
	   (102, 'Science');

INSERT INTO mark
VALUES (1, 1, 101, 85),
		(2, 1, 102, 90),
		(3, 2, 101, 75),
		(4, 3, 102, 60);
        

## 3. *Write Queries**Get all students:*        

SELECT * FROM STUDENT;


##List students and their marks:*

SELECT s.name_, c.course_name, m.mark
FROM Mark m
JOIN Student s ON m.student_id = s.student_id
JOIN Courses c ON m.course_id = c.course_id;


## Find average marks per student:*

SELECT s.name_, AVG(m.mark) AS average_marks
FROM Mark m
JOIN Student s ON m.student_id = s.student_id
GROUP BY s.name_;


##Find students with marks > 80:*

SELECT s.name_,m.mark
FROM mark m
JOIN student s ON m.student_id = s.student_id
WHERE mark > 80;
```
## About Me
Rithika R
📌 Data Analyst | SQL | Python | Tableau | Power BI | Excel
🔗 ![LinkedIn](https://www.linkedin.com/in/rithika-ramalingam-r-02714b244/) • ![GitHub](https://github.com/settings/profile)






