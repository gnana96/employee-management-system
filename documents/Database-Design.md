# Employee Management System - Database Design

## 1. Department

### Purpose
Stores department information.

### Columns
| Column | Data Type | Description |
|---|---|---|
| department_id | BIGINT | Unique department ID |
| department_name | VARCHAR | Department name |
| description | VARCHAR | Description |
| created_at | Date | created date |
| updated_at | Date | updated date |

### Primary Key
- department_id

### Foreign Keys
- None

---

## 2. Employee

### Purpose
Stores employee information.

### Columns
| Column | Data Type | Description |
|---|---|---|
| employee_id | BIGINT | Unique employee ID |
| employee_code | BIGINT | employee_code |
| first_name | VARCHAR | Employee first name |
| last_name | VARCHAR | Employee last name |
| email | VARCHAR | Employee email |
| phone | BIGINT | phone number |
| date_of_birth | Date | date_of_birth |
| joining_date | Date | joining_date |
| salary | BIGINT | salary |
| department_id | BIGINT | Employee department |
| user_id | BIGINT | user_id |
| created_at | Date | created date |
| updated_at | Date | updated date |

### Primary Key
- employee_id

### Foreign Keys
- department_id → Department.department_id

---

## 3. User

### Purpose
Stores login information.

### Columns
| Column | Data Type | Description |
|---|---|---|
| id | BIGINT | ID |
| user_name | VARCHAR | User name |
| password | VARCHAR | password |
| role | VARCHAR | role |
| enabled | VARCHAR | enabled |
| created_at | Date | created date |
| updated_at | Date | updated date |

### Primary Key
- id

### Foreign Keys
- None

---

## 4. Attendance

### Purpose
Stores attendance records.

### Columns
| Column | Data Type | Description |
|---|---|---|
| id | BIGINT | ID |
| employee_id | BIGINT | Unique employee ID |
| attendance_date | Date | Attendance date |
| status | VARCHAR | Status |
| check_in | VARCHAR | check in |
| check_out | VARCHAR | check out |


### Primary Key
- id

### Foreign Keys
- employee_id → Employee.employee_id

---

## 5. Leave_Request

### Purpose
Stores leave requests.

### Columns
| Column | Data Type | Description |
|---|---|---|
| id | BIGINT | ID |
| employee_id | BIGINT | Unique employee ID |
| start_date | Date | Start date |
| end_date | Date | End date |
| reason | VARCHAR | Reason |
| status | VARCHAR | Status |
| approved_by | VARCHAR | Approved by |

### Primary Key
- id

### Foreign Keys
- employee_id → Employee.employee_id

---

## 6. Salary

### Purpose
Stores salary details.

### Columns
| Column | Data Type | Description |
|---|---|---|
| id | BIGINT | ID |
| employee_id | BIGINT | Unique employee ID |
| basic_salary | BIGINT | Basic salary |
| bonus | BIGINT | Bonus |
| deduction | BIGINT | Deduction  |
| payment_date | Date | Payment date |

### Primary Key
- id

### Foreign Keys
- employee_id → Employee.employee_id

---

# ER Diagram

                   USER
                     |
                     | 1 : 1
                     |
                 EMPLOYEE
                     |
          -----------------------
          |         |          |
        N:1       1:N        1:N
          |         |          |
    DEPARTMENT  ATTENDANCE  LEAVE_REQUEST
                     |
                     |
                   SALARY