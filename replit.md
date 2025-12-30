# Employee Attendance System

## Overview
A Flask-based employee attendance management system with admin and employee dashboards. The system allows employees to check in/out and view their attendance records, while admins can manage employees, rotas (schedules), and generate reports.

## Project Structure
```
├── app.py              # Main Flask application with all routes and models
├── requirements.txt    # Python dependencies
├── static/
│   └── style.css      # CSS styles
├── templates/          # Jinja2 HTML templates
│   ├── login.html
│   ├── admin_dashboard.html
│   ├── employee_dashboard.html
│   ├── manage_employees.html
│   ├── manage_rotas.html
│   └── ...
└── instance/           # SQLite database location (auto-created)
```

## Tech Stack
- **Backend**: Python 3.11, Flask 2.3.2
- **Database**: SQLite (with Flask-SQLAlchemy)
- **Authentication**: Flask-Login
- **Excel Export**: openpyxl

## Running the Application
The application runs on port 5000 via the "Start application" workflow which executes `python app.py`.

## Default Credentials
- **Admin**: username: `admin`, password: `admin123`
- **Employee**: Create via admin panel or use demo credentials shown on login page

## Features
- Employee check-in/check-out with schedule validation
- Admin dashboard with employee management
- Rota (work schedule) management
- Attendance records and reports
- Excel export for reports

## Recent Changes
- Initial setup for Replit environment (December 2025)
- Configured host to 0.0.0.0:5000 for Replit compatibility
