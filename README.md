# Daily Working Status Tracker Bot

A one-time installable bot system that automatically opens a popup when employees login to collect their daily working status (Office/WFH/Leave).

## Features

✅ One-time installation for all employees
✅ Auto popup on login
✅ Daily status capture: Office / WFH / Leave
✅ Previous-day editing from weekly dashboard
✅ Monthly analytics with percentage report
✅ Admin and employee views
✅ Shared central database for organization-wide use

## Architecture

This is best implemented as a small internal web app, not a chatbot only:

- Frontend: React or HTML/JS app
- Backend: Node.js/Express or ASP.NET Core
- Database: PostgreSQL/MySQL
- Authentication: employee login with email/username and password
- Storage: one central database shared by everyone

## Main Flow

1. Employee logs into the system
2. Login page opens
3. A popup appears immediately asking for today’s work status
4. Employee selects from:
   - Office
   - Work from Home
   - Leave
5. Optional remarks can be added
6. Data is saved to database
7. Employee can later edit previous entries from a weekly view
8. A monthly report shows totals and percentages for Office / WFH / Leave

## Example Reports

If a user has:
- Office: 12 days
- WFH: 9 days
- Leave: 3 days
- Total: 24 days

Then percentages are:
- Office: 50%
- WFH: 37.5%
- Leave: 12.5%

## Suggested Data Structure

### Users
- id
- employee_name
- email
- password_hash
- role
- created_at

### Attendance
- id
- user_id
- date
- status
- remarks
- created_at
- updated_at

## API Ideas

- POST /login
- POST /attendance/save
- GET /attendance/week
- PUT /attendance/:id
- GET /reports/monthly
- GET /reports/team

## Daily Popup UX

Popup contains:
- Title: Daily Work Status
- Date
- Radio buttons:
  - Office
  - Work from Home
  - Leave
- Remarks field
- Save button
- Edit previous day link

## Weekly Editing UX

- Select week
- Show all 7 days
- Let user update any day
- Save changes
- System updates report automatically

## Monthly Reporting UX

- Employee view: my monthly summary
- Manager/Admin view: team summary
- Show:
  - total office days
  - total WFH days
  - total leave days
  - percentage chart
  - downloadable PDF/Excel optional

## Recommended Technology Stack

Best choice for your requirement:

- Frontend: React
- Backend: Node.js + Express
- Database: PostgreSQL
- Authentication: JWT

This gives:
- login popup
- central shared storage
- editing old entries
- monthly analytics
- easy deployment for all employees

## Example of popup logic

```javascript
// On successful login
if (!todayStatusExists) {
  showModal('Daily Work Status');
}
```

## Example of monthly percentage calculation

```javascript
const total = office + wfh + leave;
const officePercent = (office / total) * 100;
const wfhPercent = (wfh / total) * 100;
const leavePercent = (leave / total) * 100;
```

## Deployment Model

Use a single central server and one shared database for the whole organization:

- Everyone logs in with their account
- One popup appears after login
- Data is stored centrally
- Admin can run reports per employee or team

## Recommended Next Step

Create a starter project with:
- login page
- daily popup modal
- attendance database schema
- weekly edit screen
- monthly report dashboard

Then share the app URL with employees after deployment.

---

This repository can be used as the foundation for building the system.
