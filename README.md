Exercise Description:
Suppose we have two tables: Employees and Departments. The Employees table contains information about company employees, and the Departments table contains details about different departments within the company. You are tasked with creating these tables and establishing a relationship between them using primary and foreign keys.

1. Create the Departments table- colums -> department id,department name(should not be null),location
   
```SQL
CREATE TABLE department (department_id INT PRIMARY KEY AUTO_INCREMENT, department_name VARCHAR(50) NOT NULL, location VARCHAR(100) );
```

2.  Create the Employees table: colum: employee id , employee name(should not be null) and one foreign key that is department id from department table

```SQL
CREATE TABLE employees ( employee_id INT PRIMARY KEY AUTO_INCREMENT, employee_name VARCHAR(50) NOT NULL, department_id INT, FOREIGN KEY(department_id) REFERENCES department(department_id));
```

3. Populate the Departments table with some sample data:
   
```SQL
INSERT INTO department (department_name, location) VALUES
    ("IT", "San Francisco"),
    ("HR", "Los Angeles"),
    ("MARKETING", "New York");
```

4. Populate the Employees table with sample data:
   
```SQL
INSERT INTO employees (employee_name, department_id) VALUES
    ("John Doe", 2),
    ("Jane Smith", 3);
``` 
   Exercise Tasks:
1.Add a new department called 'IT' in the Departments table and assign an employee (e.g., EmployeeID 106, 'David Wilson') to this department in the Employees table.
```SQL
INSERT INTO employees (employee_id, employee_name, department_id) VALUES
    (106, "David Wilson", 1);
``` 

2.Update the location of the 'HR' department from 'New York' to 'Chicago'.

```SQL
UPDATE department SET location = "Chicago" WHERE department_name = "HR";
```

3.Delete the employee named 'Michael Brown' from the Employees table.
```SQL
DELETE FROM employees WHERE employee_name = "Michael Brown" AND employee_id = 107;
```

Expected Results:
Task 1 should successfully add the 'IT' department and assign an employee to it.
Task 2 should update the location of the 'HR' department.
Task 3 should remove the employee 'Michael Brown' from the table.
You can practice these tasks and SQL statements against the created tables to understand how primary keys (PKs) and foreign keys (FKs) work together to establish relationships between tables in a database.
