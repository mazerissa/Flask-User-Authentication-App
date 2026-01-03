# Flask Authentication Web Application

A secure and responsive web application built with Flask that implements a complete user authentication system. This project demonstrates modern web development practices including user registration, login, session management, and protected content access.

## ✨ Features

### 🔐 Secure User Authentication
- User registration with email validation
- Secure login with session management
- Password hashing using PBKDF2-SHA256
- Email uniqueness validation

### 🛡️ Security Features
- Protected routes requiring authentication
- Password hashing with salt using Werkzeug
- Session-based authentication with Flask-Login
- Flash messages for user feedback

### 📁 Content Management
- Protected "secrets" page for authenticated users
- Secure file download functionality
- Dynamic content based on login status

### 🗄️ Database
- SQLite database with SQLAlchemy ORM
- User model with email, password, and name fields
- Automatic database creation and migration

## 🚀 Quick Start

### Prerequisites
- Python 3.7+
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/flask-auth-app.git
   cd flask-auth-app
   ```

2. **Create a virtual environment (optional but recommended)**
   ```bash
   python -m venv venv
   
   # On Windows:
   venv\Scripts\activate
   
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install flask flask-sqlalchemy flask-login
   ```

4. **Run the application**
   ```bash
   python main.py
   ```

5. **Open your browser and navigate to:**
   ```
   http://localhost:5000
   ```

## 📁 Project Structure

```
flask-auth-app/
├── main.py                 # Main Flask application
├── users.db               # SQLite database (auto-generated)
├── static/
│   └── files/
│       └── cheat_sheet.pdf # Protected downloadable file
├── templates/
│   ├── index.html         # Home page
│   ├── login.html         # Login page
│   ├── register.html      # Registration page
│   └── secrets.html       # Protected content page
└── README.md             # This file
```

## 🔧 Configuration

The application uses the following configuration:

- **Secret Key**: Used for session security (change in production)
- **Database**: SQLite database at `sqlite:///users.db`
- **Password Hashing**: PBKDF2 with SHA256, salt length 8

## 🎯 Usage Guide

### 1. Home Page
- Publicly accessible landing page
- Navigation changes based on login status

### 2. Registration
- Navigate to `/register`
- Enter email, name, and password
- Email must be unique
- Password is securely hashed before storage

### 3. Login
- Navigate to `/login`
- Enter registered email and password
- Successful login redirects to protected content

### 4. Protected Content
- Accessible only when logged in
- Displays personalized greeting with user's name
- Contains link to download protected files

### 5. File Download
- Authenticated users can download files from `/download`
- Example: `cheat_sheet.pdf` from static/files/

### 6. Logout
- Accessible via `/logout`
- Clears user session
- Redirects to home page

## 🛡️ Security Notes

- **Never commit sensitive data** like real secret keys
- **Change the secret key** in production environments
- **Consider using environment variables** for configuration
- **Implement CSRF protection** for production use
- **Use HTTPS** in production environments

## 🐛 Common Issues & Solutions

### Issue: "ModuleNotFoundError"
**Solution**: Ensure all dependencies are installed:
```bash
pip install -r requirements.txt
```

### Issue: Database not created
**Solution**: The database is created automatically on first run. Ensure the app has write permissions in the directory.

### Issue: "Email already registered"
**Solution**: Each email can only register once. Use a different email or check existing registrations.

## 📚 Dependencies

- **Flask** (2.3.3+) - Web framework
- **Flask-SQLAlchemy** (3.0.5+) - Database ORM
- **Flask-Login** (0.6.2+) - User session management
- **Werkzeug** (3.0.1+) - Security and utilities

Install all at once:
```bash
pip install flask flask-sqlalchemy flask-login
```

## 🚀 Deployment Considerations

For production deployment:

1. **Change the secret key** to a strong, random value
2. **Use a production database** like PostgreSQL or MySQL
3. **Set up HTTPS** with a valid SSL certificate
4. **Use environment variables** for configuration
5. **Consider adding:**
   - Rate limiting
   - Email verification
   - Password reset functionality
   - Two-factor authentication

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

- Built with [Flask](https://flask.palletsprojects.com/)
- Authentication with [Flask-Login](https://flask-login.readthedocs.io/)
- Database with [SQLAlchemy](https://www.sqlalchemy.org/)
- Security with [Werkzeug](https://werkzeug.palletsprojects.com/)

---

**Note**: This is a demonstration application. For production use, implement additional security measures and follow security best practices.
