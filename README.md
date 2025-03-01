# spur

1) SELECT (выборка данных)
```
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

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

2) UPDATE (обновление данных)
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

3) INSERT (вставка данных)
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

4) DELETE (удаление данных)
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

5) TRUNCATE (очистка таблицы)
```
TRUNCATE TABLE table_name;
```

Пример:
```
TRUNCATE TABLE users;
```






