**Типы операций:**
	- Промежуточные
	- Терминальные

### **Промежуточные:**

**==filter==(Predicate predicate)**
	Отфильтровывает элементы, соответствующие предикату.

**==map==(Function mapper)**
	Маппит элементы с помощью заданной функции.

**==sorted==()**
**==sotred==(Comparator comparator)**
	Сортирует stream

**==flatMap==()**
	Убирает вложенность
	(например, если в List вложены ещё два List-a, он уберёт эти обёртки и вернёт единый лист из значений двух List-ов)

**==peek==(Consumer)**
	Промежуточный forEach

**==distinct==()**
	Возвращает стрим без дубликатов.

**==limit==(Long maxSize)**
	Ограничивает выборку, принимая максимальный размер.

**==skip==(Long minSize)**
	Ограничивает выборку, принимая минимальный размер.

### Терминальные:

**==collect==(Collector collector)**
	Преобразовывает stream в коллекцию или другую структуру данных.

**==forEach==(Consumer action)**
	Выполняет действие для каждого элемента.

**==count==()**
	Возвращает кол-во элементов в stream.

**==min==(Comparator comparator)**
**==max==(Comparator comparator)**
	Возвращает минимальный или максимальный элемент в stream.

**==findFirst==()**
	Возвращает первый элемент stream.

**==allMatch==(Predicate predicate)**
**==anyMatch==(Predicate predicate)**
**==noneMatch==(Predicate predicate)**
	Проверяет, соответствуют ли 
	- все элементы
	- хотя бы один элемент
	- ни один элемент
	предикату.

**==collect==(Predicate pridicate)**
	...

**==reduce==(BinaryOperator accumulator)**
	Выполняет вычисление по переданной агрегатной функции и возвращает ОДИН результат

