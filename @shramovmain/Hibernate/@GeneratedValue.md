Позволяет Hibernate присваивать id новым объектам автоматически.

`@Target({ElementType.METHOD, ElementType.FIELD})`  
`@Retention(RetentionPolicy.RUNTIME)`  
`public @interface GeneratedValue {`  
    `GenerationType strategy() default GenerationType.AUTO;`  
  
    `String generator() default "";`  
`}`

**Параметры:**
	**strategy**
		**AUTO**
			(по умолчанию)
			Hibernate самостоятельно выбирает наиболее подходящую стратегию для конкретной БД.
		**IDENTITY**
			Автоинкремент (начиная с 1).
		**SEQUENCE**
			Позволяет настроить шаг.
			Представляет из себя однострочную таблицу.
		**TABLE**
			Создается отдельная таблица со значением Id сущности, которая попадёт в таблицу следующей.
			Представляет из себя однострочную таблицу.
	**generator**
		Указывает имя генератора последовательности, которые будет использоваться.