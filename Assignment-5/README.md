# PROGRAMMING IN JAVA

## ASSIGNMENT – 5

### CO5 – DATA PERSISTENCE ENGINEERING: FILES AND DATABASES

---

## Student Details

| Details | Information |
|---|---|
| Name | K. Nikhil |
| Register Number | 192525307 |
| Course Code | CSA0922 |
| Subject | Programming in Java |
| Assignment | Assignment 5 – CO5 |


---

## 1. Assignment Overview

This assignment focuses on Java data persistence engineering using files, object serialization and databases. It contains multiple design and implementation tasks that demonstrate how data can be stored, retrieved, validated and managed efficiently.

The programs are based on practical scenarios such as university bus-pass management, attendance log processing, student database management, hostel resident records and financial transactions.

The assignment also focuses on performance optimization, database security, transaction management, JDBC connectivity and reliable data storage.

## 2. Objectives

- Understand text-file and binary-file handling in Java.
- Implement file reading and writing using buffered streams.
- Design suitable file formats for storing records.
- Understand Java object serialization and deserialization.
- Apply the Data Access Object (DAO) design pattern.
- Compare Statement and PreparedStatement.
- Implement JDBC database operations.
- Understand database transactions and rollback.
- Prevent SQL injection using PreparedStatement.
- Analyse file-processing and database performance.
- Design reliable data migration strategies.

## 3. Technologies Used

| Technology | Purpose |
|---|---|
| Java | Programming Language |
| JDK | Java Development Kit |
| File Handling | Data storage and retrieval |
| BufferedReader | Efficient text-file reading |
| BufferedWriter | Efficient text-file writing |
| Serialization | Object persistence |
| JDBC | Java Database Connectivity |
| MySQL | Relational Database Management |
| PreparedStatement | Secure SQL execution |
| DatabaseMetaData | Database information |
| System.nanoTime() | Performance measurement |
| Git | Version Control |
| GitHub | Source Code Repository |

## 4. Assignment Tasks

### PART A – PERSISTENCE DESIGN AND PSEUDOCODE

### Task A1 – Design a File Format

**File:** `PassStore.java`

**Concepts Covered:**

- Text-file storage
- Delimited file formats
- DataOutputStream
- BufferedReader
- BufferedWriter
- RandomAccessFile
- File validation
- Error handling

**Objective:** Design suitable text and binary file formats for storing university bus-pass records. Develop operations to add records, search by Pass ID and list passes based on route number.

### Task A2 – Don't Read What You Don't Need

**File:** `BufferedCounter.java`

**Concepts Covered:**

- FileInputStream
- BufferedInputStream
- Buffered reading
- File processing
- Performance measurement
- Time and space complexity

**Objective:** Compare unbuffered and buffered file reading while processing large attendance log files. Analyse the effect of buffer size on execution performance.

### Task A3 – Discover the Data-Access Design Pattern

**Files:** `Dao.java`, `Student.java`, `StudentDao.java`

**Concepts Covered:**

- Data Access Object (DAO)
- Generic interfaces
- JDBC
- Database operations
- Object-relational mapping
- Code reusability
- Separation of responsibilities

**Objective:** Design a reusable data-access structure for StudentDB, CourseDB and MarksDB. Implement a generic DAO interface for common database operations.

### Task A4 – What Should Be Serialized?

**File:** `Resident.java`

**Concepts Covered:**

- Java Serialization
- Serializable interface
- ObjectOutputStream
- ObjectInputStream
- Transient variables
- serialVersionUID
- Object persistence

**Objective:** Design a serialization approach for hostel records containing Hostel, Room and Resident objects. Identify the fields that should be serialized and the fields that should be excluded.

### Task A5 – Design for Correctness and Safety

**File:** `TransactionDemo.java`

**Concepts Covered:**

- JDBC transactions
- Commit and rollback
- Auto-commit
- SQL injection
- PreparedStatement
- Database consistency
- Secure database operations

**Objective:** Design a safe financial transfer operation between hostel and canteen wallets. Identify SQL injection risks and implement secure SQL queries using PreparedStatement.

---

### PART B – IMPLEMENTATION AND EXPERIMENTAL INVESTIGATION

### Task B1 – Implement and Instrument the File Store

**Files:** `PassStore.java`, `LineCounterBenchmark.java`

**Concepts Covered:**

- File creation
- File reading and writing
- Record searching
- Route-based filtering
- Damaged-record handling
- Buffered streams
- Performance benchmarking
- Complexity analysis

**Objective:** Implement a bus-pass file storage system that supports adding, searching and listing records. Compare buffered and unbuffered file-reading performance using different file sizes.

### Task B2 – Engineer an Adversarial Input

**File:** `LoginTest.java`

**Concepts Covered:**

- SQL injection
- Unsafe SQL queries
- Statement
- PreparedStatement
- Input validation
- Database security
- Error handling

**Objective:** Demonstrate how malicious input can affect an unsafe SQL query and compare it with a secure implementation using PreparedStatement. Test damaged bus-pass records and verify that invalid records are handled safely.

### Task B3 – Statement vs PreparedStatement vs Batch

**File:** `PassLoader.java`

**Concepts Covered:**

- JDBC
- Statement
- PreparedStatement
- Batch processing
- executeBatch()
- Database transactions
- Commit and rollback
- Database metadata

**Objective:** Implement bulk insertion of bus-pass records using PreparedStatement batching. Compare the performance of Statement, PreparedStatement and batch insertion for different record counts.

### Task B4 – Final Engineering Decision

**File:** `DatabaseInfo.java`

**Concepts Covered:**

- DatabaseMetaData
- Database migration
- JDBC connectivity
- Database inspection
- Data consistency
- Scalability
- Persistence design

**Objective:** Develop a practical migration strategy for moving bus-pass records from text files into a relational database. Inspect database information and evaluate suitable persistence solutions for a university with multiple campuses.

---

## 5. Project Folder Structure

```text
CSA09-192525307-Assignment5/
│
├── PartA/
│   │
│   ├── TaskA1/
│   │   ├── PassStore.java
│   │   └── output.png
│   │
│   ├── TaskA2/
│   │   ├── BufferedCounter.java
│   │   └── output.png
│   │
│   ├── TaskA3/
│   │   ├── Dao.java
│   │   ├── Student.java
│   │   ├── StudentDao.java
│   │   └── output.png
│   │
│   ├── TaskA4/
│   │   ├── Resident.java
│   │   └── output.png
│   │
│   └── TaskA5/
│       ├── TransactionDemo.java
│       └── output.png
│
├── PartB/
│   │
│   ├── TaskB1/
│   │   ├── PassStore.java
│   │   ├── LineCounterBenchmark.java
│   │   └── output.png
│   │
│   ├── TaskB2/
│   │   ├── LoginTest.java
│   │   └── output.png
│   │
│   ├── TaskB3/
│   │   ├── PassLoader.java
│   │   ├── bus_pass.sql
│   │   └── output.png
│   │
│   └── TaskB4/
│       ├── DatabaseInfo.java
│       └── output.png
│
└── README.md
```

---

## 6. How to Compile and Execute

### Prerequisites

- Java Development Kit (JDK) installed.
- MySQL Server installed.
- MySQL Connector/J JDBC driver.
- Command Prompt or Terminal.
- Any Java IDE (VS Code, IntelliJ IDEA or Eclipse).

### Step 1: Check Java Installation

```bash
java -version
javac -version
```

### Step 2: Navigate to a Task Folder

Example:

```bash
cd TaskB1
```

### Step 3: Compile the Java Program

```bash
javac PassStore.java
```

### Step 4: Execute the Program

```bash
java PassStore
```

Repeat the same procedure for the remaining Java programs using their respective class names.

### Step 5: Configure MySQL

Create the assignment database:

```sql
CREATE DATABASE assignment5;
USE assignment5;
```

Execute the required SQL scripts before running the database-related programs.

Update the database URL, username and password in the JDBC programs according to the local MySQL configuration.

For JDBC programs, include the MySQL Connector/J library in the classpath.

---

## 7. Expected Learning Outcomes

After completing this assignment, I gained practical knowledge of:

1. Designing suitable file formats for data storage.
2. Reading and writing files using Java streams.
3. Improving file-processing performance through buffering.
4. Implementing Java object serialization.
5. Applying the DAO design pattern.
6. Managing database operations using JDBC.
7. Understanding commit and rollback operations.
8. Preventing SQL injection using PreparedStatement.
9. Performing batch database operations.
10. Analysing performance and selecting suitable persistence methods.

## 8. Testing and Validation

All programs are designed to demonstrate their respective Java concepts.

- Compile each Java program independently.
- Execute the programs using the provided sample data.
- Verify file creation, reading and searching operations.
- Test damaged records and invalid input.
- Compare buffered and unbuffered reading performance.
- Verify database records using SQL queries.
- Test transaction rollback behaviour.
- Compare Statement, PreparedStatement and batch operations.
- Capture screenshots of successful program execution.
- Record actual performance measurements after execution.

**Note:** Benchmark execution times depend on the computer, Java version, database configuration and system load. Actual measured values should be recorded after execution.

## 9. Conclusion

This assignment helped me understand the practical implementation of data persistence techniques in Java through different real-world scenarios.

By completing the design and implementation tasks, I gained knowledge of file handling, buffered streams, object serialization, JDBC connectivity, database transactions and secure SQL execution.

The assignment also improved my understanding of performance optimization, data validation, database consistency and reliable data management.

These concepts are useful for developing scalable Java applications that require secure and efficient storage and retrieval of information.

---

## 10. Author Information

**Name:** K. Nikhil

**Register Number:** 192525307

**Department:** Computer Science and Engineering – Artificial Intelligence and Machine Learning

**Institution:** Saveetha University

**Course:** Programming in Java

**Course Code:** CSA0922

---

**Assignment 5 – CO5: Data Persistence Engineering – Files and Databases**

**END OF README**
