# JAVA PROGRAMMING – ASSIGNMENT 4

## Course Details

**Course Name:** Programming in Java  
**Course Code:** CSA0922  
**Assignment:** Assignment 4 – Event-Driven GUI Design  
**Student Name:** Karnati Nikhil  
**Register Number:** 192525307
**University:** Saveetha University, Chennai

---

## 1. Project Description

This repository contains the Java programs and design solutions developed for Assignment 4. The assignment focuses on Java programming concepts, event handling, GUI design, input validation, object-oriented programming and database connectivity.

The programs demonstrate the working logic of student fee payment, library search, mouse click handling, currency conversion and campus event registration.

## 2. Technologies Used

- Programming Language: Java
- GUI Technology: AWT and Swing (for the full GUI implementations)
- Database: MySQL (for the full Task 6 implementation)
- Database Connectivity: JDBC
- IDE: IntelliJ IDEA / Eclipse / VS Code
- Version Control: Git and GitHub

## 3. Assignment Tasks

### Task 1 – Student Fee Payment System
- Accepts student registration number and fee amount.
- Validates the entered details.
- Displays payment confirmation.
- Generates a payment receipt message.
- Includes Clear and Pay operations.

### Task 2 – Hospital Appointment Desk
- Identifies event sources and event listeners.
- Explains the component hierarchy.
- Provides pseudocode for appointment booking.
- Describes event handling and application lifecycle.

### Task 3 – Campus Library Search System
- Searches for books using keywords.
- Displays matching search results.
- Demonstrates result filtering.
- Explains layout management and resizing.

### Task 4 – Drawing Pad
- Demonstrates mouse click event handling.
- Stores mouse coordinates.
- Maintains a click counter.
- Demonstrates redrawing stored points.

### Task 5 – Currency Converter
- Converts Indian Rupees into US Dollars.
- Demonstrates four event-handling approaches:
  1. Separate ActionListener implementation
  2. Named inner class
  3. Anonymous inner class
  4. Lambda expression

### Task 6 – Campus Event Registration System
- Registers student details.
- Validates input fields.
- Rejects duplicate registrations.
- Displays registered student records.
- Filters registrations by event.
- Exports registration details to CSV.

## 4. Repository Structure

```text
CSA09-RegisterNumber-Assignment4/
│
├── Task01/
│   ├── Main.java
│   └── Output.png
│
├── Task02/
│   └── Design_Document.pdf
│
├── Task03/
│   ├── Main.java
│   └── Output.png
│
├── Task04/
│   ├── Main.java
│   └── Output.png
│
├── Task05/
│   ├── Main.java
│   └── Output.png
│
├── Task06/
│   ├── Main.java
│   ├── registrations.csv
│   └── Output.png
│
└── README.md
```

## 5. How to Compile and Execute

The console demonstration programs can be executed using an online Java compiler or a local JDK.

Compile:

```bash
javac Main.java
```

Run:

```bash
java Main
```

Each task should be executed separately because each contains its own `Main` class.

**Note:** The console programs demonstrate the application logic. The full assignment GUI requirements need separate AWT/Swing implementations. Task 6's full database implementation requires MySQL and JDBC configuration.

## 6. Sample Test Cases

| Task | Test | Expected Result |
|---|---|---|
| 1 | Valid fee details | Payment successful |
| 1 | Invalid fee amount | Error message |
| 3 | Search for Java | Matching book displayed |
| 4 | Five mouse-click samples | Click count is 5 |
| 5 | Convert Rs. 1000 | USD 12.0 at the illustrative rate |
| 6 | New student registration | Registration successful |
| 6 | Duplicate student ID | Registration rejected |
| 6 | Empty student details | Validation message |
| 6 | Export records | CSV file created |

## 7. Learning Outcomes

Through this assignment, I gained an understanding of:

- Java event handling.
- AWT and Swing GUI concepts.
- Input validation and exception handling.
- Mouse event handling.
- Lambda expressions and inner classes.
- Java collections.
- File handling and CSV export.
- JDBC and database connectivity concepts.

## 8. Conclusion

This assignment helped me understand the practical implementation of Java programming concepts through different application scenarios. It improved my knowledge of event handling, GUI design, validation, object-oriented programming and database-related operations.

---

**Submitted by:** Karnati Nikhil  
**Course Code:** CSA0922  
**Assignment:** 4 – Event-Driven GUI Design
