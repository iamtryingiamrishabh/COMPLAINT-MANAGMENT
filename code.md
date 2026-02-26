

CREATE DATABASE Complaint_Management_System;
USE Complaint_Management_System;

CREATE TABLE User (
    User_ID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE NOT NULL,
    Phone VARCHAR(15) UNIQUE NOT NULL,
    Address VARCHAR(255) NOT NULL
);


CREATE TABLE Category (
    Category_ID INT PRIMARY KEY AUTO_INCREMENT,
    Category_Name VARCHAR(100) NOT NULL,
    Department VARCHAR(100) NOT NULL,
    Priority_Level ENUM('Low','Medium','High','Critical') NOT NULL,
    SLA_Days INT NOT NULL CHECK (SLA_Days > 0)
);

CREATE TABLE Admin (
    Admin_ID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(100) NOT NULL,
    Role VARCHAR(50) NOT NULL,
    Email VARCHAR(100) UNIQUE NOT NULL,
    Work_Shift ENUM('Morning','Evening','Night') NOT NULL
);

CREATE TABLE Complaint (
    Complaint_ID INT PRIMARY KEY AUTO_INCREMENT,
    User_ID INT NOT NULL,
    Category_ID INT NOT NULL,
    Admin_ID INT,
    Title VARCHAR(200) NOT NULL,
    Description TEXT NOT NULL,
    Date_Filed DATE NOT NULL,
    Status ENUM('Pending','In Progress','Resolved','Closed') DEFAULT 'Pending',

    FOREIGN KEY (User_ID) REFERENCES User(User_ID)
        ON DELETE CASCADE
        ON UPDATE CASCADE,

    FOREIGN KEY (Category_ID) REFERENCES Category(Category_ID)
        ON DELETE CASCADE
        ON UPDATE CASCADE,

    FOREIGN KEY (Admin_ID) REFERENCES Admin(Admin_ID)
        ON DELETE SET NULL
        ON UPDATE CASCADE
);


CREATE TABLE Resolution (
    Resolution_ID INT PRIMARY KEY AUTO_INCREMENT,
    Complaint_ID INT UNIQUE NOT NULL,
    Remarks TEXT NOT NULL,
    Date_Resolved DATE NOT NULL,
    Feedback VARCHAR(255),
    Solution_Type VARCHAR(100) NOT NULL,

    FOREIGN KEY (Complaint_ID) REFERENCES Complaint(Complaint_ID)
        ON DELETE CASCADE
        ON UPDATE CASCADE
);


INSERT INTO User (Name, Email, Phone, Address)
VALUES ('Rahul Sharma', 'rahul@gmail.com', '9876543210', 'Delhi');

INSERT INTO Category (Category_Name, Department, Priority_Level, SLA_Days)
VALUES ('Network Issue', 'IT Department', 'High', 3);

INSERT INTO Admin (Name, Role, Email, Work_Shift)
VALUES ('Anita Verma', 'Support Manager', 'anita@cms.com', 'Morning');