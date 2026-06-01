💰 Monthly Salary Sheet Generator
> A Google Apps Script automation that creates a new monthly salary sheet from a master employee data file — with one click, directly inside Google Sheets.
![Google Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-4285F4?style=for-the-badge&logo=google&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-34A853?style=for-the-badge&logo=google-sheets&logoColor=white)
---
📌 Overview
Managing monthly salary sheets manually is time-consuming and error-prone — copying templates, updating employee data, clearing old attendance columns, and renaming sheets all take effort every single month.
This script automates the entire process. A custom HRA Tools menu appears inside Google Sheets. With one click, it detects the latest month sheet, suggests the next month name automatically, pulls fresh employee data from a Master sheet, and creates a fully structured salary sheet — ready for attendance and payroll data entry.
---
✨ Features
📅 Auto month detection — finds the latest month sheet and suggests the next one (e.g. after `May'25` it suggests `June'25`)
👥 Master data sync — pulls employee names and salary components (Basic, HRA, Conveyance, LTA, Phone, Other, Gross) directly from the Master sheet
🧹 Smart column clearing — automatically clears attendance columns (J to AN), leave taken columns (BA, BB), and payroll output columns (BD to BI) — while preserving all other data
🗂️ Template-based — copies the previous month's sheet as the template, preserving all formatting and formulas
✅ Duplicate protection — alerts you if a sheet with that name already exists
💬 Custom menu — adds a dedicated `📆 HRA Tools` menu to the Google Sheets toolbar
---
📁 File Structure
```
Salary-Sheet-Generator/
├── Code.gs        # Full Google Apps Script automation
└── README.md
```
---
🗂️ Master Sheet Structure
The script reads from a sheet named `Master` with the following column layout:
Column	Field
A	Employee Name
F	Basic Salary
G	HRA
H	Conveyance Allowance
I	LTA
J	Phone Allowance
K	Other Allowance
L	Gross (CTC)
> Make sure your Master sheet follows this column structure exactly for the script to work correctly.
---
⚙️ How It Works
HR opens the Google Sheet and clicks 📆 HRA Tools → Create New Month Sheet
The script scans all existing sheets for the `Month'YY` format (e.g. `May'25`)
It identifies the latest month and suggests the next one automatically
HR confirms or types a custom month name
The script:
Copies the latest month sheet as a template
Sets column headers in row 3
Pulls all employee salary data from the Master sheet into row 4 onwards
Clears attendance, leave, and payroll output columns ready for fresh data entry
Sets the month name in cell A2
New sheet is ready for the HR team in seconds
---
🚀 Setup & Deployment
Prerequisites
A Google account with Google Sheets access
A Google Sheet with at least one existing month sheet in `Month'YY` format (e.g. `January'25`)
A `Master` sheet with employee data in the column structure above
Steps
Open your Google Sheet
Go to Extensions → Apps Script
Paste the script
Delete any existing code in the editor
Paste the full contents of `Code.gs`
Click Save (Ctrl+S)
Run once to authorise
Click the Run button (▶) on the `onOpen` function
Google will ask for permissions — click Review permissions → Allow
Reload your Google Sheet
Close the Apps Script tab
Refresh your Google Sheet
You will now see the 📆 HRA Tools menu in the toolbar
Use it
Click 📆 HRA Tools → Create New Month Sheet
Confirm the suggested month name and click OK
---
🛠️ Tech Stack
Layer	Technology
Scripting	Google Apps Script (V8 runtime)
Data Source	Google Sheets (Master sheet)
UI	Custom Sheets menu via `SpreadsheetApp.getUi()`
Logic	JavaScript — date detection, array manipulation, range operations
---
💡 Use Case
Built for an HR & Accounts team to eliminate the manual effort of preparing monthly salary sheets. Reduces a 30–45 minute manual task to a single menu click, while ensuring data accuracy by always pulling from the central Master employee record.
---
👤 Author
Avinaba Chakraborty
Senior MIS Analyst · 17+ Years Experience in BI & Data Analytics
LinkedIn · GitHub
---
📄 License
This project is open source and available under the MIT License.
