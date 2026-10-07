# Setup Guide - Working Status Tracker Bot

## Prerequisites
- Python 3.8+
- pip (Python package manager)
- Git

## Installation Steps

### Step 1: Clone Repository
```bash
git clone https://github.com/abhijeetmore-tomtom/working-status-tracker-bot.git
cd working-status-tracker-bot
```

### Step 2: Create Python Virtual Environment
```bash
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Initialize Database
```bash
python init_db.py
```

### Step 5: Run Application
```bash
python app.py
```

### Step 6: Open in Browser
```
http://localhost:5000
```

## Default Login (for testing)
- Email: admin@company.com
- Password: admin123

## Project Structure
```
working-status-tracker-bot/
├── app.py                 # Main Flask app
├── requirements.txt       # Python dependencies
├── init_db.py            # Database initialization
├── database.db           # SQLite database (auto-created)
├── templates/
│   ├── base.html         # Base template
│   ├── login.html        # Login page
│   ├── dashboard.html    # Main dashboard
│   ├── popup.html        # Daily status popup
│   ├── weekly_edit.html  # Weekly editing screen
│   └── report.html       # Monthly report
├── static/
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── script.js
└── README.md
```

## Features Included
- ✅ Employee login
- ✅ Daily status popup
- ✅ Weekly editing
- ✅ Monthly reports with percentages
- ✅ Admin dashboard to view team reports
- ✅ SQLite database (no server needed)

## Troubleshooting

**Port 5000 already in use?**
```bash
python app.py --port 5001
```

**Database issues?**
```bash
rm database.db
python init_db.py
```

**ModuleNotFoundError?**
```bash
pip install -r requirements.txt
```

## Next Steps
1. Customize with your company colors/logo
2. Add more employees to database
3. Deploy to free hosting (Heroku, PythonAnywhere)
4. Share URL with your team

