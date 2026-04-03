HR-PULSE: Human Resource Management System

A comprehensive, role-based Human Resource Management System built with modern web technologies. HR-PULSE streamlines employee management, attendance tracking, internship management, and performance reporting with a user-friendly interface.

![Next.js](https://img.shields.io/badge/Next.js-15.3.3-black?style=flat-square)
![React](https://img.shields.io/badge/React-19.1.0-blue?style=flat-square)
![MongoDB](https://img.shields.io/badge/MongoDB-Latest-green?style=flat-square)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.1.10-blue?style=flat-square)

---

Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Configuration](#configuration)
- [User Roles & Permissions](#user-roles--permissions)
- [API Endpoints](#api-endpoints)
- [Database Models](#database-models)
- [Running the Application](#running-the-application)
- [File Upload Feature](#file-upload-feature)
- [Scripts](#scripts)
- [Contributing](#contributing)
- [License](#license)

---
Features

Role-Based Access Control
- **Super Admin**: System configuration and user management
- **HR Manager**: Employee management, company administration
- **Manager**: Team management and task assignment
- **Employee**: Personal dashboard, attendance, and reporting
- **Intern**: Limited access - attendance and task viewing

Core Functionalities

Employee Management
- Add, edit, and delete employee records
- Upload and manage employee resumes and documents
- Track employee details (ID, name, email, department, designation)
- Employee database filtering and search

Attendance Tracking
- Daily attendance marking
- View attendance history
- Attendance reports and analytics
- Multi-user attendance management

Intern Management
- Separate intern database
- Intern profile management
- Intern task assignment
- Intern attendance tracking

#### Task Management
- Create and assign tasks to employees/interns
- Task status tracking
- Task prioritization
- Employee-specific task views

#### Reporting & Analytics
- Generate HR reports
- Employee performance reports
- Attendance reports
- Customizable date range filtering

#### File Management
- Resume upload capability
- Additional documents upload
- Secure file storage
- File path tracking in database

---

## 🛠 Tech Stack

### Frontend
- **React 19.1.0** - UI library
- **Next.js 15.3.3** - Full-stack framework with App Router
- **TailwindCSS 4.1.10** - Utility-first CSS framework
- **Lucide React 0.518.0** - Icon library

### Backend
- **Node.js** - Runtime environment
- **Next.js API Routes** - Backend API
- **Express-like routing** - via Next.js

### Database
- **MongoDB 8.16.0** - NoSQL database
- **Mongoose 8.16.0** - ODM for MongoDB

### Authentication & Security
- **JWT (jsonwebtoken 9.0.2)** - Token-based authentication
- **bcrypt 6.0.0** - Password hashing and security

### File Handling
- **Formidable 3.5.4** - File upload handling
- **Multer 2.0.1** - Middleware for file uploads

### Development Tools
- **ESLint** - Code quality
- **Turbopack** - Fast build tool

---

## Project Structure

```
HR-PULSE/
├── HRM-HB/                          # Main application directory
│   ├── app/                         # Next.js App Router pages
│   │   ├── api/                     # API route handlers
│   │   ├── login/                   # Login page
│   │   ├── homepageC/               # Company homepage
│   │   ├── homepageE/               # Employee homepage
│   │   ├── homepageHR/              # HR homepage
│   │   ├── homepageM/               # Manager homepage
│   │   ├── employeesHR/             # HR employee management
│   │   ├── employeesM/              # Manager employee view
│   │   ├── employeesC/              # Company employee management
│   │   ├── attendance/              # Attendance marking
│   │   ├── viewattendanceE/         # Employee attendance view
│   │   ├── viewattendanceHR/        # HR attendance management
│   │   ├── intern/                  # Intern management
│   │   ├── internsHR/               # HR intern management
│   │   ├── taskAssign/              # Task assignment
│   │   ├── taskassignE/             # Employee task view
│   │   ├── reporting/               # Reports dashboard
│   │   ├── reportingE/              # Employee reporting
│   │   ├── reportingHR/             # HR reporting
│   │   ├── addHR/                   # Add HR module
│   │   ├── addM/                    # Add Manager module
│   │   ├── super/                   # Super Admin panel
│   │   ├── superLogin/              # Super Admin login
│   │   ├── presentEmployees/        # Present employees view
│   │   ├── layout.js                # Root layout
│   │   ├── page.js                  # Home page (redirects to login)
│   │   └── globals.css              # Global styles
│   │
│   ├── pages/                       # API routes (Pages Router)
│   │   └── api/
│   │       ├── employees.js         # Employee API endpoints
│   │       ├── interns.js           # Intern API endpoints
│   │       └── reports.js           # Reports API endpoints
│   │
│   ├── models/                      # Mongoose database models
│   │   ├── employeeModel.js         # Employee schema
│   │   ├── internModel.js           # Intern schema
│   │   ├── User.js                  # User authentication schema
│   │   ├── Attendance.js            # Attendance schema
│   │   ├── Report.js                # Report schema
│   │   ├── Company.js               # Company schema
│   │   └── SuperAdmin.js            # Super Admin schema
│   │
│   ├── lib/                         # Utility and helper functions
│   │   └── dbConnect.js             # MongoDB connection setup
│   │
│   ├── public/                      # Static assets
│   │   └── uploads/                 # File upload directory
│   │
│   ├── package.json                 # Project dependencies
│   ├── package-lock.json            # Dependency lock file
│   ├── jsconfig.json                # JavaScript/path aliases config
│   ├── next.config.mjs              # Next.js configuration
│   ├── tailwind.config.js           # TailwindCSS configuration
│   ├── postcss.config.mjs           # PostCSS configuration
│   ├── eslint.config.mjs            # ESLint configuration
│   ├── .gitignore                   # Git ignore rules
│   └── README.md                    # Project documentation
│
└── .git/                            # Git repository
```

---

##  Installation & Setup

### Prerequisites
- **Node.js** (v16 or higher)
- **npm** (v8 or higher)
- **MongoDB** (local or cloud - MongoDB Atlas)
- **Git**

### Step 1: Clone the Repository
```bash
git clone https://github.com/ROHITKINDARLE/HR-PULSE.git
cd HR-PULSE/HRM-HB
```

### Step 2: Install Dependencies
```bash
npm install
```

### Step 3: Environment Setup
Create a `.env.local` file in the `HRM-HB` directory with the following variables:

```env
# MongoDB Connection
MONGODB_URI=mongodb://localhost:27017/hrpulse
# Or for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/hrpulse?retryWrites=true&w=majority

# JWT Configuration
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRY=7d

# Application
NEXT_PUBLIC_API_URL=http://localhost:3000

# File Upload
UPLOAD_DIR=public/uploads
MAX_FILE_SIZE=5242880  # 5MB in bytes
```

### Step 4: Create Upload Directory
```bash
mkdir -p public/uploads
```

---

##  Configuration

### MongoDB Connection
The application uses Mongoose to connect to MongoDB. Update your connection string in `.env.local`:

**For Local MongoDB:**
```
MONGODB_URI=mongodb://localhost:27017/hrpulse
```

**For MongoDB Atlas (Cloud):**
```
MONGODB_URI=mongodb+srv://username:password@cluster-name.mongodb.net/hrpulse?retryWrites=true&w=majority
```

### Database Connection File
See `lib/dbConnect.js` for MongoDB connection configuration.

### TailwindCSS
TailwindCSS is configured in `tailwind.config.js`. Customize styles by modifying the configuration file.

---

##  User Roles & Permissions

### 1. Super Admin
- **Access**: Full system access
- **Permissions**:
  - Manage companies
  - Create HR managers
  - View all reports
  - System settings

### 2. HR Manager
- **Access**: Company-wide HR functions
- **Permissions**:
  - Add/edit/delete employees
  - Upload employee documents
  - Manage interns
  - View and mark attendance
  - Assign managers
  - Generate HR reports

### 3. Manager
- **Access**: Team and employee management
- **Permissions**:
  - View assigned employees
  - Assign tasks
  - View attendance
  - Submit reports
  - Cannot modify employee records

### 4. Employee
- **Access**: Personal and team functions
- **Permissions**:
  - View personal dashboard
  - Check own attendance
  - View assigned tasks
  - Submit reports
  - Limited to own data access

### 5. Intern
- **Access**: Limited functions
- **Permissions**:
  - View own profile
  - Check attendance
  - View assigned tasks
  - No modification rights

---

## 🔌 API Endpoints

### Authentication APIs
- `POST /api/login` - User login
- `POST /api/logout` - User logout
- `POST /api/register` - User registration (Admin only)

### Employee APIs
- `GET /api/employees` - Get all employees
- `POST /api/employees` - Create new employee with file upload
- `GET /api/employees/:id` - Get employee by ID
- `PUT /api/employees/:id` - Update employee details
- `DELETE /api/employees/:id` - Delete employee

### Intern APIs
- `GET /api/interns` - Get all interns
- `POST /api/interns` - Create new intern
- `GET /api/interns/:id` - Get intern by ID
- `PUT /api/interns/:id` - Update intern details
- `DELETE /api/interns/:id` - Delete intern

### Attendance APIs
- `POST /api/attendance/mark` - Mark attendance
- `GET /api/attendance/:userId` - Get user attendance
- `GET /api/attendance/report/:dateRange` - Get attendance report

### Reports APIs
- `GET /api/reports` - Get all reports
- `POST /api/reports` - Create new report
- `GET /api/reports/:id` - Get report by ID

### File Upload
- Integrated into employee creation (`/api/employees`)
- Supports resume and document uploads
- Files stored in `public/uploads/`

---

## Database Models

### Employee Model
```javascript
{
  employeeId: String (unique, required),
  name: String (required),
  email: String,
  mobileNumber: String,
  department: String,
  designation: String,
  resumeUrl: String,      // File path
  documentsUrl: String,   // File path
  createdAt: Date (default: now)
}
```

### User Model
```javascript
{
  name: String (required),
  email: String (unique, required),
  username: String (unique, required),
  passwordHash: String (required),
  role: Enum ['hr', 'manager', 'employee', 'intern'] (required),
  companyId: ObjectId (ref: Company, required),
  managerId: ObjectId (ref: User),
  createdBy: ObjectId (ref: User),
  timestamps: true
}
```

### Attendance Model
```javascript
{
  userId: ObjectId (ref: User),
  date: Date,
  status: Enum ['present', 'absent', 'leave'],
  checkInTime: Time,
  checkOutTime: Time,
  notes: String,
  createdAt: Date
}
```

### Intern Model
```javascript
{
  internId: String (unique),
  name: String (required),
  email: String,
  department: String,
  mentor: ObjectId (ref: User),
  startDate: Date,
  endDate: Date,
  status: String,
  resumeUrl: String,
  createdAt: Date
}
```

### Report Model
```javascript
{
  reportType: String,
  generatedBy: ObjectId (ref: User),
  dateRange: { start: Date, end: Date },
  data: Object,
  filePath: String,
  createdAt: Date
}
```

### Company Model
```javascript
{
  name: String (required, unique),
  email: String,
  phone: String,
  address: String,
  hrManager: ObjectId (ref: User),
  createdAt: Date
}
```

---

## Running the Application

### Development Mode
```bash
npm run dev
```
Application runs on `http://localhost:3000`

Features:
- Hot reload with Turbopack
- Fast development experience
- Auto-refreshing on file changes

### Build for Production
```bash
npm run build
```

### Start Production Server
```bash
npm start
```

### Linting
```bash
npm run lint
```

---

## 📤 File Upload Feature

### How It Works
1. Employee creation form accepts resume and documents
2. Files are handled using **Formidable** middleware
3. Files are stored in `public/uploads/` directory
4. File paths are saved in the database
5. Files can be accessed via `/uploads/[filename]`

### Configuration
- **File Handler**: `pages/api/employees.js`
- **Storage Directory**: `public/uploads/`
- **Supported Types**: All file types (consider adding validation for security)
- **Max File Size**: Configurable in `.env.local`

### Security Considerations
- Implement file type validation
- Add file size limits
- Scan uploaded files for malware
- Use secure file naming
- Restrict file access based on user role

---

##  Package Details

### Key Dependencies
| Package | Version | Purpose |
|---------|---------|---------|
| next | 15.3.3 | React framework |
| react | 19.1.0 | UI library |
| mongoose | 8.16.0 | MongoDB ODM |
| jsonwebtoken | 9.0.2 | Authentication tokens |
| bcrypt | 6.0.0 | Password hashing |
| axios | 1.10.0 | HTTP client |
| tailwindcss | 4.1.10 | CSS framework |
| lucide-react | 0.518.0 | Icons |
| formidable | 3.5.4 | File upload handling |
| multer | 2.0.1 | Middleware for file uploads |

---

##  Common Tasks

### Adding a New User Role
1. Update User model schema to include new role in enum
2. Create corresponding homepage component
3. Add API endpoint protection with role-based middleware
4. Create UI components for the role's functionality

### Creating a New API Endpoint
1. Create handler in `pages/api/` or `app/api/`
2. Connect to MongoDB via `connectDB()`
3. Implement CRUD operations
4. Add error handling
5. Return appropriate HTTP status codes

### Adding File Upload to New Feature
1. Use formidable in API route
2. Set `config.api.bodyParser = false`
3. Parse form data with `IncomingForm`
4. Save files to `public/uploads/`
5. Store file path in database

---

## 🐛 Troubleshooting

### MongoDB Connection Issues
- Ensure MongoDB service is running
- Verify connection string in `.env.local`
- Check network access for MongoDB Atlas
- Review MongoDB logs for errors

### File Upload Not Working
- Verify `public/uploads/` directory exists
- Check file permissions
- Ensure formidable configuration is correct
- Validate file size limits

### Authentication Issues
- Verify JWT_SECRET in `.env.local`
- Check token expiry settings
- Ensure user role is correctly set in database
- Review authentication middleware

### Build Errors
- Clear `.next` directory: `rm -rf .next`
- Reinstall dependencies: `npm install`
- Check ESLint errors: `npm run lint`
- Verify Node.js version compatibility

---

## Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/YourFeature`
3. Commit changes: `git commit -m 'Add YourFeature'`
4. Push to branch: `git push origin feature/YourFeature`
5. Submit pull request

---

## 📝 License

This project is private and proprietary. All rights reserved by ROHITKINDARLE.

---

##  Contact & Support

For issues, questions, or support:
- GitHub: [@ROHITKINDARLE](https://github.com/ROHITKINDARLE)
- Repository: [HR-PULSE](https://github.com/ROHITKINDARLE/HR-PULSE)

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 0.1.0 | 2024 | Initial release |

---

##  Learning Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [React Documentation](https://react.dev)
- [Mongoose Documentation](https://mongoosejs.com)
- [TailwindCSS Documentation](https://tailwindcss.com/docs)
- [JWT Documentation](https://jwt.io)

---

**Last Updated**: April 3, 2026  
**Project Status**: Active Development

 
