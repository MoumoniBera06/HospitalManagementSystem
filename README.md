# Hospital Management System (Java + MySQL)

A simple console-based hospital management system in Java that lets you manage patients, doctors, and appointments using a MySQL database.  

## Features
- Add and view patients  
- Add and view doctors  
- Book appointments and check doctor availability  
- Data stored in MySQL for persistence  

## Requirements
- Java JDK  
- MySQL server  
- MySQL JDBC Driver  
- Database schema (`hospital`) set up as below:

```
CREATE DATABASE hospital;

USE hospital;

CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    gender VARCHAR(10)
);

CREATE TABLE doctors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50),
    specialization VARCHAR(50)
);

CREATE TABLE appointments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    patient_id INT,
    doctor_id INT,
    appointment_date DATE,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
```

### Adding Sample Doctors
INSERT INTO doctors (name, specialization) VALUES
('Alice Smith', 'Cardiologist'),
('Bob Johnson', 'Dermatologist'),
('Carol Brown', 'Neurologist'),
('Daniel White', 'Pediatrician'),
('Emily Davis', 'Orthopedic Surgeon');

## How to Run
1. Compile the program:  
javac HospitalManagementSystem.java

2. Run the program and follow the menu:  
HOSPITAL MANAGEMENT SYSTEM
1. Add Patient
2. View Patients
3. View Doctors
4. Book Appointment
5. Exit

### Example
Adding a patient:  
Enter Patient Name: Arjun
Enter Patient Age: 27
Enter Patient Gender: Male
Patient Added Successfully!!

Viewing patients or doctors displays them in a table.  

Booking an appointment:  
Enter Patient Id: 1
Enter Doctor Id: 2
Enter appointment date (YYYY-MM-DD): 2025-03-18
Appointment Booked!

If the doctor is unavailable, it will notify:  
Doctor not available on this date!!

## Database Configuration
Update your database credentials in HospitalManagementSystem.java:

private static final String url = "jdbc connection string";
private static final String username = "root";
private static final String password = "your_password";


## Contributing
Fork and submit pull requests to improve the project.
