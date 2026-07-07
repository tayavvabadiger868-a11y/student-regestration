# Student Registration REST API

A full-stack Student Registration application built with **Express.js**, **SQLite (better-sqlite3)**, and **React + Vite**.

This project allows users to register students, search records, update information, delete records, and view students with pagination.

---

# Features

## Backend (Express + SQLite)

- Express.js REST API
- SQLite database using better-sqlite3
- Automatic database/table creation
- Student registration
- Email uniqueness validation
- CRUD Operations
- Pagination
- Search by Name or Course
- CORS enabled
- JSON request handling
- Proper HTTP status codes
- Timestamp for registration

---

## Frontend (React + Vite)

- Student Registration Form
- Client-side validation
- Live Name Character Counter (40 max)
- Student List
- Avatar with Initials
- Search Students
- Pagination Controls
- Edit Student
- Delete Student
- Loading Indicator
- Last Updated Timestamp
- Dark Mode Toggle
- API Error Messages

---

# Project Structure

```
Project Folder
│
├── backend
│   └── server
│       ├── index.js
│       └── data.db
│
├── frontend
│   └── apiDemo
│       └── src
│           ├── App.jsx
│           └── App.css
│
└── postman
    ├── Student-Registration-API.postman_collection.json
    └── Student-Registration.postman_environment.json
```

---

# Technologies Used

## Backend

- Node.js
- Express.js
- better-sqlite3
- SQLite
- CORS

## Frontend

- React
- Vite
- CSS

---

# Installation

## 1. Clone the Repository

```bash
git clone <repository-url>
```

Open the project folder.

---

## 2. Backend Setup

Navigate to the backend folder.

```bash
cd backend/server
```

Install dependencies.

```bash
npm install
```

Required packages:

```
express
cors
better-sqlite3
```

Start the server.

```bash
node index.js
```

Server runs on

```
http://localhost:5000
```

---

## 3. Frontend Setup

Open another terminal.

```bash
cd frontend/apiDemo
```

Install packages.

```bash
npm install
```

Run Vite.

```bash
npm run dev
```

Usually opens at

```
http://localhost:5173
```

---

# Database

The application automatically creates

```
data.db
```

and creates the table

```
students
```

Columns

| Column | Type |
|---------|------|
| id | INTEGER |
| name | TEXT |
| email | TEXT UNIQUE |
| phone | TEXT |
| course | TEXT |
| registered_at | TIMESTAMP |

---

# REST API Endpoints

## Create Student

```
POST /students
```

Required fields

- name
- email
- course

Returns

- 201 Created
- 400 Missing Fields
- 409 Duplicate Email

---

## Get All Students

```
GET /students
```

Query Parameters

```
?page=1

?limit=5

?search=java
```

Example

```
GET /students?page=1&limit=5&search=bca
```

Returns

```
{
  data: [],
  page:1,
  limit:5,
  total:10,
  totalPages:2
}
```

---

## Get Student by ID

```
GET /students/:id
```

Returns

- Student Details
- 404 if not found

---

## Update Student

```
PUT /students/:id
```

Update any field

- name
- email
- phone
- course

Returns

- Updated Student
- 404 if not found

---

## Delete Student

```
DELETE /students/:id
```

Returns

```
Student deleted successfully
```

---

# Frontend Features

### Registration Form

- Name
- Email
- Phone
- Course

---

### Validation

Required

- Name
- Email
- Course

Shows API errors like

- Missing fields
- Duplicate Email

---

### Character Counter

Example

```
Name

25 / 40
```

---

### Student List

Displays

- Avatar
- Name
- Course
- Email
- Phone
- Registration Date

---

### Search

Search by

- Student Name
- Course

---

### Pagination

Navigate using

- Previous
- Next
- Page Numbers

---

### Edit

Loads student information into the form.

After editing

```
PUT /students/:id
```

is called.

---

### Delete

Deletes a student after confirmation.

---

### Dark Mode

Switch between

- Light Theme
- Dark Theme

using the toggle button.

---

### Loading Indicator

Displays

```
Loading students...
```

while data is fetched.

---

### Last Updated

Shows the latest time when the student list was refreshed.

---

# Postman

The project includes

```
Student-Registration-API.postman_collection.json
```

with requests for

- Create Student
- Duplicate Email Test
- Missing Field Test
- Get All Students
- Search Students
- Get Student by ID
- Update Student
- Delete Student

Environment

```
Student-Registration.postman_environment.json
```

Variables

```
base_url
```

Default

```
http://localhost:5000
```

```
student_id
```

Placeholder for testing.

---

# HTTP Status Codes

| Status | Meaning |
|---------|----------|
| 200 | OK |
| 201 | Created |
| 400 | Bad Request |
| 404 | Not Found |
| 409 | Duplicate Email |
| 500 | Internal Server Error |

---

# Example Student

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "9876543210",
  "course": "BCA"
}
```

---

# Future Improvements

- Authentication (JWT)
- Password-based login
- Export to CSV
- Student photo upload
- Email notifications
- Sorting options
- Dashboard with charts
- Mobile responsive enhancements

---

# Learning Outcomes

By completing this project, you will learn:

- REST API development
- CRUD operations
- SQLite database integration
- Express.js routing
- React Hooks
- API integration with Fetch
- Form validation
- Pagination
- Search functionality
- Dark mode implementation
- State management
- Postman API testing

---

# Author

Student Registration REST API

Built using:

- Express.js
- SQLite
- React
- Vite
- better-sqlite3

For educational and learning purposes.
