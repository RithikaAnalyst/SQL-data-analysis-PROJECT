# 🎓 Student Management System – SQL Project

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

```sql
CREATE TABLE student (
  student_id INT PRIMARY KEY,
  Name_ VARCHAR(50),
  Age INT,
  Gender VARCHAR(20)
);

CREATE TABLE courses (
  Course_id INT PRIMARY KEY,
  course_name VARCHAR(50)
);

CREATE TABLE mark (
  mark_id INT PRIMARY KEY,
  student_id INT,
  Course_id INT,
  mark INT,
  FOREIGN KEY(student_id) REFERENCES student(student_id),
  FOREIGN KEY(Course_id) REFERENCES courses(Course_id)
);



