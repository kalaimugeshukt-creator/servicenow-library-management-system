# ServiceNow Library Management System

A complete Library Management System built on the ServiceNow platform to streamline book borrowing, approvals, and tracking using automation, role-based access, and reporting.

---

## Project Overview

This project focuses on automating and managing library operations efficiently within ServiceNow. It enables students to request books and librarians to approve and manage those requests with minimal manual effort.

The system leverages ServiceNow features such as Flow Designer, ACLs, UI Policies, and custom tables to ensure a secure and scalable solution.

---

## Objectives

- Implement role-based access control (Student & Librarian)
- Create custom tables for managing books and borrow requests
- Automate approval workflows using Flow Designer
- Ensure data security using ACLs
- Improve user experience with UI Policies
- Generate reports for tracking library usage

---

## Technologies Used

- **ServiceNow Platform**
- Flow Designer
- Access Control Rules (ACLs)
- UI Policies
- Reference Qualifiers
- Reporting & Analytics

---

## Features

- Book catalog management
- Student book request system
- Librarian approval workflow
-  Automated status updates
-  Role-based access control
-  Reports (Most Borrowed Books)
-  Email notifications

---

## System Architecture

### Roles
- **Student** → Can view books and request borrowing
- **Librarian** → Full access (approve, update, delete)

### Tables
- **Book Table**
  - Title
  - Author
  - Status (Available / Issued)

- **Borrow Request Table**
  - Book (Reference)
  - Requested By
  - Status
  - Return Date

---

## Implementation Steps

### 1️.Role Creation
- Navigate to **User Administration → Roles**
- Create:
  - `student`
  - `librarian`
- Assign roles to users

---

### 2️.Table Creation
- Navigate to **System Definition → Tables**
- Create:
  - `Book`
  - `Borrow Request`
- Add required fields (Title, Author, Status, etc.)

---

### 3️.Reference Qualifier
- Configure Book field in Borrow Request table
- شرط: Show only books where `Status = Available`

---

### 4. Flow Designer Automation
- Create Flow: **Borrow Request Approval Flow**

**Trigger:**
- When Borrow Request is created with Status = Requested

**Actions:**
- Approval by Librarian
- Update:
  - Book → Issued
  - Request → Approved
- Send Email Notification

---

### 5️. UI Policies
- Example:
  - Make **Return Date mandatory** when Status = Issued

---

### 6️.Access Control (ACLs)
- Book Table:
  - Student → Read only
  - Librarian → Full access

---

### 7. Reporting
- Create Report: **Most Borrowed Books**
- Table: Borrow Request
- Group by: Book
- Aggregate: Count
- Filter: Status = Approved

---

## Sample Output

- Book availability tracking
- Borrow request approval system
- Reports showing popular books

---

## Future Enhancements

-  Automated overdue reminders (Scheduled Jobs)
-  SMS/Push Notifications
-  Integration with digital libraries
-  Advanced analytics dashboards
-  Extend system for asset management

---

## Conclusion

This project demonstrates how ServiceNow can be used beyond ITSM to build real-world business applications. It improves efficiency, reduces manual work, and ensures secure, automated library operations.

---

## Author

**Mugesh K**  
B.Tech Information Technology 

---
