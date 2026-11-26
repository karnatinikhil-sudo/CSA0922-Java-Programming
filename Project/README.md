# 🏥 Hospital Management and Appointment Booking System

![Java](https://img.shields.io/badge/Java-17-orange?logo=openjdk)
![Swing](https://img.shields.io/badge/GUI-Java%20Swing-blue)
![MySQL](https://img.shields.io/badge/Database-MySQL%208-4479A1?logo=mysql&logoColor=white)
![JDBC](https://img.shields.io/badge/Connectivity-JDBC-green)
![Status](https://img.shields.io/badge/Status-Capstone%20Project-success)

A desktop application that replaces manual hospital registers and phone/walk-in appointment booking with a centralised digital system. Patients can register, search for doctors and book, reschedule or cancel appointments. Doctors and administrators can manage schedules, appointment statuses, prescriptions and hospital analytics. The system prevents double bookings, reuses cancelled slots through a waitlist, and puts emergency cases at the front of the queue.

> **Capstone Project – CSA0922 Java Programming**  
> SIMATS Engineering, Saveetha Institute of Medical and Technical Sciences, Chennai  
> **Developed by:** K. Nikhil (Reg. No. 192525307)  
> **Guide:** Mr. N. Vijayaragavan, Technical Trainer / CSE

---

## 📑 Table of Contents

1. [Overview](#-overview)
2. [Problem Statement](#-problem-statement)
3. [Objectives](#-objectives)
4. [Key Features](#-key-features)
5. [System Architecture](#-system-architecture)
6. [Technologies Used](#-technologies-used)
7. [Database Design](#-database-design)
8. [Core Algorithms](#-core-algorithms)
9. [Object-Oriented Design](#-object-oriented-design)
10. [Security and Privacy](#-security-and-privacy)
11. [Project Structure](#-project-structure)
12. [Installation and Setup](#-installation-and-setup)
13. [How to Use](#-how-to-use)
14. [Screenshots](#-screenshots)
15. [Testing](#-testing)
16. [Course Outcomes Covered](#-course-outcomes-covered)
17. [Limitations](#-limitations)
18. [Future Enhancements](#-future-enhancements)
19. [Troubleshooting](#-troubleshooting)
20. [Documentation](#-documentation)
21. [Author](#-author)
22. [Acknowledgements](#-acknowledgements)

---

## 📌 Overview

Hospitals that depend on paper registers and telephone bookings face long queues, scheduling conflicts and lost records. The **Hospital Management and Appointment Booking System** solves these problems with a layered Java application backed by a MySQL database.

The application is divided into two integrated modules that share one database through a common JDBC layer:

| Module | Users | Purpose |
|---|---|---|
| **Module 1 – Patient Operations** | Patients, reception | Registration, doctor search, booking, rescheduling, cancellation, symptom recommender, waitlist, live token queue |
| **Module 2 – Doctor and Admin Operations** | Doctors, administrators | Doctor profiles, schedules, appointment status, emergency triage, prescriptions, reminders, no-show tracking, analytics |

Because both modules read and write the same tables, the system behaves as **one integrated application** and not as two separate programs.

**Example of integration**

1. Admin creates a doctor's schedule (Module 2).
2. The patient screen reads the schedule and shows free slots (Module 1).
3. A patient books a slot; the appointment is saved in MySQL (Module 1).
4. The doctor's daily view shows the new booking (Module 2).
5. If the appointment is cancelled, the updated status is visible to both modules and the waitlist is triggered.

---

## ❗ Problem Statement

Manual and semi-manual hospital administration suffers from five main problems:

1. **Records are hard to search and update** when kept in paper registers.
2. **Phone and walk-in bookings** create queues and scheduling conflicts.
3. **Patient details and medical histories are scattered** across books and files.
4. **Appointment statuses are difficult to monitor.**
5. **Emergency patients receive no systematic priority,** and cancelled slots go unused.

The project designs and implements a centralised, role-based system that removes these problems while guaranteeing that no doctor slot can be booked twice, even under simultaneous requests.

---

## 🎯 Objectives

1. Design a four-layer architecture and a normalised MySQL schema.
2. Develop the patient module (registration, search, booking, rescheduling, cancellation, recommender, waitlist, token queue).
3. Develop the doctor/admin module (profiles, schedules, status, triage, prescriptions, reminders, no-show tracking, analytics).
4. Prevent double booking with database transactions and a unique slot constraint.
5. Implement authentication, password hashing and role-based access with an audit log.
6. Test the system with a defined test plan.
7. Evaluate the results against the specifications.

---

## ✨ Key Features

### 👤 Module 1 – Patient Side

| Feature | Description |
|---|---|
| Patient registration | Stores patient details after validating name, age, phone and e-mail |
| Doctor search | Search by doctor name, department or specialization |
| Appointment booking | Shows free and booked slots and confirms the selected slot |
| Rescheduling | Moves an existing appointment to another free slot |
| Cancellation | Cancels an appointment and frees the slot |
| Symptom recommender | Suggests a suitable specialization from entered symptoms (not a diagnosis) |
| Smart waitlist | Offers a cancelled slot to the next waiting patient, with a timeout |
| Live token queue | Shows token number, queue position and estimated waiting time |

### 🩺 Module 2 – Doctor and Admin Side

| Feature | Description |
|---|---|
| Doctor profiles | Add, update and delete doctors |
| Schedule management | Set available days, working hours and slot length |
| Appointment status | Booked, Completed or Cancelled |
| Emergency triage | Orders critical cases first using a `PriorityQueue` (priority set by clinical staff) |
| Patient timeline | Maintains visit history for each patient |
| Prescriptions | Stores prescription details against an appointment |
| Reminders | Sends e-mail reminders before appointments |
| No-show tracking | Identifies missed appointments |
| Admin analytics | Doctor workload, cancellations and peak hours |

### 🌟 What makes it more than a basic CRUD application

- Symptom-based doctor recommender
- Emergency triage queue
- Smart waitlist for cancelled slots
- Live token queue with estimated waiting time
- Automated reminders and analytics

---

## 🏗 System Architecture

```
Users:  Admin | Doctor | Patient
   |
Presentation Layer   - Java Swing GUI
   |
Application Layer    - Core Java and OOP (Module 1 + Module 2)
   |
Data Access Layer    - JDBC (MySQL Connector/J, DAO classes)
   |
Database Layer       - MySQL (InnoDB)
```

| Layer | Responsibility |
|---|---|
| Presentation | Swing screens, event handling, layout managers, menus |
| Application | Business rules: booking, waitlist, triage, queue, recommender |
| Data access | DAO classes using JDBC and `PreparedStatement` |
| Database | MySQL tables, constraints, transactions |

### Booking flow

```
Validate input -> Search doctor -> Read free slots -> Begin transaction
   -> INSERT appointment
        |-- duplicate-key error  -> ROLLBACK -> "Slot already taken"
        |-- success              -> COMMIT -> assign token -> confirmation + reminder
```

### Waitlist flow

```
Appointment cancelled -> slot freed -> offer to first waiting patient
   -> accepts            -> booking transaction runs, waitlist closed
   -> declines / timeout -> offer passes to the next patient
   -> nobody waiting     -> slot stays open for normal booking
```

---

## 🛠 Technologies Used

| Technology | Role in the project |
|---|---|
| **Core Java (JDK 17)** | Application logic |
| **Java Swing / AWT** | Graphical user interface |
| **MySQL 8 (InnoDB)** | Database storage, transactions, constraints |
| **JDBC / MySQL Connector/J** | Java–database connection |
| **ArrayList, HashMap, HashSet, Hashtable** | Data handling, symptom matching, sessions |
| **PriorityQueue** | Emergency triage ordering |
| **Timer / threads** | Scheduled reminders and waitlist timeouts |
| **JavaMail (Jakarta Mail)** | E-mail notifications |
| **OOP** | Modular, reusable design |
| **NetBeans / Eclipse** | Development environment |
| **Git / GitHub** | Version control |

---

## 🗄 Database Design

### Tables

| Table | Purpose |
|---|---|
| `users` | Login accounts with role and hashed password |
| `patients` | Patient details |
| `doctors` | Doctor profiles, department and specialization |
| `schedules` | Doctor working days, hours and slot length |
| `appointments` | Bookings with status, priority and token number |
| `waitlist` | Patients waiting for a freed slot |
| `prescriptions` | Prescription details linked to appointments |
| `symptom_map` | Keyword-to-specialization mapping for the recommender |
| `audit_log` | Record of logins and changes |

### Relationships

- One patient → many appointments and waitlist entries
- One doctor → many schedules, appointments and waitlist entries
- One appointment → many prescriptions
- One user → many audit log entries; one user ↔ one patient or doctor profile

### SQL schema

```sql
CREATE DATABASE IF NOT EXISTS hms;
USE hms;

CREATE TABLE users (
  user_id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50) NOT NULL UNIQUE,
  password_hash VARCHAR(255) NOT NULL,
  salt VARCHAR(64) NOT NULL,
  role ENUM('Admin','Doctor','Patient') NOT NULL
);

CREATE TABLE patients (
  patient_id INT AUTO_INCREMENT PRIMARY KEY,
  user_id INT NULL,
  name VARCHAR(100) NOT NULL,
  age INT NOT NULL,
  gender VARCHAR(10),
  phone VARCHAR(15) NOT NULL,
  email VARCHAR(100),
  address VARCHAR(255),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (user_id) REFERENCES users(user_id)
);

CREATE TABLE doctors (
  doctor_id INT AUTO_INCREMENT PRIMARY KEY,
  user_id INT NULL,
  name VARCHAR(100) NOT NULL,
  department VARCHAR(80) NOT NULL,
  specialization VARCHAR(80) NOT NULL,
  email VARCHAR(100),
  FOREIGN KEY (user_id) REFERENCES users(user_id)
);

CREATE TABLE schedules (
  schedule_id INT AUTO_INCREMENT PRIMARY KEY,
  doctor_id INT NOT NULL,
  day_of_week ENUM('Mon','Tue','Wed','Thu','Fri','Sat','Sun') NOT NULL,
  start_time TIME NOT NULL,
  end_time TIME NOT NULL,
  slot_minutes INT NOT NULL DEFAULT 10,
  FOREIGN KEY (doctor_id) REFERENCES doctors(doctor_id)
);

CREATE TABLE appointments (
  appointment_id INT AUTO_INCREMENT PRIMARY KEY,
  patient_id INT NOT NULL,
  doctor_id INT NOT NULL,
  appt_date DATE NOT NULL,
  slot_time TIME NOT NULL,
  status ENUM('Booked','Completed','Cancelled') NOT NULL DEFAULT 'Booked',
  priority_level TINYINT DEFAULT 4,          -- 1 = critical ... 4 = routine
  token_no INT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  active_key TINYINT GENERATED ALWAYS AS
    (CASE WHEN status = 'Cancelled' THEN NULL ELSE 1 END) STORED,
  UNIQUE KEY uq_active_slot (doctor_id, appt_date, slot_time, active_key),
  FOREIGN KEY (patient_id) REFERENCES patients(patient_id),
  FOREIGN KEY (doctor_id) REFERENCES doctors(doctor_id)
);

CREATE TABLE waitlist (
  waitlist_id INT AUTO_INCREMENT PRIMARY KEY,
  patient_id INT NOT NULL,
  doctor_id INT NOT NULL,
  preferred_date DATE NOT NULL,
  status ENUM('Waiting','Offered','Accepted','Expired') DEFAULT 'Waiting',
  offered_at TIMESTAMP NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (patient_id) REFERENCES patients(patient_id),
  FOREIGN KEY (doctor_id) REFERENCES doctors(doctor_id)
);

CREATE TABLE prescriptions (
  prescription_id INT AUTO_INCREMENT PRIMARY KEY,
  appointment_id INT NOT NULL,
  details TEXT NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (appointment_id) REFERENCES appointments(appointment_id)
);

CREATE TABLE symptom_map (
  symptom_keyword VARCHAR(50) PRIMARY KEY,
  specialization VARCHAR(80) NOT NULL
);

CREATE TABLE audit_log (
  log_id INT AUTO_INCREMENT PRIMARY KEY,
  user_id INT,
  action VARCHAR(255) NOT NULL,
  log_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (user_id) REFERENCES users(user_id)
);

-- Sample symptom mapping
INSERT INTO symptom_map VALUES
 ('chest pain','Cardiologist'), ('palpitations','Cardiologist'),
 ('rash','Dermatologist'), ('itching','Dermatologist'),
 ('headache','Neurologist'), ('seizure','Neurologist'),
 ('fever','General Physician'), ('cough','General Physician'),
 ('joint pain','Orthopedic'), ('fracture','Orthopedic'),
 ('ear pain','ENT'), ('sore throat','ENT');
```

---

## 🧮 Core Algorithms

### 1. Double-booking prevention
The final decision is made by the database, not only by Java code. The unique key `(doctor_id, appt_date, slot_time, active_key)` allows only one *active* booking per slot. Cancelled rows have `active_key = NULL`, so the slot can be rebooked. If two users insert the same slot at the same time, one insert fails with a duplicate-key error and the transaction is rolled back.

### 2. Emergency triage ordering
A `PriorityQueue<Appointment>` is ordered by `priority_level` (1 = critical … 4 = routine) and then by arrival time, so patients with the same level are served first-come-first-served.

> ⚠️ The software only **orders** the queue. The priority level is entered by qualified clinical staff; the system never makes a medical triage decision on its own.

### 3. Symptom-based recommender
Each entered symptom keyword is looked up in a `HashMap<String, String>` (keyword → specialization). The specialization with the most matching keywords is suggested; if nothing matches, *General Physician* is returned. This is a suggestion only, not a diagnosis.

### 4. Estimated waiting time
```
T_wait = N_ahead × T_avg
```
- `N_ahead` – number of patients ahead in the queue  
- `T_avg` – average consultation time (rolling average of the doctor's recent completed visits; default 10 minutes)

Example: 4 patients ahead × 10 minutes = **40 minutes**.

### 5. Smart waitlist
On cancellation the first eligible waiting patient receives an offer (on screen and by e-mail). If the patient accepts, the booking transaction runs. If the patient declines or does not respond within the timeout (default 15 minutes, using `Timer`), the offer passes to the next patient.

---

## 🧱 Object-Oriented Design

- **Encapsulation and data hiding:** entity classes (`Patient`, `Doctor`, `Appointment`) keep fields `private` and expose getters/setters with validation.
- **Inheritance:** abstract class `User` is extended by `Admin`, `Doctor` and `Patient`.
- **Polymorphism:** role-specific dashboards and behaviour are selected through overridden methods; the triage comparator orders `Appointment` objects polymorphically.
- **Abstraction:** DAO interfaces (for example `AppointmentDAO`) separate the contract from the JDBC implementation.
- **Collections and generics:** `List<Appointment>`, `Map<String,String>`, `Set<LocalTime>`, `PriorityQueue<Appointment>`, with `Iterator` for traversal.
- **Exception handling:** custom exceptions (for example `SlotUnavailableException`) and try-catch-finally for SQL and mail errors.
- **Multithreading:** background reminder and waitlist-timeout tasks; synchronised token generation.

---

## 🔐 Security and Privacy

| Area | Measure |
|---|---|
| Authentication | Login required for every role |
| Authorisation | Role-based access: patients see their own records, doctors their own patients, admins management data |
| Password storage | Salted PBKDF2 (`PBKDF2WithHmacSHA256`) from the Java standard library; no plain-text passwords |
| SQL injection | `PreparedStatement` for parameterised queries; input validation |
| Data integrity | Transactions with commit/rollback; unique slot constraint |
| Auditing | `audit_log` records logins and changes |
| Backups | Schedule regular MySQL backups |
| Test data | Sample data only; no real patient records |

---

## 📂 Project Structure

```
HospitalManagementSystem/
├── src/
│   ├── model/      User, Admin, Doctor, Patient, Appointment, ...
│   ├── dao/        JDBC data access classes
│   ├── service/    Booking, waitlist, triage, token queue, recommender
│   ├── ui/         Swing screens (login, registration, booking, schedule, analytics)
│   └── util/       Validation, password hashing, mail, timers
├── sql/
│   └── schema.sql  Database tables and sample data
├── lib/            MySQL Connector/J, JavaMail jars
├── screenshots/    Application screenshots
├── docs/           Project report
└── README.md
```

*(Adjust folder names to match your repository.)*

---

## ⚙ Installation and Setup

### Prerequisites

- JDK 17 or later
- MySQL Server 8
- MySQL Connector/J (JDBC driver)
- JavaMail / Jakarta Mail library (for reminders)
- NetBeans or Eclipse (optional)

### Step 1 – Clone the repository

```bash
git clone https://github.com/<your-username>/<your-repository>.git
cd <your-repository>
```

### Step 2 – Create the database

Open MySQL and run the schema from the section above:

```bash
mysql -u root -p < sql/schema.sql
```

### Step 3 – Configure the connection

Set the database URL, user and password (and SMTP settings for reminders) in the connection/configuration class:

```
URL      : jdbc:mysql://localhost:3306/hms
USER     : <your-mysql-user>
PASSWORD : <your-mysql-password>
```

> Never commit real passwords to GitHub. Use a local configuration file listed in `.gitignore`.

### Step 4 – Add libraries

Add the MySQL Connector/J and JavaMail jars from `lib/` to the project's classpath (Libraries in NetBeans / Build Path in Eclipse).

### Step 5 – Run

- **IDE:** run the main class (the login screen).
- **Command line:**

```bash
javac -cp "lib/*" -d out $(find src -name "*.java")
java -cp "out:lib/*" <your.main.Class>      # use ';' instead of ':' on Windows
```

---

## 🖥 How to Use

### Patient

1. Log in or register as a new patient.
2. Search for a doctor by name, department or specialization (or enter symptoms to get a suggestion).
3. Pick a free slot and confirm the booking.
4. Use **Reschedule** or **Cancel** from your appointments list.
5. Join the **waitlist** if the slot you want is full, and accept the offer if one arrives.
6. Check your **token, queue position and estimated waiting time** on the day.

### Doctor

1. Log in and open the daily appointment list.
2. Update each appointment's status (Booked → Completed / Cancelled).
3. Add prescriptions and view the patient's visit history.
4. Handle emergency cases shown at the top of the triage queue.

### Administrator

1. Add, update or delete doctors.
2. Configure each doctor's schedule (days, hours, slot length).
3. Review workload, cancellations, no-shows and peak hours in the analytics screen.
4. Manage user accounts and review the audit log.

---

## 📸 Screenshots

Add your screenshots to the `screenshots/` folder and link them here.

| Screen | Preview |
|---|---|
| Patient registration | `![Registration](screenshots/registration.png)` |
| Doctor search and slot booking | `![Doctor Search](screenshots/doctor-search.png)` |
| Appointment confirmation | `![Confirmation](screenshots/confirmation.png)` |
| Doctor dashboard | `![Doctor Dashboard](screenshots/doctor-dashboard.png)` |
| Admin analytics | `![Analytics](screenshots/analytics.png)` |

---

## 🧪 Testing

The test plan covers 14 cases, defined before testing began.

| ID | What is tested | Expected result |
|---|---|---|
| T1 | Registration validation | Valid data saved; invalid data rejected |
| T2 | Doctor search | Correct doctors listed; "no result" message shown |
| T3 | Booking | Appointment saved with status Booked |
| T4 | Reschedule / cancel | Old slot freed, new slot held |
| T5 | Simultaneous booking of one slot | Exactly one succeeds, no partial record |
| T6 | Symptom recommender | Correct specialization or General Physician |
| T7 | Waitlist | Offer, acceptance and timeout work correctly |
| T8 | Token queue | Position and wait time follow the formula |
| T9 | Emergency triage | Higher priority served first |
| T10 | Reminders and no-show | Reminder sent on time; no-show recorded |
| T11 | Analytics | Totals match SQL counts |
| T12 | Security | Wrong password refused; role access enforced |
| T13 | Performance | Search and booking within 2 seconds |
| T14 | Rollback | No partial record after a forced error |

**Test results**

| Measure | Result |
|---|---|
| Patients registered in testing | _add your value_ |
| Doctors registered | _add your value_ |
| Successful appointments | _add your value_ |
| Duplicate bookings rejected (T5) | _add your value_ |
| Average booking time | _add your value_ |

*(Fill these from your own test runs.)*

---

## 🎓 Course Outcomes Covered

| CO | Outcome | Where it is applied |
|---|---|---|
| CO1 | OOP: classes, objects, encapsulation, data hiding, inheritance, polymorphism | Entity classes, `User` hierarchy, role dashboards, DAO classes |
| CO2 | Collections: List, ArrayList, Set, Map, Hashtable, HashMap, iterators, generics | Appointment lists, slot sets, symptom map, session table, waitlist iteration |
| CO3 | Multithreading, priorities, synchronisation, inter-thread communication, exception handling | Reminder and waitlist threads, synchronised tokens, custom exceptions |
| CO4 | GUI with AWT, Swing and Applets: event handling, layouts, controls, menus | Swing screens, layout managers, `JMenuBar`, listeners (Applets are deprecated in JDK 17, so Swing is used) |
| CO5 | JDBC: insert, update, delete with different statement types | `PreparedStatement`, `Statement`, transactions |

---

## ⚠ Limitations

- Desktop and LAN use only; no web or mobile client
- Single hospital branch
- Tested with sample data and a small number of concurrent users
- The symptom recommender uses keyword matching; it cannot diagnose
- Emergency priority depends on staff entering the correct level
- Waiting-time estimates are approximate
- Reminder e-mails depend on valid addresses and mail server availability
- No billing, pharmacy, laboratory or insurance integration
- No formal security audit

---

## 🚀 Future Enhancements

- Billing and invoicing; pharmacy and stock management
- Web and mobile apps for patients
- SMS and push notifications
- Laboratory and imaging integration
- IoT devices and AI-based prediction (no-show forecasting, demand prediction)
- Multi-branch support and encrypted backups
- Larger-scale load and concurrency testing

---

## 🔧 Troubleshooting

| Problem | Likely cause and fix |
|---|---|
| `ClassNotFoundException: com.mysql.cj.jdbc.Driver` | Connector/J jar is not on the classpath – add it from `lib/` |
| `Access denied for user` | Wrong MySQL user or password in the configuration |
| `Communications link failure` | MySQL server is not running or the port is not 3306 |
| `Unknown database 'hms'` | Run the schema script first |
| E-mail reminders not sent | Check SMTP host, port, credentials and internet access |
| Duplicate entry error when booking | The slot is already booked – choose another slot (expected behaviour) |

---

## 📄 Documentation

The full capstone report (requirements, design, trade-off analysis, risk register, test plan and reflection) is available in the `docs/` folder.

---

## 👨‍💻 Author

**K. Nikhil**  
Register No.: 192525307  
SIMATS Engineering, Saveetha Institute of Medical and Technical Sciences, Chennai


---

## 🙏 Acknowledgements

- **Mr. N. Vijayaragavan**, Technical Trainer / CSE, for guidance throughout the project
- **Dr. G. Charlyn Pushpa Latha**, Professor / CSE, Course Coordinator
- SIMATS Engineering for the opportunity and resources
- Oracle (Java, JDBC, MySQL) and the Eclipse Foundation (Jakarta Mail) for their documentation
- AI assistance (Claude by Anthropic) was used to help draft the report and this README; the author reviewed and takes responsibility for the content.

---

⭐ If you found this project useful, consider giving the repository a star.
