# SQL-Joins
Joins with examples
##  What is a Join? 
A join is a SQL operation used to combine rows from two or more tables based on a related column between them. Joins help retrieve data spread across multiple tables by merging them into a single result set.

##  Types of Joins 
There are several types of joins, each serving a specific purpose:

- **Inner Join**  
- **Outer Join**  
  - Left Outer Join  
  - Right Outer Join  
  - Full Outer Join  
- **Cross Join**  
- **Self Join**  
- **Natural Join**  
- **Equi Join**  
- **Non-Equi Join**

## **1. Inner Join**  
The **Inner Join** returns rows when there is a match in both tables based on the specified condition.

### **Syntax:**
```sql
SELECT column1, column2, ...
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
```

### Employees Table:

| EmployeeID | EmployeeName | DepartmentID |
|------------|--------------|--------------|
| 1          | Alice        | 101          |
| 2          | Bob          | 102          |
| 3          | Charlie      | NULL         |

### Departments Table:

| DepartmentID | DepartmentName |
|--------------|----------------|
| 101          | HR             |
| 102          | IT             |
### Result of Inner Join:

| EmployeeName | DepartmentName |
|--------------|----------------|
| Alice        | HR             |
| Bob          | IT             |
Note: Charlie is excluded because there is no matching DepartmentID.


