**AXPLAIN ANALYZE**

Операторы:

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

### ORDER BY
	ASC - сортировка по возрастанию (по умолчанию)
	DESC - сортировка по убыванию
```
SELECT DISTINCT town_from, town_to FROM Trip
ORDER BY town_from, town_to DESC;
```

### HAVING
Выполняет агрегатные функции после группировки (фильтрация результатов группировки)

