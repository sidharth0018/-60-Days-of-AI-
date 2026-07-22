# SQL Notes

## GROUP BY

Groups similar records together.

---

## HAVING

Filters aggregated results.

Example

SELECT department,
AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;

---

## WHERE vs HAVING

WHERE

Filters rows.

HAVING

Filters groups.

---

## Self Join

Used when a table references itself.

Example

Employee

↓

Manager

Both stored inside the same table.

Example Query

SELECT
e.employee_name,
m.employee_name
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.employee_id;

---

## LEFT JOIN

Returns all employees

Even CEO without manager.
