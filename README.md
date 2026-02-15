# University Course Registration System

This project is a modern web-based prototype for course registration, built with **Node.js**, **Express**, **MongoDB**, and **EJS**. It addresses key problems such as scheduling conflicts, real-time seat availability, prerequisite tracking, and more.

> [!NOTE]
> This project is a **forked/cloned** repository for research and assignment purposes (Software Reengineering - Assignment #1: Code Smell Analysis).

---

## Table of Contents

1. [Features](#features)
2. [Tech Stack](#tech-stack)
3. [Project Structure](#project-structure)
4. [Installation & Setup](#installation--setup)
5. [Docker Execution](#docker-execution)
6. [SonarQube Analysis](#sonarqube-analysis)
7. [GitHub Repository](#github-repository)
8. [License](#license)

---

## Features

### 1. **Admin Features**

- **Login**: Admins authenticate with a username & password.
- **Course Management**: Add, update, or delete courses; set prerequisites; manage scheduling (days, times).
- **Student Management**: View & override student registrations; remove or mark courses as completed for any student.
- **Seat Management**: Adjust capacity for each course; see real-time seat availability.
- **Reports**:
  - Students registered for a specific course
  - Courses with available seats
  - Students missing prerequisites

### 2. **Student Features**

- **Login**: Students log in with their roll number & password (no sign-up).
- **View & Register Courses**: Filter courses by department, level, or time of day; see real-time seat counts.
- **Weekly Schedule**: An interactive table that updates automatically when registering or dropping a course.
- **Prerequisite Checks**: Prevents registration if prerequisites aren’t completed (configurable logic).
- **Mark Course as Completed**: Admin or student can mark courses as completed, removing them from “in-progress” schedule.

### 3. **Real-Time Updates**

- **Seat Availability**: A polling mechanism updates seat counts every 10 seconds without refreshing the page.
- **Interactive Schedule**: Registering or dropping a course re-renders the weekly schedule on the fly.

---

## Tech Stack

- **Node.js** & **Express**: Backend server and routing.
- **MongoDB** & **Mongoose**: Database for courses, students, admin data.
- **EJS**: Templating engine for dynamic views.
- **Docker**: For containerized deployment.
- **SonarQube**: For static code analysis and code smell detection.

---

## Project Structure

```
├── config
│   └── db.js                # MongoDB connection setup
├── middleware
│   └── login.js             # Login & access control middleware
├── models
│   ├── admin.js
│   ├── course.js
│   └── student.js
├── public
│   ├── css
│   │   └── studentDashboard.css  # Main stylesheet
│   └── js
│       └── script.js            # Main client-side JS
├── routes
│   ├── admin.js
│   └── student.js
├── views
│   ├── admin
│   │   └── admindashboard.ejs
│   ├── student
│   │   └── studentDashboard.ejs
├── .env                # Environment variables
├── server.js           # Entry point for Express
├── Dockerfile          # Docker configuration
├── sonar-project.properties # SonarQube configuration
├── package.json
└── README.md           # Project documentation
```

---

## Installation & Setup

1. **Clone** the repository:
   ```bash
   git clone https://github.com/ShaheeraMalik/UniversityCourseRegistrationSystem.git
   ```
2. **Install** dependencies:
   ```bash
   npm install
   ```
3. **Configure** environment:
   - Create a `.env` file in the root directory.
   - Add `MONGO_URI`, `PORT`, and any other variables.
4. **Run** the server:
   ```bash
   npm start
   ```

---

## Docker Execution

The project includes a `Dockerfile` for easy containerization.

### Prerequisites

- Docker installed and running.

### Steps to Run

1. **Build the Docker Image**:
   ```bash
   docker build -t university-course-registration .
   ```
2. **Run the Container**:
   ```bash
   docker run -p 5000:5000 --env-file .env university-course-registration
   ```
3. **Access the Application**:
   Open [http://localhost:5000](http://localhost:5000) in your browser.

---

## SonarQube Analysis

The project is configured for static code analysis using SonarQube via the `sonar-project.properties` file.

### Steps to Analyze

1. **Ensure SonarQube is Running**:
   You should have a SonarQube instance available (local or server).
2. **Install Sonar-Scanner**:
   Ensure you have the `sonar-scanner` CLI tool installed.
3. **Run the Scan**:
   Execute the following command in the project root:
   ```bash
   sonar-scanner \
     -Dsonar.projectKey=university-course-registration \
     -Dsonar.sources=. \
     -Dsonar.host.url=http://localhost:9000 \
     -Dsonar.login=<YOUR_SONAR_TOKEN>
   ```
   _Note: Replace `http://localhost:9000` and `<YOUR_SONAR_TOKEN>` with your actual SonarQube URL and authentication token._

---

## GitHub Repository

**Repository Name**: `UniversityCourseRegistrationSystem`
**Repository Link**: [GitHub Repo](https://github.com/ShaheeraMalik/UniversityCourseRegistrationSystem.git)

---

## License

This project is licensed under the **MIT License**.
