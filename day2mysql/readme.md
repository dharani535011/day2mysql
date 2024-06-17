# Design DB model for Guvi Zen class
>first i created the databases in mysql workbench
>then created the required normalized tables


# Created Tables :
![](images/Screenshot%20(32).png)
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    DateOfBirth DATE,
    Email VARCHAR(100),
    PhoneNumber VARCHAR(15)
);

CREATE TABLE Courses (
    CourseID INT PRIMARY KEY,
    CourseName VARCHAR(100),
    CourseDescription TEXT,
    Credits INT
);

CREATE TABLE Teachers (
    TeacherID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100),
    PhoneNumber VARCHAR(15)
);

CREATE TABLE Classes (
    ClassID INT PRIMARY KEY,
    CourseID INT,
    TeacherID INT,
    Semester VARCHAR(10),
    Schedule VARCHAR(50),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID),
    FOREIGN KEY (TeacherID) REFERENCES Teachers(TeacherID)
);

CREATE TABLE Enrollments (
    EnrollmentID INT PRIMARY KEY,
    StudentID INT,
    CourseID INT,
    EnrollmentDate DATE,
    Grade CHAR(2),
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);

and added some datas in the tables..


and some example questions and thier ans..

1. List all students enrolled in the "Data Science" course.
![](images/Screenshot%20(33).png)
2. Find the names of teachers who are teaching "Cloud Computing" in the "Fall 2024" semester.
![](images/Screenshot%20(34).png)
3. List the courses that student "John Doe" is enrolled in along with the grades.
![](images/Screenshot%20(35).png)
4. Retrieve the schedule and semester of all classes taught by teacher "Alice Green".
![](images/Screenshot%20(36).png)
5. Count the number of students enrolled in each course.
![](images/Screenshot%20(37).png)