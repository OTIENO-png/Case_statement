#SELECT Clause:
This clause specifies the columns to be retrieved from the joined tables.
s.Employee_id_No, s.Department_name, s.Designation: These columns are from the Staffs_Data table, which might contain information about the department and job details of employees.
e.Full_Name, e.Email, e.Birth_year, e.Phone_Number: These columns are from the Employee_Personal_Info table, which contains personal details of the employees.
#CASE Statement:
The CASE statement is used to evaluate a set of conditions and return different results based on those conditions.
WHEN s.Employee_id_No IS NULL THEN 'Not onboarded': If the Employee_id_No in the Staffs_Data table is NULL, it implies that the employee is not associated with any department or role, hence marked as 'Not onboarded'.
WHEN s.Designation IS NULL THEN 'Not onboarded': If the Designation is NULL, it suggests that the employee's role is not defined, also marking them as 'Not onboarded'.
ELSE 'Fully onboarded': If none of the above conditions are met (i.e., both Employee_id_No and Designation are not NULL), the employee is considered 'Fully onboarded'.
#FROM Clause:
FROM Staffs_Data s: This specifies the Staffs_Data table as the primary table for the join operation, with an alias s for easier reference.
#RIGHT JOIN Clause:
RIGHT JOIN Employee_Personal_Info e ON s.Employee_id_No = e.Employee_id_No: This performs a RIGHT JOIN, which returns all rows from the right table (Employee_Personal_Info) and the matched rows from the left table (Staffs_Data). If there is no match, the result is NULL on the side of the left table.
The join condition is that the Employee_id_No in both tables must match.
#ORDER BY Clause:
ORDER BY s.Employee_id_No DESC: This orders the result set by the Employee_id_No column in descending order, so the highest employee IDs appear first.
