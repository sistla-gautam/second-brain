## Insertion scripts
```SQL
-- Create Tables
CREATE TABLE School (
    school_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    curriculum VARCHAR(50) NOT NULL
);

CREATE TABLE SchoolCalendar (
    calendar_id INT PRIMARY KEY,
    school_id INT,
    holiday_date DATE NOT NULL,
    holiday_description VARCHAR(200),
    FOREIGN KEY (school_id) REFERENCES School(school_id)
);

CREATE TABLE Grade (
    grade_id INT PRIMARY KEY,
    school_id INT,
    grade_number INT NOT NULL CHECK (grade_number BETWEEN 1 AND 12),
    FOREIGN KEY (school_id) REFERENCES School(school_id)
);

CREATE TABLE Subject (
    subject_id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    is_language BIT DEFAULT 0
);

CREATE TABLE GradeSubject (
    grade_id INT,
    subject_id INT,
    PRIMARY KEY (grade_id, subject_id),
    FOREIGN KEY (grade_id) REFERENCES Grade(grade_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id)
);

CREATE TABLE Staff (
    staff_id INT PRIMARY KEY,
    school_id INT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    is_teaching BIT DEFAULT 0,
    phone_number VARCHAR(15),
    FOREIGN KEY (school_id) REFERENCES School(school_id)
);

CREATE TABLE TeacherSubject (
    staff_id INT,
    subject_id INT,
    PRIMARY KEY (staff_id, subject_id),
    FOREIGN KEY (staff_id) REFERENCES Staff(staff_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id)
);

CREATE TABLE Section (
    section_id INT PRIMARY KEY,
    grade_id INT,
    section_name VARCHAR(10) NOT NULL,
    class_teacher_id INT,
    FOREIGN KEY (grade_id) REFERENCES Grade(grade_id),
    FOREIGN KEY (class_teacher_id) REFERENCES Staff(staff_id)
);

CREATE TABLE Student (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    date_of_birth DATE NOT NULL,
    phone_number VARCHAR(15),
    section_id INT,
    FOREIGN KEY (section_id) REFERENCES Section(section_id)
);

CREATE TABLE SectionTeacher (
    section_id INT,
    staff_id INT,
    subject_id INT,
    PRIMARY KEY (section_id, staff_id, subject_id),
    FOREIGN KEY (section_id) REFERENCES Section(section_id),
    FOREIGN KEY (staff_id) REFERENCES Staff(staff_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id)
);

CREATE TABLE Timetable (
    timetable_id INT PRIMARY KEY,
    section_id INT,
    day_of_week INT CHECK (day_of_week BETWEEN 1 AND 5),
    period_number INT CHECK (period_number BETWEEN 1 AND 8),
    subject_id INT,
    teacher_id INT,
    FOREIGN KEY (section_id) REFERENCES Section(section_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id),
    FOREIGN KEY (teacher_id) REFERENCES Staff(staff_id)
);

-- Insert Sample Data
INSERT INTO School (school_id, name, curriculum) VALUES
(1, 'Springfield High', 'International');

INSERT INTO Subject (subject_id, name, is_language) VALUES
(1, 'Mathematics', 0),
(2, 'English', 1),
(3, 'Physics', 0),
(4, 'Chemistry', 0),
(5, 'Biology', 0),
(6, 'History', 0),
(7, 'Geography', 0),
(8, 'French', 1),
(9, 'Computer Science', 0);

INSERT INTO Staff (staff_id, school_id, first_name, last_name, is_teaching, phone_number) VALUES
(1, 1, 'John', 'Smith', 1, '1234567890'),
(2, 1, 'Mary', 'Johnson', 1, '2345678901'),
(3, 1, 'Robert', 'Williams', 1, '3456789012'),
(4, 1, 'Sarah', 'Brown', 1, '4567890123'),
(5, 1, 'Michael', 'Davis', 1, '5678901234'),
(6, 1, 'James', 'Wilson', 0, '6789012345'),
(7, 1, 'Patricia', 'Miller', 0, '7890123456');

INSERT INTO Grade (grade_id, school_id, grade_number) VALUES
(1, 1, 9),
(2, 1, 10),
(3, 1, 11),
(4, 1, 12);

INSERT INTO Section (section_id, grade_id, section_name, class_teacher_id) VALUES
(1, 1, 'A', 1),
(2, 1, 'B', 2),
(3, 2, 'A', 3),
(4, 2, 'B', 4),
(5, 3, 'A', 5);

INSERT INTO TeacherSubject (staff_id, subject_id) VALUES
(1, 1), -- John teaches Math
(1, 3), -- John teaches Physics
(2, 2), -- Mary teaches English
(3, 4), -- Robert teaches Chemistry
(4, 5), -- Sarah teaches Biology
(5, 8); -- Michael teaches French

INSERT INTO Student (student_id, first_name, last_name, date_of_birth, phone_number, section_id) VALUES
(1, 'Alice', 'Anderson', '2009-03-15', '8901234567', 1),
(2, 'Bob', 'Baker', '2009-05-20', '9012345678', 1),
(3, 'Charlie', 'Clark', '2009-07-10', '0123456789', 2),
(4, 'Diana', 'Davis', '2008-04-25', '1234567890', 3),
(5, 'Eric', 'Evans', '2008-08-30', '2345678901', 3),
(6, 'Frank', 'Fisher', '2007-06-12', '3456789012', 4);

INSERT INTO GradeSubject (grade_id, subject_id)
SELECT g.grade_id, s.subject_id
FROM Grade g
CROSS JOIN Subject s
WHERE g.grade_number IN (9, 10, 11, 12);

INSERT INTO SectionTeacher (section_id, staff_id, subject_id)
SELECT s.section_id, ts.staff_id, ts.subject_id
FROM Section s
CROSS JOIN TeacherSubject ts;

INSERT INTO Timetable (timetable_id, section_id, day_of_week, period_number, subject_id, teacher_id) VALUES
(1, 1, 1, 1, 1, 1), -- Math
(2, 1, 1, 2, 2, 2), -- English
(3, 1, 1, 3, 3, 1), -- Physics
(4, 1, 1, 4, 4, 3), -- Chemistry
(5, 1, 1, 5, 5, 4), -- Biology
(6, 1, 1, 6, 8, 5), -- French
(7, 1, 1, 7, 1, 1), -- Math
(8, 1, 1, 8, 2, 2); -- English

INSERT INTO SchoolCalendar (calendar_id, school_id, holiday_date, holiday_description) VALUES
(1, 1, '2025-01-01', 'New Year''s Day'),
(2, 1, '2025-04-15', 'Spring Break'),
(3, 1, '2025-07-04', 'Independence Day'),
(4, 1, '2025-12-25', 'Christmas');
```

---
## CRUD + queries

```SQL
-- CRUD Operations

-- School CRUD
INSERT INTO School (school_id, name, curriculum) 
VALUES (2, 'New School', 'National');

UPDATE School 
SET curriculum = 'International Baccalaureate' 
WHERE school_id = 2;

DELETE FROM School 
WHERE school_id = 2;

SELECT * FROM School;

-- Grade CRUD
INSERT INTO Grade (grade_id, school_id, grade_number) 
VALUES (5, 1, 8);

UPDATE Grade 
SET grade_number = 7 
WHERE grade_id = 5;

DELETE FROM Grade 
WHERE grade_id = 5;

SELECT * FROM Grade;

-- Section CRUD
INSERT INTO Section (section_id, grade_id, section_name, class_teacher_id) 
VALUES (6, 1, 'C', 3);

UPDATE Section 
SET class_teacher_id = 4 
WHERE section_id = 6;

DELETE FROM Section 
WHERE section_id = 6;

SELECT * FROM Section;

-- Student CRUD
INSERT INTO Student (student_id, first_name, last_name, date_of_birth, phone_number, section_id) 
VALUES (7, 'New', 'Student', '2009-01-01', '1234567890', 1);

UPDATE Student 
SET phone_number = '9999999999' 
WHERE student_id = 7;

DELETE FROM Student 
WHERE student_id = 7;

SELECT * FROM Student;

-- Staff CRUD
INSERT INTO Staff (staff_id, school_id, first_name, last_name, is_teaching, phone_number) 
VALUES (8, 1, 'New', 'Teacher', 1, '1234567890');

UPDATE Staff 
SET phone_number = '9999999999' 
WHERE staff_id = 8;

DELETE FROM Staff 
WHERE staff_id = 8;

SELECT * FROM Staff;

-- QURIES

-- 1. How many staff members are there in the school?
SELECT COUNT(*) as total_staff
FROM Staff
WHERE school_id = 1;

-- 2. How many staff members are teachers?
SELECT COUNT(*) as total_teachers
FROM Staff
WHERE school_id = 1 AND is_teaching = 1;

-- 3. For each teacher, report the number of subjects they are teaching
SELECT 
    s.staff_id,
    s.first_name + ' ' + s.last_name as teacher_name,
    COUNT(DISTINCT ts.subject_id) as subjects_count
FROM Staff s
LEFT JOIN TeacherSubject ts ON s.staff_id = ts.staff_id
WHERE s.is_teaching = 1
GROUP BY s.staff_id, s.first_name, s.last_name;

-- 4. Which subject is taught by the most number of teachers?
SELECT TOP 1
    s.name as subject_name,
    COUNT(DISTINCT ts.staff_id) as teachers_count
FROM Subject s
JOIN TeacherSubject ts ON s.subject_id = ts.subject_id
GROUP BY s.subject_id, s.name
ORDER BY teachers_count DESC;

-- 5. How many students are in a given section?
DECLARE @section_id INT = 1;
SELECT 
    COUNT(*) as student_count
FROM Student
WHERE section_id = @section_id;

-- 6. What fraction of the staff are teachers?
SELECT 
    CAST(SUM(CASE WHEN is_teaching = 1 THEN 1 ELSE 0 END) AS FLOAT) / 
    COUNT(*) as teacher_fraction
FROM Staff
WHERE school_id = 1;

-- 7. How many students are in a given grade?
DECLARE @grade_id INT = 1;
SELECT 
    COUNT(*) as student_count
FROM Student s
JOIN Section sec ON s.section_id = sec.section_id
WHERE sec.grade_id = @grade_id;

-- 8. Who is the class teacher of a given student?
DECLARE @student_id INT = 1;
SELECT 
    st.first_name + ' ' + st.last_name as class_teacher_name
FROM Student s
JOIN Section sec ON s.section_id = sec.section_id
JOIN Staff st ON sec.class_teacher_id = st.staff_id
WHERE s.student_id = @student_id;

-- 9. What subjects does a given grade have?
DECLARE @grade_id_for_subjects INT = 1;
SELECT 
    s.name as subject_name
FROM Subject s
JOIN GradeSubject gs ON s.subject_id = gs.subject_id
WHERE gs.grade_id = @grade_id_for_subjects;

-- 10. How many sections is a given teacher teaching?
DECLARE @teacher_id INT = 1;
SELECT 
    COUNT(DISTINCT section_id) as sections_count
FROM SectionTeacher
WHERE staff_id = @teacher_id;

-- 11. What is the average number of sections a teacher is teaching?
SELECT 
    AVG(sections_per_teacher) as avg_sections
FROM (
    SELECT 
        staff_id,
        COUNT(DISTINCT section_id) as sections_per_teacher
    FROM SectionTeacher
    GROUP BY staff_id
) as teacher_sections;

-- 12. In a given week, how many hours is a teacher teaching?
DECLARE @week_teacher_id INT = 1;
SELECT 
    COUNT(*) as total_periods
FROM Timetable
WHERE teacher_id = @week_teacher_id;

-- 13. For a given section, how many hours of each subject is being taught per week?
DECLARE @section_id_for_hours INT = 1;
SELECT 
    s.name as subject_name,
    COUNT(*) as periods_per_week
FROM Timetable t
JOIN Subject s ON t.subject_id = s.subject_id
WHERE t.section_id = @section_id_for_hours
GROUP BY s.subject_id, s.name
ORDER BY periods_per_week DESC;

-- 14. How many language teachers are there in the school?
SELECT 
    COUNT(DISTINCT ts.staff_id) as language_teachers_count
FROM TeacherSubject ts
JOIN Subject s ON ts.subject_id = s.subject_id
JOIN Staff st ON ts.staff_id = st.staff_id
WHERE s.is_language = 1 AND st.school_id = 1;
```

---
## Complete script

```SQL
CREATE TABLE School (
    school_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    curriculum VARCHAR(50) NOT NULL
);

CREATE TABLE SchoolCalendar (
    calendar_id INT PRIMARY KEY,
    school_id INT,
    holiday_date DATE NOT NULL,
    holiday_description VARCHAR(200),
    FOREIGN KEY (school_id) REFERENCES School(school_id)
);

CREATE TABLE Grade (
    grade_id INT PRIMARY KEY,
    school_id INT,
    grade_number INT NOT NULL CHECK (grade_number BETWEEN 1 AND 12),
    FOREIGN KEY (school_id) REFERENCES School(school_id)
);

CREATE TABLE Subject (
    subject_id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    is_language BIT DEFAULT 0
);

CREATE TABLE GradeSubject (
    grade_id INT,
    subject_id INT,
    PRIMARY KEY (grade_id, subject_id),
    FOREIGN KEY (grade_id) REFERENCES Grade(grade_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id)
);

CREATE TABLE Staff (
    staff_id INT PRIMARY KEY,
    school_id INT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    is_teaching BIT DEFAULT 0,
    phone_number VARCHAR(15),
    FOREIGN KEY (school_id) REFERENCES School(school_id)
);

CREATE TABLE TeacherSubject (
    staff_id INT,
    subject_id INT,
    PRIMARY KEY (staff_id, subject_id),
    FOREIGN KEY (staff_id) REFERENCES Staff(staff_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id)
);

CREATE TABLE Section (
    section_id INT PRIMARY KEY,
    grade_id INT,
    section_name VARCHAR(10) NOT NULL,
    class_teacher_id INT,
    FOREIGN KEY (grade_id) REFERENCES Grade(grade_id),
    FOREIGN KEY (class_teacher_id) REFERENCES Staff(staff_id)
);

CREATE TABLE Student (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    date_of_birth DATE NOT NULL,
    phone_number VARCHAR(15),
    section_id INT,
    FOREIGN KEY (section_id) REFERENCES Section(section_id)
);

CREATE TABLE SectionTeacher (
    section_id INT,
    staff_id INT,
    subject_id INT,
    PRIMARY KEY (section_id, staff_id, subject_id),
    FOREIGN KEY (section_id) REFERENCES Section(section_id),
    FOREIGN KEY (staff_id) REFERENCES Staff(staff_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id)
);

CREATE TABLE Timetable (
    timetable_id INT PRIMARY KEY,
    section_id INT,
    day_of_week INT CHECK (day_of_week BETWEEN 1 AND 5),
    period_number INT CHECK (period_number BETWEEN 1 AND 8),
    subject_id INT,
    teacher_id INT,
    FOREIGN KEY (section_id) REFERENCES Section(section_id),
    FOREIGN KEY (subject_id) REFERENCES Subject(subject_id),
    FOREIGN KEY (teacher_id) REFERENCES Staff(staff_id)
);

-- Insert Sample Data
INSERT INTO School (school_id, name, curriculum) VALUES
(1, 'Springfield High', 'International');

INSERT INTO Subject (subject_id, name, is_language) VALUES
(1, 'Mathematics', 0),
(2, 'English', 1),
(3, 'Physics', 0),
(4, 'Chemistry', 0),
(5, 'Biology', 0),
(6, 'History', 0),
(7, 'Geography', 0),
(8, 'French', 1),
(9, 'Computer Science', 0);

INSERT INTO Staff (staff_id, school_id, first_name, last_name, is_teaching, phone_number) VALUES
(1, 1, 'John', 'Smith', 1, '1234567890'),
(2, 1, 'Mary', 'Johnson', 1, '2345678901'),
(3, 1, 'Robert', 'Williams', 1, '3456789012'),
(4, 1, 'Sarah', 'Brown', 1, '4567890123'),
(5, 1, 'Michael', 'Davis', 1, '5678901234'),
(6, 1, 'James', 'Wilson', 0, '6789012345'),
(7, 1, 'Patricia', 'Miller', 0, '7890123456');

INSERT INTO Grade (grade_id, school_id, grade_number) VALUES
(1, 1, 9),
(2, 1, 10),
(3, 1, 11),
(4, 1, 12);

INSERT INTO Section (section_id, grade_id, section_name, class_teacher_id) VALUES
(1, 1, 'A', 1),
(2, 1, 'B', 2),
(3, 2, 'A', 3),
(4, 2, 'B', 4),
(5, 3, 'A', 5);

INSERT INTO TeacherSubject (staff_id, subject_id) VALUES
(1, 1), -- John teaches Math
(1, 3), -- John teaches Physics
(2, 2), -- Mary teaches English
(3, 4), -- Robert teaches Chemistry
(4, 5), -- Sarah teaches Biology
(5, 8); -- Michael teaches French

INSERT INTO Student (student_id, first_name, last_name, date_of_birth, phone_number, section_id) VALUES
(1, 'Alice', 'Anderson', '2009-03-15', '8901234567', 1),
(2, 'Bob', 'Baker', '2009-05-20', '9012345678', 1),
(3, 'Charlie', 'Clark', '2009-07-10', '0123456789', 2),
(4, 'Diana', 'Davis', '2008-04-25', '1234567890', 3),
(5, 'Eric', 'Evans', '2008-08-30', '2345678901', 3),
(6, 'Frank', 'Fisher', '2007-06-12', '3456789012', 4);

INSERT INTO GradeSubject (grade_id, subject_id)
SELECT g.grade_id, s.subject_id
FROM Grade g
CROSS JOIN Subject s
WHERE g.grade_number IN (9, 10, 11, 12);

INSERT INTO SectionTeacher (section_id, staff_id, subject_id)
SELECT s.section_id, ts.staff_id, ts.subject_id
FROM Section s
CROSS JOIN TeacherSubject ts;

INSERT INTO Timetable (timetable_id, section_id, day_of_week, period_number, subject_id, teacher_id) VALUES
(1, 1, 1, 1, 1, 1), -- Math
(2, 1, 1, 2, 2, 2), -- English
(3, 1, 1, 3, 3, 1), -- Physics
(4, 1, 1, 4, 4, 3), -- Chemistry
(5, 1, 1, 5, 5, 4), -- Biology
(6, 1, 1, 6, 8, 5), -- French
(7, 1, 1, 7, 1, 1), -- Math
(8, 1, 1, 8, 2, 2); -- English

INSERT INTO SchoolCalendar (calendar_id, school_id, holiday_date, holiday_description) VALUES
(1, 1, '2025-01-01', 'New Year''s Day'),
(2, 1, '2025-04-15', 'Spring Break'),
(3, 1, '2025-07-04', 'Independence Day'),
(4, 1, '2025-12-25', 'Christmas');
-- CRUD Operations

-- School CRUD
INSERT INTO School (school_id, name, curriculum) 
VALUES (2, 'New School', 'National');

UPDATE School 
SET curriculum = 'International Baccalaureate' 
WHERE school_id = 2;

DELETE FROM School 
WHERE school_id = 2;

-- SELECT * FROM School;

-- Grade CRUD
INSERT INTO Grade (grade_id, school_id, grade_number) 
VALUES (5, 1, 8);

UPDATE Grade 
SET grade_number = 7 
WHERE grade_id = 5;

DELETE FROM Grade 
WHERE grade_id = 5;

-- SELECT * FROM Grade;

-- Section CRUD
INSERT INTO Section (section_id, grade_id, section_name, class_teacher_id) 
VALUES (6, 1, 'C', 3);

UPDATE Section 
SET class_teacher_id = 4 
WHERE section_id = 6;

DELETE FROM Section 
WHERE section_id = 6;

-- SELECT * FROM Section;

-- Student CRUD
INSERT INTO Student (student_id, first_name, last_name, date_of_birth, phone_number, section_id) 
VALUES (7, 'New', 'Student', '2009-01-01', '1234567890', 1);

UPDATE Student 
SET phone_number = '9999999999' 
WHERE student_id = 7;

DELETE FROM Student 
WHERE student_id = 7;

-- SELECT * FROM Student;

-- Staff CRUD
INSERT INTO Staff (staff_id, school_id, first_name, last_name, is_teaching, phone_number) 
VALUES (8, 1, 'New', 'Teacher', 1, '1234567890');

UPDATE Staff 
SET phone_number = '9999999999' 
WHERE staff_id = 8;

DELETE FROM Staff 
WHERE staff_id = 8;

-- SELECT * FROM Staff;

-- REPORTS

-- 1. How many staff members are there in the school?
PRINT 'How many staff members are there in the school?';
SELECT COUNT(*) as total_staff
FROM Staff
WHERE school_id = 1;

-- 2. How many staff members are teachers?
PRINT 'How many staff members are teachers?';
SELECT COUNT(*) as total_teachers
FROM Staff
WHERE school_id = 1 AND is_teaching = 1;

-- 3. For each teacher, report the number of subjects they are teaching
PRINT 'For each teacher, report the number of subjets they are teaching';
SELECT 
    s.staff_id,
    s.first_name + ' ' + s.last_name as teacher_name,
    COUNT(DISTINCT ts.subject_id) as subjects_count
FROM Staff s
LEFT JOIN TeacherSubject ts ON s.staff_id = ts.staff_id
WHERE s.is_teaching = 1
GROUP BY s.staff_id, s.first_name, s.last_name;

-- 4. Which subject is taught by the most number of teachers?
PRINT 'Which subject is taught by the most number of teachers?';
SELECT TOP 1
    s.name as subject_name,
    COUNT(DISTINCT ts.staff_id) as teachers_count
FROM Subject s
JOIN TeacherSubject ts ON s.subject_id = ts.subject_id
GROUP BY s.subject_id, s.name
ORDER BY teachers_count DESC;

-- 5. How many students are in a given section?
PRINT 'How many students are in a given section?';
DECLARE @section_id INT = 1;
SELECT 
    COUNT(*) as student_count
FROM Student
WHERE section_id = @section_id;

-- 6. What fraction of the staff are teachers?
PRINT 'What fraction of the staff are teachers?';
SELECT 
    CAST(SUM(CASE WHEN is_teaching = 1 THEN 1 ELSE 0 END) AS FLOAT) / 
    COUNT(*) as teacher_fraction
FROM Staff
WHERE school_id = 1;

-- 7. How many students are in a given grade?
PRINT 'How many students are in a given grade?';
DECLARE @grade_id INT = 1;
SELECT 
    COUNT(*) as student_count
FROM Student s
JOIN Section sec ON s.section_id = sec.section_id
WHERE sec.grade_id = @grade_id;

-- 8. Who is the class teacher of a given student?
PRINT 'Who is the class teacher of a given student?';
DECLARE @student_id INT = 1;
SELECT 
    st.first_name + ' ' + st.last_name as class_teacher_name
FROM Student s
JOIN Section sec ON s.section_id = sec.section_id
JOIN Staff st ON sec.class_teacher_id = st.staff_id
WHERE s.student_id = @student_id;

-- 9. What subjects does a given grade have?
PRINT 'What subjects does a given grade have?';
DECLARE @grade_id_for_subjects INT = 1;
SELECT 
    s.name as subject_name
FROM Subject s
JOIN GradeSubject gs ON s.subject_id = gs.subject_id
WHERE gs.grade_id = @grade_id_for_subjects;

-- 10. How many sections is a given teacher teaching?
PRINT 'How many sections is a given teacher teaching?';
DECLARE @teacher_id INT = 1;
SELECT 
    COUNT(DISTINCT section_id) as sections_count
FROM SectionTeacher
WHERE staff_id = @teacher_id;

-- 11. What is the average number of sections a teacher is teaching?
PRINT 'What is the average number of sections a teacher is teaching?';
SELECT 
    AVG(sections_per_teacher) as avg_sections
FROM (
    SELECT 
        staff_id,
        COUNT(DISTINCT section_id) as sections_per_teacher
    FROM SectionTeacher
    GROUP BY staff_id
) as teacher_sections;

-- 12. In a given week, how many hours is a teacher teaching?
PRINT 'In a given week, how many hours is a teacher teaching?';
DECLARE @week_teacher_id INT = 1;
SELECT 
    COUNT(*) as total_periods
FROM Timetable
WHERE teacher_id = @week_teacher_id;

-- 13. For a given section, how many hours of each subject is being taught per week?
PRINT 'For a given section, how many hours of each subject is being taught per week?';
DECLARE @section_id_for_hours INT = 1;
SELECT 
    s.name as subject_name,
    COUNT(*) as periods_per_week
FROM Timetable t
JOIN Subject s ON t.subject_id = s.subject_id
WHERE t.section_id = @section_id_for_hours
GROUP BY s.subject_id, s.name
ORDER BY periods_per_week DESC;

-- 14. How many language teachers are there in the school?
PRINT 'How many language teachers are there in the school?';
SELECT 
    COUNT(DISTINCT ts.staff_id) as language_teachers_count
FROM TeacherSubject ts
JOIN Subject s ON ts.subject_id = s.subject_id
JOIN Staff st ON ts.staff_id = st.staff_id
WHERE s.is_language = 1 AND st.school_id = 1;
```