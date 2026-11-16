# Mini Learning Management System (Mini LMS)

A console-based Learning Management System built using **Java and Object-Oriented Programming principles**. The application models instructors, students, courses, modules, lessons, and student enrollments.

The project focuses on applying OOP concepts and basic software design patterns to build a modular and maintainable application.

## Features

- **User Management:** Supports students and instructors using a common `User` base class.
- **Course Management:** Create courses and associate them with instructors.
- **Module and Lesson Management:** Organize courses into modules, with lessons inside each module.
- **Student Enrollment:** Enroll students into courses.
- **Progress Tracking:** Track completed lessons and calculate course completion percentages.
- **Enrollment Status:** Automatically update enrollment status from `ACTIVE` to `COMPLETED` when all lessons are finished.
- **Notification System:** Supports email and SMS notification channels.
- **In-Memory Repositories:** Store and retrieve courses and enrollments using Java collections.

## Technologies Used

- Java
- Object-Oriented Programming (OOP)
- Java Collections Framework
- Git and GitHub

## Project Structure

```text
mini_lms/
│
├── User.java
├── Instructor.java
├── student.java
├── course.java
├── module.java
├── lesson.java
├── enrollment.java
│
├── EnrollmentService.java
│
├── ICourseRepository.java
├── IEnrollmentRepository.java
├── InMemoryCourseRepository.java
├── InMemoryEnrollmentRepository.java
│
├── INotificationChannel.java
└── Main.java
```

## OOP Concepts and Design Principles

This project demonstrates:

- **Encapsulation:** Model classes manage their internal state through methods.
- **Inheritance:** `Instructor` and `student` extend the common `User` class.
- **Abstraction:** Interfaces define contracts for repositories and notification channels.
- **Polymorphism:** Different notification implementations can be used through `INotificationChannel`.
- **Dependency Injection:** `EnrollmentService` receives repository and notification dependencies through its constructor.
- **Repository Pattern:** Separates data storage operations from business logic.

## How Progress Tracking Works

The enrollment maintains a set of completed lesson IDs to avoid counting the same lesson multiple times.

Course progress is calculated using:

```text
Progress = (Completed Lessons / Total Lessons) * 100
```

When all lessons are completed, the enrollment status changes to `COMPLETED`.

## Running the Project

1. Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/mini-lms.git
```

2. Navigate to the project directory:

```bash
cd mini-lms
```

3. Compile the Java files:

```bash
javac -d out mini_lms/*.java
```

4. Run the application:

```bash
java -cp out mini_lms.Main
```

## Sample Output

```text
Email to Sai: hi
Initial status: ACTIVE
Progress: 50.0%
Status: ACTIVE
Final status: COMPLETED
Final progress: 100.0%
```

## Future Improvements

- Introduce unique enrollment IDs.
- Support multiple course enrollments per student.
- Add persistent database storage.
- Improve course and instructor relationship management.
- Add unit testing and input validation.
- Introduce a REST API for application access.
