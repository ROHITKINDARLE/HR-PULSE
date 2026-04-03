HR-PULSE: Human Resource Management System

A comprehensive, role-based Human Resource Management System built with modern web technologies. HR-PULSE streamlines employee management, attendance tracking, internship management, and performance reporting with a user-friendly interface.








Table of Contents
Features
Tech Stack
Project Structure
Installation and Setup
API Endpoints
Database Models
Running the Application
File Upload Feature
Contributing
License
Features
Role-Based Access Control
Super Admin: System configuration and user management
HR Manager: Employee management and company administration
Manager: Team management and task assignment
Employee: Personal dashboard, attendance, and reporting
Intern: Limited access (attendance and task viewing)
Core Functionalities

Employee Management:

Add, edit, and delete employee records
Upload and manage resumes and documents
Track employee details
Search and filter employee database

Attendance Tracking:

Daily attendance marking
Attendance history
Reports and analytics

Intern Management:

Intern profile management
Task assignment
Attendance tracking

Task Management:

Assign tasks
Track task status
Priority management

Reporting:

HR reports
Performance reports
Attendance reports

File Management:

Resume and document uploads
Secure file storage
File path tracking
Tech Stack

Frontend:

React.js
Next.js
Tailwind CSS

Backend:

Node.js
Next.js API Routes

Database:

MongoDB
Mongoose

Authentication:

JWT
bcrypt
Project Structure

HR-PULSE/
├── HRM-HB/
│ ├── app/
│ ├── pages/api/
│ ├── models/
│ ├── lib/
│ ├── public/uploads/
│ └── config files

Installation and Setup
Clone repository
git clone https://github.com/ROHITKINDARLE/HR-PULSE.git

cd HR-PULSE/HRM-HB
Install dependencies
npm install
Create .env.local file
MONGODB_URI=your_mongodb_uri
JWT_SECRET=your_secret
Run the project
npm run dev
API Endpoints

GET /api/employees
POST /api/employees
GET /api/interns
POST /api/interns
POST /api/attendance
GET /api/reports

Database Models

Employee:

employeeId
name
email
department
designation
resumeUrl

User:

name
email
username
role
companyId

Attendance:

userId
date
status

Intern:

internId
name
department
mentor
Running the Application

Development:
npm run dev

Build:
npm run build

Start:
npm start

File Upload Feature
Upload resumes and documents
Stored in public/uploads
Managed using Formidable
Contributing
Fork repository
Create a branch
Commit changes
Push changes
Create a pull request
License

Private project. All rights reserved.

Author

Rohit Kindarle
GitHub: https://github.com/ROHITKINDARLE

LinkedIn: https://www.linkedin.com/in/rohit-kindarle-247742284

Status

Active Development
