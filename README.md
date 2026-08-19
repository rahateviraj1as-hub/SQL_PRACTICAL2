Database Schema Explanation
This SQL script defines a relational database schema for an academic management system, creating four interconnected tables: department, student, course, and enrollment.
1. department Table
Stores information about academic departments.
dept_id: Integer primary key that uniquely identifies each department.
dept_name: Text field up to 50 characters storing the department name. It is enforced as both UNIQUE (no duplicate names allowed) and NOT NULL (cannot be empty).
2. student Table
Stores personal and academic details of students.
roll_no: Integer primary key identifying each student uniquely.
name: Student name, restricted to 50 characters max and mandatory (NOT NULL).
email: Unique email address for each student.
aadhar_no: 12-character unique national identification number.
dept_id: Foreign key linking the student to their respective record in the department table.
3. course Table
Stores details of available courses.
course_id: Unique integer primary key for each course.
course_name: Course name up to 50 characters; mandatory (NOT NULL).
dept_id: Foreign key mapping the course to the department offering it.
4. enrollment Table
Acts as a junction table managing student course registrations, semester progression, and grades.
roll_no & course_id: Foreign keys linking back to the student and course tables.
semester: Restricted via a CHECK constraint to values strictly between 1 and 8.
grade: 2-character string storing academic performance (e.g., 'A+', 'B').
Composite Primary Key: Combination of (roll_no, course_id, semester) ensures a student cannot enroll in the exact same course twice within the same semester.
