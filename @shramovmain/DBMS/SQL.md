- SQL-запросы - https://proglib.io/p/sql-cheat-sheet
---

**AXPLAIN ANALYZE**

Операторы:

### ROUND
	Принимает два параметра:
		- Десятичную дробь
		- Разряд, до которого нужно округлить
### CEILING
	Округляет в большую сторону
### FLOOR
	Округляет в меньшую сторону


### BETWEEN min AND max
```
SELECT * FROM Payments
WHERE unit_price BETWEEN 100 AND 500;
```

### IN
```
SELECT * FROM FamilyMembers
WHERE status IN ('father', 'mother');
```

### ORDER BY ...
	ASC - сортировка по возрастанию (по умолчанию)
	DESC - сортировка по убыванию
```
SELECT DISTINCT town_from, town_to FROM Trip
ORDER BY town_from, town_to DESC;
```

### HAVING
	Выполняет агрегатные функции после группировки (фильтрация результатов группировки)

### WHERE EXTRACT(YEAR FROM News.published_at) = 2024
	Условие "Где год в published_at == 2024"


# Запросы

```sql
CREATE TABLE Users (
    user_id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

```sql
UPDATE employees
SET salary = 0 
WHERE name = "Ivan Ivanov";
```

```sql
DELETE
FROM employees
WHERE name = "Ivan Ivanov";
```

```sql
INSERT INTO portions (dog_name, weight, portion) VALUES ("Max", 15, 180), ("Charlie", 37, 350);
```

