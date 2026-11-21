# PROGRAMMING IN JAVA – ASSIGNMENT 3 (CO3)

## Student Details

**Student Name:** Karnati Nikhil  
**Register Number:** 192525307  
**Course Code:** CSA0922  
**Subject:** Programming in Java  
**Department:** Computer Science and Engineering – Artificial Intelligence and Machine Learning  
**University:** Saveetha University, Chennai  
**Academic Year:** 2026–2027  



## 1. Assignment Overview

This assignment focuses on Java exception handling, resource management, multithreading, synchronization, deadlock prevention and concurrent programming.

The objective is to understand how Java applications handle runtime failures, manage resources safely and execute multiple tasks concurrently.

The assignment contains seven questions covering practical programming scenarios.

## 2. Objectives

- Understand checked and unchecked exceptions.
- Implement user-defined exceptions and exception propagation.
- Use try-with-resources for safe resource management.
- Create and manage threads using Thread and Runnable.
- Understand thread life cycle and thread coordination.
- Identify and prevent race conditions.
- Understand deadlocks and producer-consumer communication.
- Develop a concurrent processor using ExecutorService, Callable and Future.
- Apply concurrent collections for thread-safe operations.

## 3. Technologies Used

- **Programming Language:** Java
- **Java Version:** Java 8 or later (depending on the APIs used)
- **IDE:** IntelliJ IDEA / Eclipse / VS Code
- **Compiler:** Java Compiler (javac)
- **Version Control:** Git and GitHub

## 4. Assignment Questions

### Q1 – Handling Failure in a Bank ATM Simulation

**Concepts:** Exception handling, try-catch, multi-catch, finally, checked and unchecked exceptions.

Develops an ATM withdrawal simulation that handles invalid input, negative withdrawal amounts, insufficient balance and card-reader file errors.

**Key Learning:** Handling different exceptions using specific catch blocks and ensuring resource cleanup using finally.

### Q2 – User-Defined Exceptions and Propagation in an Online Examination Portal

**Concepts:** Custom exceptions, throw, throws, exception propagation and exception chaining.

Implements an examination submission system with custom exceptions for examination-related and storage-related failures.

**Key Learning:** Creating meaningful application-specific exceptions and preserving the original cause of an error.

### Q3 – Resource Safety, Debugging and Robust Code

**Concepts:** File handling, IOException, AutoCloseable and try-with-resources.

Demonstrates safe reading and writing of files while preventing resource leaks.

**Key Learning:** Automatic resource management and handling suppressed exceptions.

### Q4 – Thread Creation and the Thread Life Cycle

**Concepts:** Thread, Runnable, start(), run(), sleep(), join() and isAlive().

Simulates multiple examination scanner stations processing answer scripts concurrently.

**Key Learning:** Creating threads, understanding thread states and coordinating thread execution.

### Q5 – Race Conditions in a Cinema Seat-Booking System

**Concepts:** Race conditions, critical sections, synchronized methods and synchronized blocks.

Develops a cinema booking system in which multiple users attempt to book seats simultaneously.

**Key Learning:** Protecting shared data and preventing duplicate seat bookings through synchronization.

### Q6 – Deadlock and Inter-Thread Communication

**Concepts:** Deadlock, lock ordering, wait(), notify(), notifyAll() and producer-consumer communication.

Demonstrates safe wallet transfers and a bounded meal-token counter.

**Key Learning:** Preventing deadlocks and coordinating producer and consumer threads.

### Q7 – Design a Concurrent, Fault-Tolerant Processor from First Principles

**Concepts:** ExecutorService, Callable, Future and ConcurrentLinkedQueue.

Designs a concurrent processor to handle 10,000 student score files while recording successful and failed processing operations.

**Key Learning:** Managing worker threads, collecting task results and handling individual task failures without stopping the complete application.

## 5. Repository Structure

The repository can be organized as follows:

```text
CSA09-192525307-Assignment3/
│
├── README.md
│
├── Task01/
│   ├── ATM.java
│   └── output.png
│
├── Task02/
│   ├── ExamPortal.java
│   └── output.png
│
├── Task03/
│   ├── ResourceManagement.java
│   └── output.png
│
├── Task04/
│   ├── ThreadDemo.java
│   └── output.png
│
├── Task05/
│   ├── CinemaBooking.java
│   └── output.png
│
├── Task06/
│   ├── DeadlockProducerConsumer.java
│   └── output.png
│
└── Task07/
    ├── ConcurrentProcessor.java
    └── output.png
```

*Note: The filenames above are suggested examples. Use the actual Java filenames and supporting files from your implementation.*

## 6. How to Compile and Run

### Step 1 – Install Java

Install the Java Development Kit (JDK) and verify the installation:

```bash
java -version
javac -version
```

### Step 2 – Open the Project

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_LINK
```

Open the project folder in your preferred Java IDE or terminal.

### Step 3 – Compile a Program

Navigate to the required task folder and compile the Java source file.

Example:

```bash
javac ATM.java
```

### Step 4 – Execute the Program

```bash
java ATM
```

Repeat the compilation and execution steps for the remaining programs using their actual class names.

**Note:** If a program uses multiple Java source files or packages, compile and execute it according to its package structure.

## 7. Testing and Validation

Each program should be tested using appropriate input values and failure conditions.

| Question | Testing Focus |
|---|---|
| Q1 | Valid withdrawal, invalid input, negative amount and insufficient balance |
| Q2 | Successful submission, expired examination and storage failure |
| Q3 | Successful file reading, missing file and resource closing |
| Q4 | Thread execution, completion and join behaviour |
| Q5 | Multiple simultaneous booking attempts and duplicate booking prevention |
| Q6 | Wallet transfer, deadlock prevention and producer-consumer operations |
| Q7 | Successful processing, missing files, corrupt files and thread pool performance |

Actual program outputs and execution measurements should be recorded after running the programs.

## 8. Expected Results

The assignment demonstrates the following expected outcomes:

- ATM transactions handle invalid operations without unexpected termination.
- Examination submissions report application-specific failures.
- File resources are closed safely.
- Multiple scanner threads execute concurrently.
- Cinema seats are booked without duplicate successful bookings.
- Producer and consumer threads coordinate correctly.
- The concurrent processor records successful and failed files separately.

For Q7, the simulated processing conditions should produce:

- Total Files: 10,000
- Successful Files: 9,800
- Failed Files: 200

**Note:** These counts depend on the specified failure-injection conditions in the program. Execution times must be measured on the actual computer.

## 9. Important Java Concepts Demonstrated

1. Exception hierarchy and exception handling.
2. Checked and unchecked exceptions.
3. User-defined exceptions.
4. Exception propagation and chaining.
5. Try-with-resources and suppressed exceptions.
6. Thread creation and thread life cycle.
7. Synchronization and race condition prevention.
8. Deadlock prevention using consistent lock ordering.
9. Producer-consumer communication.
10. ExecutorService and concurrent collections.

## 10. Learning Outcomes

After completing this assignment, I gained practical knowledge of Java exception handling, resource management and multithreaded programming.

I learned how to identify application failures, create custom exceptions, safely manage files, coordinate multiple threads and protect shared resources.

I also understood how concurrent applications can process multiple independent tasks while handling individual failures reliably.

## 11. Individual Contribution

Both team members should contribute to the implementation, testing and analysis of the seven questions.

The individual contribution record should be completed in the assignment report according to the actual work performed by each student.

## 12. Conclusion

This assignment provided practical experience with important Java programming concepts related to exception handling and concurrency.

The seven programs demonstrate how Java applications can handle failures, manage resources, execute multiple threads, prevent race conditions and process large numbers of tasks concurrently.

Overall, the assignment strengthened my understanding of reliable programming, debugging, synchronization and concurrent application development.

---

**Submitted by:** Karnati Nikhil  
**Register Number:** 192525307  
**Course Code:** CSA0922
**Assignment:** Assignment 3 – CO3  
**Academic Year:** 2026–2027
