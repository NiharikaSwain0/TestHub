# Online Examination System

A web-based platform for conducting exams digitally, built with HTML, CSS, JavaScript, and Firebase.

## Features

- **Admin Panel**: Add students, subjects, questions, and view results
- **Student Panel**: Login, attend exams, submit answers, view score
- **Exam Section**: Timer-based tests with multiple-choice questions
- **Result Section**: Automatic result generation after submission
- Secure login/signup
- Responsive design

## Technologies Used

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Firebase
- **Database**: Firebase Realtime Database

## Setup Instructions

1. **Create a Firebase Project**
   - Go to [Firebase Console](https://console.firebase.google.com/)
   - Create a new project
   - Enable Email/Password authentication
   - Enable Realtime Database

2. **Configure Firebase**
   - Go to Project Settings > General
   - Scroll down to "Your apps" and add a web app
   - Copy the Firebase configuration object
   - Open `js/firebase.js` and replace the placeholder values with your Firebase config

3. **Set Up Database Rules**
   - Go to Realtime Database > Rules
   - Set the rules to:
     ```json
     {
       "rules": {
         "users": {
           ".read": "auth != null",
           ".write": "auth != null"
         },
         "subjects": {
           ".read": "auth != null",
           ".write": "auth != null"
         },
         "questions": {
           ".read": "auth != null",
           ".write": "auth != null"
         },
         "results": {
           ".read": "auth != null",
           ".write": "auth != null"
         }
       }
     }
     ```

4. **Run the Application**
   - Open `index.html` in a web browser
   - Register as an admin first
   - Use the admin panel to add subjects, questions, and students

## Usage

### Admin
- Login with admin credentials
- Add subjects
- Add questions for each subject
- Add students (default password: password123)
- View all exam results

### Student
- Login with student credentials
- Select a subject and start the exam
- Answer questions within the time limit
- View results immediately after submission

## Project Structure

```
Online Examination System/
├── index.html          # Landing page
├── login.html          # Login page
├── register.html       # Registration page
├── admin.html          # Admin panel
├── student.html        # Student panel
├── exam.html           # Exam page
├── result.html         # Result page
├── css/
│   └── style.css       # Stylesheet
├── js/
│   ├── firebase.js     # Firebase configuration
│   ├── login.js        # Login logic
│   ├── register.js     # Registration logic
│   ├── admin.js        # Admin panel logic
│   ├── student.js      # Student panel logic
│   ├── exam.js         # Exam logic
│   └── result.js       # Result logic
└── README.md           # This file
```
