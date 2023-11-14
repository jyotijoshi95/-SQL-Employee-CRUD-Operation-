## Employee Information System

This Project Do CRUD Operation in employees table.

### Table of Contents
- [Create Employee Table](#create-employee-table)
- [Insert Data into Employee Table](#insert-data-into-employee-table)
- [Select All Employee Data](#select-all-employee-data)
- [Update Gender and Salary](#update-gender-and-salary)
- [Querying Employee Information](#querying-employee-information)

### Create Employee Table
```sql
/* create employee table */
Create table Employee(
    Id int identity(1,1) primary key,
    EmpName varchar(50),
    Gender char(1),
    Department varchar(50),
    EmailId varchar(50),
    Phoneno int,
    Position varchar(50),
    Salary float
)
```

### Insert Data into Employee Table
```sql
/* insert data into employee table */
insert into Employee (EmpName, gender, department, emailid, phoneno, position, salary) values 
    ('Jyoti','F','IT', 'Jyoti@gmail.com',123456789, 'Developer', 60000.00 ),
    ('Hema','F','HR', 'Hema@gmail.com',987654321, 'HR Specialist', 70000.00 ),
    -- Add more data here...
```

### Select All Employee Data
```sql
/* select all employee data */
Select * From Employee
```

### Update Gender and Salary
```sql
/* set Gender value to "F" for employees in the IT department */
update Employee set gender = 'F' where Department = 'IT'

/* increase salary by 10% for employees in the HR department */
update Employee set Salary = Salary * 1.10 where Department = 'HR'
```

### Querying Employee Information
```sql
/* get employees who are in the IT department and have a salary greater than 50000 */
select * from Employee where Department = 'IT' and Salary > 50000

/* get employees in the HR department with a position of HR Specialist */
Select * from Employee where department = 'HR' and Position = 'HR Specialist'

/* get the top 5 highest-paid employees */
Select Top 5 * from Employee order by Salary desc

/* get employees who have a salary between 60000 and 80000 */
Select * from Employee where Salary between 60000 and 80000

/* get employees with a gender of "M" and a position of "Developer" */
Select * from Employee where Gender = 'M' and Position = 'Developer'

/* get the average salary for employees in each department */
Select Department, AVG(Salary) as AverageSalary from Employee group by Department
```

### Delete Query
```sql
/* delete employee with ID 1 */
DELETE FROM Employee WHERE Id = 1
```

### Delete Table
```sql
/* delete employee table */
DROP TABLE Employee
```

### Fetch Employee First Name in Upper Case with Alias
```sql
/* fetch EmpFname in upper case with alias EmpName */
SELECT UPPER(EmpFname) AS EmpName FROM EmployeeInfo
```

### Number of Employees in HR Department
```sql
/* fetch the number of employees working in the department 'HR' */
SELECT COUNT(*) AS NumberOfEmployees FROM EmployeeInfo WHERE Department = 'HR'
```

### Get Current Date
```sql
/* get the current date */
SELECT GETDATE() AS CurrentDate
```

### Retrieve First Four Characters of EmpLname
```sql
/* retrieve the first four characters of EmpLname */
SELECT LEFT(EmpLname, 4) AS FirstFourCharacters FROM EmployeeInfo
```

### Fetch Place Name from Address Column
```sql
/* fetch only the place name (string before brackets) from the Address column */
SELECT SUBSTRING(Address, 1, CHARINDEX('(', Address) - 1) AS PlaceName FROM EmployeeInfo
```

### Create New Table from Existing Table
```sql
/* create a new table with the same structure and data from EmployeeInfo */
SELECT * INTO NewEmployeeTable FROM EmployeeInfo
```

### Employees with Salary Between 50000 to 100000
```sql
/* find all employees whose salary is between 50000 to 100000 */
SELECT * FROM EmployeeInfo WHERE Salary BETWEEN 50000 AND 100000
```

### Employees with Names Starting with 'S'
```sql
/* find the names of employees that begin with 'S' */
SELECT * FROM EmployeeInfo WHERE EmpFname LIKE 'S%'
```

### Fetch Top N Records
```sql
/* fetch top 5 records from EmployeeInfo */
SELECT TOP 5 * FROM EmployeeInfo
```

### Fetch Full Name (EmpFname and EmpLname combined with a space)
```sql
/* fetch EmpFname and EmpLname in a single column as "FullName" */
SELECT EmpFname + ' ' + EmpLname AS FullName FROM EmployeeInfo
```
