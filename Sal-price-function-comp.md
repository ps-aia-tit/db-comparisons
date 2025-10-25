## 🧠 SQL Procedures & Functions — Syntax & Behavior Comparison

| Feature               | Db2 Example                                                                 | SQL Server Example                                                              | Oracle Example                                                                   |
|-----------------------|------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| **Procedure Definition** | ```sql<br>CREATE PROCEDURE raise_salary(IN emp_id INT, IN amount INT)<br>BEGIN<br>  UPDATE employees SET salary = salary + amount WHERE id = emp_id;<br>END<br>``` | ```sql<br>CREATE PROCEDURE raise_salary @emp_id INT, @amount INT<br>AS<br>BEGIN<br>  UPDATE employees SET salary = salary + @amount WHERE id = @emp_id;<br>END<br>``` | ```sql<br>CREATE OR REPLACE PROCEDURE raise_salary(emp_id IN NUMBER, amount IN NUMBER) AS<br>BEGIN<br>  UPDATE employees SET salary = salary + amount WHERE id = emp_id;<br>END;<br>``` |
| **Function Definition** | ```sql<br>CREATE FUNCTION get_bonus(salary INT) RETURNS INT<br>RETURN salary * 0.10;<br>``` | ```sql<br>CREATE FUNCTION get_bonus(@salary INT)<br>RETURNS INT<br>AS<br>BEGIN<br>  RETURN @salary * 0.10;<br>END<br>``` | ```sql<br>CREATE OR REPLACE FUNCTION get_bonus(salary NUMBER)<br>RETURN NUMBER IS<br>BEGIN<br>  RETURN salary * 0.10;<br>END;<br>``` |
| **Calling Procedure**   | `CALL raise_salary(101, 5000);`                                            | `EXEC raise_salary 101, 5000;`                                                  | `BEGIN raise_salary(101, 5000); END;`                                           |
| **Calling Function**    | `SELECT get_bonus(salary) FROM employees;`                                 | `SELECT dbo.get_bonus(salary) FROM employees;`                                  | `SELECT get_bonus(salary) FROM employees;`                                      |
| **Exception Handling**  | `DECLARE EXIT HANDLER FOR SQLEXCEPTION ...`                                | `BEGIN TRY ... END TRY BEGIN CATCH ... END CATCH`                               | `EXCEPTION WHEN OTHERS THEN ...`                                                |
| **Return Type Support** | Scalar only (no table-valued functions)                                    | Supports scalar and table-valued functions                                      | Supports scalar and pipelined table functions                                   |
| **Transaction Support** | Limited inside procedures                                                  | Full transaction control inside procedures                                      | Full transaction control inside procedures                                      |

---

### 📝 Notes

- **Db2** uses `SQL PL` with `CALL` for procedures and `RETURN` for scalar functions.
- **SQL Server** uses `T-SQL` with `EXEC` for procedures and supports both scalar and table-valued functions.
- **Oracle** uses `PL/SQL` with `BEGIN ... END;` blocks and supports pipelined table functions.
- Exception handling syntax varies significantly and must be modularized during migration.
