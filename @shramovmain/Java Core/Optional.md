Класс обёртка для обеспечения удобства обработки возможных null значений.

Способы создания:
1) Пустой объект **.empty()**
2) С присвоением значения **.of("text")** | НЕЛЬЗЯ null
3) С присвоением значения **.ofNallable("text")** | Если будет null - получим пустой объект

Методы:
- **isPresent()** - возвращает true, если не null
- **isEmpty()** - обратный isPresent()
- **ifPresent(code)** - выполняется код, если не null
- **orElse(value)** - возвращает переданный value, если null
- **orElseThrow(Exception)** - выбрасывает исключение, если null (NoSushElementException по умолчанию)
- **filter(condition)** - возвращает значение, если condition = true, иначе пустой Optional
- **get()** - возвращает значение, если оно есть, иначе выбрасывает исключение NoSushElementException