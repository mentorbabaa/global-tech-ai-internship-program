# Project 1: Build Full Stack Mentorbabaa Quiz App

## Objective
Develop a full-stack quiz application with Python Flask backend and MySQL database, delivering a robust, user-friendly quiz experience.

---

## Functional Requirements

### 1. User Management
- Users must be able to register using email and password.
- Passwords must be securely hashed and stored.
- Users must be able to log in and log out.
- Session management with secure cookies.

### 2. Quiz Management
- Admin or authorized users can upload questions using an Excel template.
- Questions include multiple choice options (A, B, C, D) and correct answer.
- Questions are stored in MySQL database.

### 3. Quiz Flow
- User sees a confirmation page before starting the quiz.
- Each question is timed (30 seconds per question).
- Timer auto-advances to the next question when time is up.
- Navigation buttons to move forward and backward between questions.
- Users can submit answers at any point.

### 4. Result Management
- Users’ answers are stored along with correctness.
- Results page shows:
  - Number of correct and incorrect answers.
  - Total score.
- Optionally display detailed question-wise feedback.

---

## Non-Functional Requirements

### 1. Performance
- Application must respond within 2 seconds for quiz navigation.
- Upload and ingestion of Excel questions should complete within reasonable time (< 1 min for 100 questions).

### 2. Security
- Passwords stored using strong hashing (e.g., bcrypt).
- Secure session management to prevent hijacking.
- Input validation to prevent SQL Injection and XSS attacks.

### 3. Usability
- Responsive UI for desktop and mobile browsers.
- Clear timer display and intuitive navigation buttons.

### 4. Maintainability
- Well-structured codebase with modular components.
- Documentation for setup, deployment, and usage.

---

## Deliverables
- Complete source code (backend + frontend).
- SQL scripts for database schema.
- Excel template for question upload.
- README with detailed setup and usage instructions.

---

## Timeline
- Week 1-2: Backend APIs + DB schema + Authentication.
- Week 3: Frontend UI + Quiz flow + Timer.
- Week 4: Testing, documentation, and polish.
