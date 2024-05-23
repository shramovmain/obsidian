## *StringBuffer*

- Позволяет изменять содержимое строки, а не создавать каждый раз новый объект.
- Предоставляет изменяемую последовательность символов.

**Методы:**

stringBuffer .**==append==** ("any string")
stringBuffer .**==delete==** (int start, int end)
stringBuffer .**==insert==** (int offsetm, "any string")

## *StringBuilder*

- Методы идентичный StringBuffer.
- Не синхронизирован (не потокобезопасен) в отличии от StringBuffer.