## 🔗 SQL JOIN Syntax Comparison — Db2 vs SQL Server vs Oracle

### 🧩 Purpose

This section highlights differences in JOIN syntax across IBM Db2, Microsoft SQL Server, and Oracle, supporting integration clarity and recruiter-facing documentation.

---

### ✅ Basic INNER JOIN

```sql
-- Db2
SELECT e.name, d.name
FROM employees e
JOIN departments d ON e.dept_id = d.id;

-- SQL Server
SELECT e.name, d.name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.id;

-- Oracle
SELECT e.name, d.name
FROM employees e
JOIN departments d ON e.dept_id = d.id;
```

---

### 🔄 LEFT OUTER JOIN

```sql
-- Db2
SELECT e.name, d.name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.id;

-- SQL Server
SELECT e.name, d.name
FROM employees e
LEFT OUTER JOIN departments d ON e.dept_id = d.id;

-- Oracle
SELECT e.name, d.name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.id;
```

---

### 🔁 RIGHT OUTER JOIN

```sql
-- Db2
SELECT e.name, d.name
FROM employees e
RIGHT JOIN departments d ON e.dept_id = d.id;

-- SQL Server
SELECT e.name, d.name
FROM employees e
RIGHT OUTER JOIN departments d ON e.dept_id = d.id;

-- Oracle
SELECT e.name, d.name
FROM employees e
RIGHT JOIN departments d ON e.dept_id = d.id;
```

---

### 🔀 FULL OUTER JOIN

```sql
-- Db2
SELECT e.name, d.name
FROM employees e
FULL JOIN departments d ON e.dept_id = d.id;

-- SQL Server
SELECT e.name, d.name
FROM employees e
FULL OUTER JOIN departments d ON e.dept_id = d.id;

-- Oracle
SELECT e.name, d.name
FROM employees e
FULL OUTER JOIN departments d ON e.dept_id = d.id;
```

---

### 🧮 CROSS JOIN

```sql
-- Db2
SELECT e.name, d.name
FROM employees e
CROSS JOIN departments d;

-- SQL Server
SELECT e.name, d.name
FROM employees e
CROSS JOIN departments d;

-- Oracle
SELECT e.name, d.name
FROM employees e
CROSS JOIN departments d;
```

---

### 📝 Notes

- SQL Server prefers explicit `INNER`, `LEFT OUTER`, `RIGHT OUTER`, and `FULL OUTER` keywords.
- Db2 and Oracle allow simplified `JOIN`, `LEFT JOIN`, etc., but support full syntax as well.
- CROSS JOIN produces Cartesian product — use cautiously in integration flows.
