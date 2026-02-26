#  📌 Complaint Management System

## 📖 Description
The Complaint Management System is a relational database project developed to manage complaints efficiently within an organization.
The system stores user information, complaint details, categories, administrator data, and resolution records in a structured format. It ensures proper tracking, accountability, and data integrity using SQL 
and relational database concepts.
This project demonstrates practical implementation of:
Relational Database Design
Entity-Relationship Modeling
Primary Keys & Foreign Keys
Data Constraints
Cardinality
SQL Table Creation

### 📄 Abstract
In many organizations, complaint handling is often unorganized and inefficient. The Complaint Management System provides a structured database solution to store, categorize, and resolve complaints systematically.
The system allows:
Users to register complaints
Complaints to be categorized by department and priority
Administrators to manage complaints
Resolutions to be recorded with feedback
By using a relational database model, the system maintains consistency, avoids redundancy, and ensures efficient complaint tracking.

####  👨‍💻 Team Members
Rakesh Kumar Sharma – 2410030539
Ram – 2410030771
Rishabh Gupta – 2410030550
Rishabh Prasad – 2410030561

##### 🛠 Tools Used
MySQL – Database Management System
SQL – Structured Query Language
Draw.io – ER Diagram Design
VS Code – Code Editor
GitHub – Project Hosting & Version Control

##### 🗂 Entities and Attributes
1️⃣  User
User_ID (PK)
Name
Email
Phone
Address

2️⃣ Complaint
Complaint_ID (PK)
Title
Description
Date_Filed
Status

3️⃣ Category
Category_ID (PK)
Category_Name
Department
Priority_Level
SLA_Days

4️⃣ Admin
Admin_ID (PK) 
Name
Role
Email
Work_Shift

5️⃣ Resolution
Resolution_ID (PK)
Remark
Date_Resolved
Feedback
Solution_Type

###### 🔗 Relationships Between Entities

Even though attributes are defined separately, the logical relationships between entities are:

1️⃣ User – Complaint
One User can file multiple Complaints
Each Complaint belongs to one User
Cardinality: 1 : M

2️⃣ Category – Complaint
One Category can contain multiple Complaints
Each Complaint belongs to one Category
Cardinality: 1 : M

3️⃣ Admin – Complaint
One Admin can handle multiple Complaints
Each Complaint is assigned to one Admin
Cardinality: 1 : M

4️⃣ Complaint – Resolution
One Complaint has one Resolution
Each Resolution belongs to one Complaint
Cardinality: 1 : 1
