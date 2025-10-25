## 🔗 SQL JOIN Types — Definitions & Syntax Comparison

| Join Type         | Definition                                                                 | Db2 Syntax Example                                                                 | SQL Server Syntax Example                                                           | Oracle Syntax Example                                                               |
|-------------------|-----------------------------------------------------------------------------|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| **INNER JOIN**    | Returns rows with matching values in both tables                           | `SELECT ... FROM A JOIN B ON A.id = B.id`                                           | `SELECT ... FROM A INNER JOIN B ON A.id = B.id`                                     | `SELECT ... FROM A JOIN B ON A.id = B.id`                                           |
| **LEFT JOIN**     | Returns all rows from left table, matched rows from right (NULL if no match)| `SELECT ... FROM A LEFT JOIN B ON A.id = B.id`                                      | `SELECT ... FROM A LEFT OUTER JOIN B ON A.id = B.id`                                | `SELECT ... FROM A LEFT JOIN B ON A.id = B.id`                                      |
| **RIGHT JOIN**    | Returns all rows from right table, matched rows from left (NULL if no match)| `SELECT ... FROM A RIGHT JOIN B ON A.id = B.id`                                     | `SELECT ... FROM A RIGHT OUTER JOIN B ON A.id = B.id`                               | `SELECT ... FROM A RIGHT JOIN B ON A.id = B.id`                                     |
| **FULL JOIN**     | Returns all rows when there is a match in one of the tables                | `SELECT ... FROM A FULL JOIN B ON A.id = B.id`                                      | `SELECT ... FROM A FULL OUTER JOIN B ON A.id = B.id`                                | `SELECT ... FROM A FULL OUTER JOIN B ON A.id = B.id`                                |
| **CROSS JOIN**    | Returns Cartesian product of both tables                                   | `SELECT ... FROM A CROSS JOIN B`                                                    | `SELECT ... FROM A CROSS JOIN B`                                                    | `SELECT ... FROM A CROSS JOIN B`                                                    |
| **SELF JOIN**     | Joins a table to itself                                                    | `SELECT ... FROM A x JOIN A y ON x.id = y.manager_id`                               | `SELECT ... FROM A x INNER JOIN A y ON x.id = y.manager_id`                         | `SELECT ... FROM A x JOIN A y ON x.id = y.manager_id`                               |

---

### 📝 Notes

- **INNER JOIN** is the default and most commonly used join.
- **LEFT/RIGHT JOIN** are useful for preserving unmatched rows from one side.
- **FULL JOIN** is ideal for merging datasets with partial overlap.
- **CROSS JOIN** should be used cautiously due to exponential row growth.
- **SELF JOIN** is useful for hierarchical or recursive relationships (e.g., employee-manager).

