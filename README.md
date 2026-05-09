# 🎓 Online Examination System with Timer & Leaderboard

A full-stack web application for conducting online examinations with real-time timers, automatic scoring, and comprehensive leaderboards.

## ✨ Features

### 🏠 Homepage
- Modern responsive design with gradient background
- Student login/signup buttons in header
- HOD login button (hidden at bottom-right corner)
- Leaderboard access
- Feature showcase with animations

### 👤 Student Features
- **Registration**: Name, Roll Number, Class, Branch, Password
- **Login**: Roll Number + Password authentication
- **Dashboard**: 
  - Upcoming tests with countdown timers
  - Recent submissions and scores
  - Quick statistics
  - Sidebar navigation
- **Test Taking**:
  - Real-time countdown timer
  - Auto-submission on timeout
  - Objective tests with instant scoring
  - Textual tests with manual evaluation
  - Prevention of multiple submissions

### 👨‍🏫 HOD (Admin) Features
- **Login**: Static credentials (admin/123456)
- **Dashboard**: Overview of tests and submissions
- **Test Creation**:
  - Objective tests with MCQs and automatic scoring
  - Textual tests with .docx file upload (stored in MongoDB)
  - Configurable duration, marks, and exam dates
- **Submission Management**:
  - View all student submissions
  - Manual evaluation of textual responses
  - Assignment of marks and feedback

### 🏆 Leaderboard
- Top 3 students in special podium layout
- Complete rankings table
- Sorting by total score and fastest submission time
- Statistics and performance metrics

### ⏱️ Timer System
- Real-time countdown for upcoming tests
- Auto-submission when time expires
- Visual indicators for time remaining
- Prevention of test access outside time windows

## 🛠️ Technology Stack

- **Backend**: Python Flask
- **Database**: MongoDB Atlas (including file storage)
- **Frontend**: HTML + Tailwind CSS
- **Templates**: Jinja2
- **File Processing**: python-docx for .docx files

## 📋 Prerequisites

- Python 3.7+
- MongoDB Atlas account
- pip (Python package installer)

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd Online-Examination-System
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables
1. Create a MongoDB Atlas account at [mongodb.com](https://mongodb.com)
2. Create a new cluster and copy your connection string
3. Copy `.env.example` to `.env`
4. Update `.env` with your values:

```text
FLASK_SECRET_KEY=replace-with-a-secure-random-string
MONGODB_URI=mongodb+srv://your-username:your-password@your-cluster.mongodb.net/?retryWrites=true&w=majority
MONGODB_DBNAME=exam_system
ADMIN_USERNAME=admin
ADMIN_PASSWORD=123456
SESSION_COOKIE_SECURE=False
```

> **Important:** Do not commit `.env` to version control. The repository already ignores `.env` via `.gitignore`.

### 4. Run the Application
```bash
python app.py
```

The application will be available at `http://localhost:5000`

## 📁 Project Structure

```
Online Examination System/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── README.md             # This file
├── templates/            # HTML templates
│   ├── base.html         # Base template with common layout
│   ├── home.html         # Homepage
│   ├── signup.html       # Student registration
│   ├── login.html        # Student login
│   ├── admin_login.html  # HOD login
│   ├── student_dashboard.html  # Student dashboard
│   ├── admin_dashboard.html    # HOD dashboard
│   ├── create_test.html  # Test creation form
│   ├── test.html         # Test taking interface
│   ├── leaderboard.html  # Leaderboard page
│   └── evaluate_submission.html # Submission evaluation
└── .gitignore           # Git ignore file
```

## 🔐 Default Credentials

### HOD Login
- **Username**: `admin`
- **Password**: `123456`

## 📖 Usage Guide

### For Students
1. **Register**: Visit the homepage and click "Signup"
2. **Login**: Use your roll number and password
3. **View Tests**: Check upcoming tests on your dashboard
4. **Take Tests**: Click "Start Test" when a test is active
5. **Submit**: Complete the test within the time limit
6. **View Results**: Check your scores and leaderboard position

### For HOD (Admin)
1. **Login**: Click the HOD button at bottom-right of homepage
2. **Create Tests**: 
   - Choose between objective or textual test
   - For objective: Add questions with 4 options each
   - For textual: Upload a .docx file with questions (stored in MongoDB)
3. **Monitor**: View all submissions and student performance
4. **Evaluate**: Grade textual submissions manually
5. **Analyze**: Check leaderboard and statistics

## 🎯 Key Features Explained

### Timer System
- **Upcoming Tests**: Shows countdown to test start
- **Active Tests**: Real-time countdown during test
- **Auto-submission**: Automatically submits when time expires
- **Visual Indicators**: Color changes for time warnings

### Test Types
- **Objective Tests**: Multiple choice questions with instant scoring
- **Textual Tests**: Essay questions requiring manual evaluation
- **File Upload**: Support for .docx question documents (stored in MongoDB)

### File Storage
- **MongoDB Storage**: All uploaded files are stored as Binary data in MongoDB
- **No Static Files**: No local file system dependencies
- **Automatic Text Extraction**: .docx files are processed and text is extracted for display

### Security Features
- **Session Management**: Secure login/logout
- **Access Control**: Prevents unauthorized test access
- **Single Submission**: Prevents multiple submissions per test
- **Time Validation**: Ensures tests are taken within scheduled windows

### Leaderboard Algorithm
- **Primary Sort**: Total score (descending)
- **Secondary Sort**: Fastest submission time (ascending)
- **Statistics**: Average scores, total tests, performance metrics

## 🔧 Customization

### Styling
- Modify Tailwind CSS classes in templates
- Update color scheme in `base.html`
- Customize animations and transitions

### Database
- Add new fields to student/test/submission schemas
- Modify queries in `app.py`
- Add new collections as needed

### Features
- Add new test types
- Implement email notifications
- Add file upload restrictions
- Create additional admin features

## 🐛 Troubleshooting

### Common Issues
1. **MongoDB Connection Error**: Check connection string and network access
2. **Import Errors**: Ensure all dependencies are installed
3. **File Upload Issues**: Check MongoDB connection and permissions
4. **Timer Issues**: Verify JavaScript is enabled

### Debug Mode
Run with debug mode for detailed error messages:
```python
app.run(debug=True)
```

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📞 Support

For support and questions:
- Create an issue in the repository
- Check the troubleshooting section
- Review the code comments

---

**Built with ❤️ using Flask, MongoDB, and Tailwind CSS** 