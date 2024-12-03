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


## **2. Outer Joins**  
Outer Joins return rows even when there is no match. They come in three types:  

- **a) Left Outer Join (or Left Join)**  
  Returns all rows from the left table and matched rows from the right table. If no match is found, `NULL`s are returned for unmatched columns.

---

### **Syntax:**
```sql
SELECT column1, column2, ...
FROM table1
LEFT JOIN table2
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

### Result of Left outer Join:

| EmployeeName | DepartmentName |
|--------------|----------------|
| Alice        | HR             |
| Bob          | IT             |
| Charlie      | NULL           |

- **b) Right Outer Join (or Right Join)**  
  Returns all rows from the right table and matched rows from the left table. If no match is found, `NULL`s are returned for unmatched columns.

---

### **Syntax:**
```sql
SELECT column1, column2, ...
FROM table1
RIGHT JOIN table2
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
| 103          | Marketing      |

### Result of Right outer Join:

| EmployeeName | DepartmentName |
|--------------|----------------|
| Alice        | HR             |
| Bob          | IT             |
| NULL         | Marketing      |


- **c) Full Outer Join**  
  Returns all rows when there is a match in either the left or right table. If there is no match, `NULL`s are returned for the unmatched columns.

---

### **Syntax:**
```sql
SELECT column1, column2, ...
FROM table1
FULL OUTER JOIN table2
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
| 103          | Marketing      |

### Result of Full outer Join:

| EmployeeName | DepartmentName |
|--------------|----------------|
| Alice        | HR             |
| Bob          | IT             |
| Charlie      | NULL           |
| NULL         | Marketing      |

