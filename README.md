
# Java Hospital Management System

A console-based Java application for managing hospital operations—patient registration, doctor listings, and appointment bookings using a MySQL database.

---

##  Features
- **Patient Management**: Add and list patients.
- **Doctor Management**: Add and list doctors.
- **Appointment Scheduling**: Book appointments, verifying doctor availability.
- **Exit**: Gracefully close the application and close the database connection.

---

##  Technologies Used
- **Programming Language:** Java  
- **Database:** MySQL (via JDBC)  
- **Dependencies:** MySQL Connector/J  
- **Tools:** Any Java-compatible IDE like Eclipse, IntelliJ, or VS Code

---

##  Prerequisites
1. **Java Development Kit (JDK)** (version 8 or above)  
2. **MySQL Server** installed and running  
3. Download **MySQL Connector/J** and place it in a `lib` folder in the project directory

---

##  Setup Instructions

### 1. Database Setup
```sql
CREATE DATABASE hospital;
USE hospital;

CREATE TABLE patients (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  age INT,
  gender VARCHAR(10)
);

CREATE TABLE doctors (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  specialty VARCHAR(100)
);

CREATE TABLE appointments (
  id INT AUTO_INCREMENT PRIMARY KEY,
  patient_id INT NOT NULL,
  doctor_id INT NOT NULL,
  appointment_date DATE,
  FOREIGN KEY (patient_id) REFERENCES patients(id),
  FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
