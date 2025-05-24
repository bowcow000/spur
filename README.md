# spur

**1) SELECT (выборка данных)**

SELECT column1, column2, ...
FROM table_name
WHERE condition;

Пример:
```
SELECT name, age FROM users WHERE age > 18;
```

Выбор всех столбцов:
```
SELECT * FROM users;
```
Сортировка (ORDER BY):
```
SELECT * FROM users ORDER BY age DESC;
```

Группировка (GROUP BY):
```
SELECT department, COUNT(*) FROM employees GROUP BY department;
```

HAVING (фильтрация групп):
```
SELECT department, COUNT(*) 
FROM employees 
GROUP BY department
HAVING COUNT(*) > 5;
```

EXISTS (проверка существования записей):
```
SELECT column1, column2, ...
FROM table1
WHERE EXISTS (SELECT 1 FROM table2 WHERE table2.column = table1.column);
```

Пример EXISTS:
```
SELECT name FROM employees e
WHERE EXISTS (SELECT 1 FROM orders o WHERE o.employee_id = e.id);
```

**2) UPDATE (обновление данных)**

```
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

Пример:
```
UPDATE users SET age = 30 WHERE name = 'John';
```

Обновление всех строк (осторожно!):
```
UPDATE users SET status = 'inactive';
```

Обновление с подзапросом:
```
UPDATE products 
SET price = price * 1.1
WHERE category_id IN (SELECT id FROM categories WHERE name = 'Electronics');
```

**3) INSERT (вставка данных)**

```
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

Пример:
```
INSERT INTO users (name, age) VALUES ('Alice', 25);
```

Вставка нескольких строк:
```
INSERT INTO users (name, age) VALUES ('Bob', 30), ('Charlie', 22);
```

Вставка из другой таблицы:
```
INSERT INTO active_users (name, age)
SELECT name, age FROM users WHERE status = 'active';
```

**4) DELETE (удаление данных)**

```
DELETE FROM table_name
WHERE condition;
```

Пример:
```
DELETE FROM users WHERE age < 18;
```

Удаление всех строк (осторожно!):
```
DELETE FROM users;
```

Удаление с подзапросом:
```
DELETE FROM orders
WHERE customer_id IN (SELECT id FROM customers WHERE status = 'inactive');
```

**5) TRUNCATE (очистка таблицы)**

```
TRUNCATE TABLE table_name;
```

Пример:
```
TRUNCATE TABLE users;
```

Отличия от DELETE:

```
    TRUNCATE быстрее

    Не записывает в журнал отдельные удаления строк

    Сбрасывает автоинкремент

    Нельзя использовать с WHERE
```

**6) JOIN (соединение таблиц)**

INNER JOIN:
```
SELECT a.column1, b.column2
FROM table1 a
INNER JOIN table2 b ON a.key = b.key;
```

LEFT JOIN:
```
SELECT a.column1, b.column2
FROM table1 a
LEFT JOIN table2 b ON a.key = b.key;
```

RIGHT JOIN:
```
SELECT a.column1, b.column2
FROM table1 a
RIGHT JOIN table2 b ON a.key = b.key;
```

FULL JOIN:
```
SELECT a.column1, b.column2
FROM table1 a
FULL JOIN table2 b ON a.key = b.key;
```

**7) Полезные функции**

Агрегатные функции:
```
SELECT COUNT(*), AVG(age), MAX(age), MIN(age), SUM(salary) FROM employees;
```

Работа с датами:
```
SELECT CURRENT_DATE, EXTRACT(YEAR FROM birth_date) FROM users;
```

Условные выражения:
```
SELECT name, 
       CASE WHEN age < 18 THEN 'Junior'
            WHEN age BETWEEN 18 AND 65 THEN 'Adult'
            ELSE 'Senior' END AS age_group
FROM users;
```
