# 🎓 Educational Organisation Using ServiceNow

### 🏫 M.A.M College of Engineering  
**Location:** Siruganur, Tiruchirappalli - 621105  
**Subject:** ServiceNow Administrator (NM1051)  
**Team ID:** NM2025TMID02735  

---

## 👥 Team Members

| Name | Register Number |
|------|------------------|
| George Samvel H | AUT812622AI012 |
| Arun Kumar S | AUT812622AI004 |
| Richard C | AUT812622AI042 |
| Hariprasanth R | AUT812622AI016 |

---

## 📘 Project Overview

**Educational Organisation Using ServiceNow** is a digital management system built on the **ServiceNow** platform.  
It automates key administrative and academic workflows for educational institutions — including **student management**, **teacher tracking**, **admission processing**, and **academic performance monitoring**.  

By integrating **TensorFlow**, the project introduces AI-based analytics to predict student performance and enhance decision-making.

---

## 🎯 Objectives

- Automate and simplify key administrative processes.  
- Centralize student and teacher data.  
- Streamline admissions and enrollment.  
- Monitor academic progress in real time.  
- Generate automated alerts and performance reports.  
- Use AI-based analytics for predictive insights.

---

## 🧩 Modules

- **Student Information Management** – Manage and secure student records.  
- **Teacher Management** – Maintain faculty and timetable information.  
- **Admission Management** – Simplify admission and enrollment workflows.  
- **Academic Progress Monitoring** – Track grades, attendance, and results.  
- **Reporting & Notifications** – Automate alerts and performance reports.  
- **AI Analytics (TensorFlow)** – Predict outcomes and optimize learning paths.

---

## 🧰 Tools & Technologies

| Category | Tools / Technologies |
|-----------|----------------------|
| Platform | ServiceNow |
| Developer Tools | ServiceNow Studio, Flow Designer, Workflow Editor |
| Analytics | TensorFlow |
| Web Browsers | Google Chrome, Mozilla Firefox |
| OS Support | Windows 10 / Linux / macOS |

---

## ⚙️ System Requirements

**Hardware**
- Processor: Intel Core i5 or above  
- RAM: 8 GB or higher  
- Hard Disk: 500 GB or higher  
- Network: Stable Internet connection  

**Software**
- Operating System: Windows / Linux / macOS  
- Browser: Google Chrome / Firefox  
- ServiceNow Developer Account and Instance

---

## 🚀 Implementation Steps

### 1️⃣ Setup ServiceNow Developer Instance
1. Sign up at [developer.servicenow.com](https://developer.servicenow.com).
2. Request a personal developer instance.
3. Log in using provided credentials.

### 2️⃣ Create Update Set
- Navigate to: **All → Local Update Sets → New**
- Enter Name: `Educational Organisation`
- Click **Submit** and **Make Current**

### 3️⃣ Create Tables
- **Salesforce Table** – Base table for linking data.
- **Admission Table** – Stores admission details.
- **Student Progress Table** – Records grades and academic data.

### 4️⃣ Configure Forms and Layouts
- Design forms for each table under **System Definition → Tables → Form Design**.

### 5️⃣ Setup Number Maintenance
- Generate admission numbers automatically under **All → Number Maintenance → New**.

### 6️⃣ Create Process Flow
- Design workflow for admission:  
  `New → InProgress → Joined → Rejected → Closed`

### 7️⃣ Add Client Scripts
| Script | Purpose |
|--------|----------|
| Auto Populate | Automatically fetch data from related records |
| Pincode Update | Auto-fill city, mandal, and district |
| Disable Fields | Make calculated fields non-editable |
| Total Update | Calculate total marks |
| Percentage | Calculate percentage based on total |
| Result | Display Pass/Fail based on percentage |

---

## 💻 Example Script – Total Update

```javascript
function onChange(control, oldValue, newValue, isLoading, isTemplate) {
  if (isLoading || newValue === '') return;

  var a = parseInt(g_form.getValue('u_telugu'));
  var b = parseInt(g_form.getValue('u_hindi'));
  var c = parseInt(g_form.getValue('u_english'));
  var d = parseInt(g_form.getValue('u_maths'));
  var e = parseInt(g_form.getValue('u_science'));
  var f = parseInt(g_form.getValue('u_social'));

  var total = a + b + c + d + e + f;
  g_form.setValue('u_total', total);
}
