# Attendance System

A complete web-based attendance management system built with Python Flask, HTML, CSS, JavaScript, and SQLite.

## Features

### Employee Features
- ✅ Check-in and Check-out system
- ✅ View today's attendance status
- ✅ View attendance history/records
- ✅ Real-time clock display

### Admin Features
- ✅ Dashboard with statistics
- ✅ Manage employees (add, view, delete)
- ✅ View employee attendance records by month
- ✅ View all attendance records with date filtering
- ✅ Generate reports (placeholder for future expansion)
- ✅ User management system

### Technical Features
- ✅ User authentication with secure password hashing
- ✅ Role-based access control (Admin/Employee)
- ✅ SQLite database
- ✅ Responsive design for desktop and mobile
- ✅ Real-time statistics
- ✅ Pagination for large datasets

## System Requirements

- Python 3.7 or higher
- Flask 2.3.2
- Flask-SQLAlchemy 3.0.5
- Flask-Login 0.6.2
- Werkzeug 2.3.6

## Installation

### Step 1: Extract the project
Extract the attendance system folder to your desired location.

### Step 2: Create a virtual environment (Recommended)
```bash
cd "Attendance system"
python -m venv venv
```

### Step 3: Activate the virtual environment
**Windows:**
```bash
venv\Scripts\activate
```

**Mac/Linux:**
```bash
source venv/bin/activate
```

### Step 4: Install dependencies
```bash
pip install -r requirements.txt
```

## Running the Application

### Step 1: Navigate to project directory
```bash
cd "Attendance system"
```

### Step 2: Activate virtual environment (if not already activated)
```bash
venv\Scripts\activate
```

### Step 3: Run the application
```bash
python app.py
```

### Step 4: Open in browser
Open your web browser and go to:
```
http://localhost:5000
```

## Default Login Credentials

### Admin Account
- **Username:** admin
- **Password:** admin123

### Demo Employee Account
- **Username:** emp1
- **Password:** emp123

## Project Structure

```
Attendance system/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── attendance.db         # SQLite database (created on first run)
├── templates/            # HTML templates
│   ├── login.html
│   ├── employee_dashboard.html
│   ├── my_records.html
│   ├── admin_dashboard.html
│   ├── manage_employees.html
│   ├── add_employee.html
│   ├── view_employee.html
│   ├── attendance_records.html
│   └── reports.html
└── static/              # CSS and JavaScript
    └── style.css
```

## Usage Guide

### For Employees
1. Login with your credentials
2. View your dashboard showing today's status
3. Click "Check In" when you arrive
4. Click "Check Out" when you leave
5. View your attendance history in "My Records"

### For Admins
1. Login with admin credentials
2. Access the admin dashboard for overview statistics
3. Navigate to "Employees" to manage employee accounts
4. View individual employee records by clicking "View Records"
5. Use "Attendance" section to see all records with filters
6. Generate reports as needed

## Database Schema

### Users Table
- id (Primary Key)
- username (Unique)
- email (Unique)
- password_hash
- full_name
- role (admin/employee)
- department
- is_active
- created_at

### Attendance Table
- id (Primary Key)
- user_id (Foreign Key)
- check_in (DateTime)
- check_out (DateTime)
- date (Date)
- status (present/absent/leave)
- notes (Text)
- created_at

## Features to Add (Future Enhancements)

- [ ] Leave management system
- [ ] Report generation and export (PDF/Excel)
- [ ] Email notifications
- [ ] QR code check-in/check-out
- [ ] Biometric integration
- [ ] Shift management
- [ ] Holiday management
- [ ] API endpoints for mobile app
- [ ] Real-time notifications
- [ ] Audit logs

## Troubleshooting

### Port already in use
If port 5000 is already in use, modify the port in app.py:
```python
app.run(debug=True, host='127.0.0.1', port=5001)  # Change 5001 to any available port
```

### Database errors
To reset the database, either:
- Delete the SQLite file (commonly located at `instance/attendance.db`) and restart the app; or
- Use the built-in Flask CLI command to safely flush all tables while recreating the default admin:

```powershell
cd "Attendance system"
$env:FLASK_APP = "app.py"
python -m flask flush-db --force
```

This drops and recreates all tables, then ensures the default admin exists (`admin` / `admin123`).

### Import errors
Make sure all dependencies are installed:
```bash
pip install -r requirements.txt
```

## Security Notes

- Change the SECRET_KEY in app.py for production use
- Use environment variables for sensitive data
- Implement HTTPS for production
- Add rate limiting for login attempts
- Consider using more secure password requirements

## License

This project is open source and available for educational purposes.

## Support

For issues or questions, please check the code comments or modify as needed for your specific requirements.
