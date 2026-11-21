# PROGRAMMING IN JAVA
## ASSIGNMENT – 2
### CO2 – STRINGS, COLLECTIONS AND GENERICS

---

## Student Details

| Details | Information |
|---|---|
| Name | K. Nikhil |
| Register Number | 192525307 |
| Course Code | CSA0922 |
| Subject | Programming in Java |
| Assignment | Assignment 2 – CO2 |
| GitHub Repository | [CSA09 Java Programming](https://github.com/karnatinikhil-sudo/CSA0922-Java-Programming/tree/main/Assignments) |

---

## 1. Assignment Overview

This assignment focuses on Java Strings, Collections Framework and Generics. It contains seven programming tasks designed to demonstrate the practical application of Java concepts, performance analysis, data structure selection and software redesign.

The programs are based on real-world scenarios such as railway ticket generation, music playlists, student attendance, pharmacy inventory, sports leaderboards and hospital emergency management.

## 2. Objectives

- Understand the differences between String, StringBuilder and StringBuffer.
- Compare ArrayList, LinkedList and ArrayDeque.
- Implement the equals() and hashCode() contract.
- Understand HashMap, TreeMap and LinkedHashMap.
- Apply Java Generics and Comparator.
- Implement priority-based scheduling using PriorityQueue.
- Analyse performance bottlenecks and redesign inefficient code.

## 3. Technologies Used

| Technology | Purpose |
|---|---|
| Java | Programming Language |
| JDK | Java Development Kit |
| Collections Framework | Data storage and manipulation |
| Generics | Type-safe reusable programming |
| Comparator | Custom sorting and ranking |
| System.nanoTime() | Performance measurement |
| Git | Version Control |
| GitHub | Source Code Repository |

## 4. Assignment Tasks

### Task 01 – Building Text Under Load: String, StringBuilder or StringBuffer?

**File:** `TicketBenchmark.java`

**Concepts Covered:**
- String immutability
- StringBuilder
- StringBuffer
- String concatenation
- Performance benchmarking
- System.nanoTime()

**Objective:** Compare the performance of String, StringBuilder and StringBuffer while generating railway e-tickets with different workloads.

### Task 02 – When Is ArrayList an Appropriate Engineering Choice?

**File:** `PlaylistComparison.java`

**Concepts Covered:**
- ArrayList
- LinkedList
- ArrayDeque
- Collection operations
- Time complexity analysis

**Objective:** Compare different collection implementations for music playlist operations and select a suitable data structure for an Up Next queue.

### Task 03 – Engineer the HashCode–Equals Contract

**File:** `Attendance.java`

**Concepts Covered:**
- equals()
- hashCode()
- HashSet
- Object equality
- Duplicate identification

**Objective:** Create a student attendance system that prevents duplicate registration numbers using HashSet.

### Task 04 – Choosing a Map for a Pharmacy Inventory

**File:** `PharmacyInventory.java`

**Concepts Covered:**
- HashMap
- TreeMap
- LinkedHashMap
- Key-value storage
- Sorting and searching

**Objective:** Develop a pharmacy inventory system and compare Map implementations based on lookup performance and ordering requirements.

### Task 05 – Derive a Generic Ranking Component from a Principle

**File:** `LeaderboardDemo.java`

**Concepts Covered:**
- Java Generics
- Comparator
- ArrayList
- Custom sorting
- Reusable components

**Objective:** Develop a generic leaderboard that ranks sports teams based on points, goal difference and alphabetical order.

### Task 06 – Priority, Order and Fairness in a Queue

**File:** `Triage.java`

**Concepts Covered:**
- PriorityQueue
- Comparator
- Queue operations
- Priority-based scheduling
- FIFO tie-breaking
- Starvation and aging

**Objective:** Develop a hospital emergency triage simulation that selects patients based on severity while maintaining arrival order for equal priorities.

### Task 07 – Diagnose, Redesign and Validate

**File:** `TicketRedesign.java`

**Concepts Covered:**
- Performance optimization
- String immutability
- StringBuilder
- Code redesign
- Output validation
- Complexity analysis

**Objective:** Identify the performance limitations of repeated String concatenation and redesign the program using StringBuilder.

---

## 5. Project Folder Structure

```text
CSA09-192525307-Assignment2/
│
├── Task01/
│   ├── TicketBenchmark.java
│   └── output.png
│
├── Task02/
│   ├── PlaylistComparison.java
│   └── output.png
│
├── Task03/
│   ├── Attendance.java
│   └── output.png
│
├── Task04/
│   ├── PharmacyInventory.java
│   └── output.png
│
├── Task05/
│   ├── LeaderboardDemo.java
│   └── output.png
│
├── Task06/
│   ├── Triage.java
│   └── output.png
│
├── Task07/
│   ├── TicketRedesign.java
│   └── output.png
│
└── README.md
```

---

## 6. How to Compile and Execute

### Prerequisites

- Java Development Kit (JDK) installed.
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
cd Task01
```

### Step 3: Compile the Java Program

```bash
javac TicketBenchmark.java
```

### Step 4: Execute the Program

```bash
java TicketBenchmark
```

Repeat the same procedure for the remaining task files, using their respective class names.

---

## 7. Expected Learning Outcomes

After completing this assignment, I gained practical knowledge of:

1. Selecting suitable String handling classes for different workloads.
2. Comparing Java collection data structures.
3. Implementing object equality correctly.
4. Selecting suitable Map implementations.
5. Creating reusable generic components.
6. Managing priority-based queue operations.
7. Analysing and improving program performance.

## 8. Testing and Validation

All seven programs are designed to demonstrate their respective Java concepts.

- Compile each program independently.
- Execute each program using the required inputs or predefined test data.
- Verify the output against the expected results.
- Capture screenshots of successful execution.
- Record actual performance measurements where applicable.
- Validate redesigned programs against their original outputs.

**Note:** Benchmark execution times depend on the computer, Java version and system load. Actual measured values should be recorded after execution.

## 9. Conclusion

This assignment helped me understand the practical applications of Java Strings, Collections and Generics through different real-world programming scenarios.

By implementing seven different programs, I learned how to select appropriate data structures, compare their performance, implement custom sorting, maintain object equality and optimize inefficient code.

The assignment also improved my understanding of Java programming practices, time complexity analysis, code validation and performance optimization.

---

## 10. Author Information

**Name:** K. Nikhil

**Register Number:** 192525307

**Department:** Computer Science and Engineering – Artificial Intelligence and Machine Learning

**Institution:** Saveetha University

**Course:** Programming in Java

**Course Code:** CSA0922

---

**Assignment 2 – CO2: Strings, Collections and Generics**

**END OF README**
