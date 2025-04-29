# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission
Student Name : BALA B
Reg No : 212224100005


## Scenario Chosen:
University 

## ER Diagram:
![Screenshot 2025-04-29 230414](https://github.com/user-attachments/assets/dc0fe173-9b62-4592-9163-8fe8226ebf28)


## Entities and Attributes:
- Student

Attributes: Student_ID, Name, Email, Phone_No, DOB

- Program

Attributes: Program_ID, Program_Name, Department

- Course

Attributes: Course_ID, Course_Name, Credits

- Prerequisite

Attributes: Course_ID (used to identify prerequisite course)
...

## Relationships and Constraints:
- Enroll

Between: Student and Course

Cardinality: Many-to-Many (M:N) — a student can enroll in many courses, and each course can have many students.

Participation: Partial (not all students may be enrolled in all courses)

- Belongs_To

Between: Student and Program

Cardinality: Many-to-One (M:1) — many students belong to one program.

Participation: Total — every student belongs to a program.

- Has

Between: Program and Course

Cardinality: One-to-Many (1:M) — one program offers many courses.

Participation: Total — each course must belong to some program.

- Can Have

Between: Course and Prerequisite

Cardinality: Many-to-Many (M:N) — a course can have multiple prerequisites, and a prerequisite can apply to multiple courses.

Participation: Optional — not all courses need prerequisites.
...

## Extension (Prerequisite / Billing):
- Prerequisite Modeling:

Represented using a separate entity Prerequisite linked with a relationship Can Have.

It handles many-to-many prerequisites by associating Course_ID with a Prerequisite Course.

This design is flexible and supports the reuse of courses as prerequisites for multiple other courses.

- Billing:

Not included in the given ER diagram. If required, could be added as a separate entity (e.g., Billing with attributes like Amount, Due_Date, etc.) linked to Student.


## Design Choices:
- Entity Selection:

Chose core entities relevant to an academic environment: Student, Course, Program, and Prerequisite.

- Attribute Placement:

Student details (contact, ID, DOB) are grouped with Student.

Program-specific info like department remains with Program.

- Normalization:

Avoided data duplication by using separate entities for Program and Prerequisite.

- Relationships Reflect Real World:

Many-to-many relationships like Enroll and Can Have accurately model how students take multiple courses and courses have multiple prerequisites.

## RESULT:
The ER diagram successfully models the University by clearly representing entities, their attributes, and real-life relationships for efficient data management.
