# Java Learning Journey 🚀

A collection of Java programs written while learning Java — starting from core OOP concepts and exception handling, up to a full JDBC-based console application. This repo documents the progression from small practice programs to a complete database-driven project.

## 📂 Repository Structure

```
.
├── CalculatorDemo.java
├── shapeDemo.java
├── EB_bill.java
├── employeeDemo.java
├── Main.java
├── TravelManagement.java
├── FileDemo.java
├── EmployeeManagement.java
└── HospitalManagement.java
```

## 🧩 Practice Programs

| File | Concept | Description |
|---|---|---|
| `CalculatorDemo.java` | Interfaces | A simple calculator (`Calculator` interface implemented by `myCalculator`) that performs addition, subtraction, multiplication and division, with division-by-zero handling. |
| `shapeDemo.java` | Abstract classes & Inheritance | An abstract `shape` class extended by `rectangle` and `circle` classes that each calculate their own area. |
| `EB_bill.java` | Conditionals | Calculates an electricity bill using slab-based rates for domestic and commercial connections. |
| `employeeDemo.java` | Classes & Objects | An `Employee` class that calculates salary components (DA, HRA, PF, Staff Club) and prints a formatted payslip. |
| `Main.java` | Custom Exceptions, Interfaces | A basic bank account system (`SavingsAccount`) supporting deposit, withdraw and balance check, with custom `InsufficientBalanceException` and `InvalidInputException`. |
| `TravelManagement.java` | Collections (ArrayList) | A menu-driven program to add, insert, search and display a list of cities using `ArrayList`. |
| `FileDemo.java` | File I/O | Copies the contents of one file to another using `FileInputStream` / `FileOutputStream`. |

## 🏥 Featured Project: Hospital Management System

A console-based **Patient Management System** — the most complete project in this repo — using JDBC to connect to a MySQL database.

**Features:**
- Add Patient — stores ID, name, age, gender, phone, admission date, illness, assigned doctor and ward
- View Patients — lists all records
- Update Patient Phone
- Delete Patient
- Search Patient by ID
- Search Patient by Joining Date

## 💼 Also Included: Employee Management System

`EmployeeManagement.java` — a menu-driven JDBC program to add, view, update and delete employee records (ID, name, department, salary) in a MySQL database.

## 🛠 Tech Stack

- **Java** (core Java, OOP concepts)
- **JDBC** with **MySQL** (for `EmployeeManagement.java` and `HospitalManagement.java`)

## ▶️ How to Run

### Simple programs

Each standalone file can be compiled and run on its own:

```bash
javac ProgramName.java
java ProgramName
```

### Database-driven programs (`EmployeeManagement.java`, `HospitalManagement.java`)

**Prerequisites:**
- Java JDK 8+
- MySQL Server
- [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/) (JDBC driver JAR)

**1. Employee Management — create the database:**
```sql
CREATE DATABASE company;
USE company;

CREATE TABLE employee (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    department VARCHAR(50),
    salary DOUBLE
);
```

**2. Hospital Management — create the database:**
```sql
CREATE DATABASE hospital;
USE hospital;

CREATE TABLE patient (
    patient_id INT PRIMARY KEY,
    patient_name VARCHAR(100),
    age INT,
    gender VARCHAR(10),
    phone VARCHAR(15),
    joining_date DATE,
    affected_with VARCHAR(100),
    assigned_doctor VARCHAR(100),
    assigned_ward VARCHAR(50)
);
```

**3. Update credentials** in the relevant `.java` file:
```java
static final String URL = "jdbc:mysql://localhost:3306/<db_name>";
static final String USER = "root";
static final String PASSWORD = "your_password";
```

**4. Compile and run with the JDBC driver on the classpath:**
```bash
javac -cp .:mysql-connector-j-x.x.x.jar HospitalManagement.java
java -cp .:mysql-connector-j-x.x.x.jar HospitalManagement
```
> On Windows, replace `:` with `;` in the classpath.

## 📌 Note

These programs were written while learning Java fundamentals and JDBC, and are meant for practice/reference rather than production use.
