**LOADING:**

**Bootstrap ClassLoader**
Загружает системные классы из стандартных библиотек Java
java.base/
(java.lang, java util, java.io, java.net и др.)

**Extension ClassLoader**
Загружает классы из расширений Java (JRE Extension)

**Application ClassLoader**
Загружает пользовательские классы из CLASSPATH

Да, конечно. Принцип делегирования загрузчиков классов в Java можно представить как систему “передачи эстафеты” вверх по иерархии загрузчиков классов. Вот как это работает:

1. **Запрос на загрузку класса**:
	Приложение пытается использовать класс, который еще не был загружен в память, оно отправляет запрос на загрузку этого класса.
    
2. **Делегирование вверх по иерархии**:
	Загрузчик классов, получивший этот запрос, не пытается сразу же загрузить класс самостоятельно. Вместо этого он передает запрос своему родительскому загрузчику классов.
    
3. **Попытка загрузки родительским загрузчиком**:
	Родительский загрузчик пытается загрузить класс.
	Если он может загрузить класс, он это делает, и процесс завершается.
	Если он не может загрузить класс, он передает запрос своему собственному родительскому загрузчику.
    
4. **Продолжение делегирования**:
	Этот процесс продолжается вверх по иерархии загрузчиков классов, пока запрос не достигнет загрузчика Bootstrap.
    
5. **Попытка загрузки Bootstrap загрузчиком**:
	Bootstrap пытается загрузить класс.
	Если он может загрузить класс, он это делает, и процесс завершается.
    
6. **Возвращение вниз по иерархии**:
	Если загрузчик Bootstrap не может загрузить класс, запрос возвращается обратно вниз по иерархии.
	Каждый загрузчик классов теперь пытается загрузить класс самостоятельно.
    
7. **Генерация исключения**:
	Если ни один из загрузчиков классов не может загрузить класс, генерируется исключение ClassNotFoundException.
    

Процесс делегирования помогает обеспечить безопасность и изоляцию пространства имен в Java, предотвращая загрузку ненадежных или вредоносных классов из ненадежных источников.

**LINKING**:

**Verify:**
Проверка байт-кода класса на соответствие правилам и структуре Java
~ Например: корректность типов, правильность наследования, использование методов и др.
Если байт-код не проходит проверку, генерируется VrifyError

**Prepare**
Выделение памяти для статических переменных класса и присвоение значений по умолчанию.

**Resolve**
Преобразование символических ссылок из байт-кода в прямые ссылки.
Это включает поиск классов, методов и полей, на которые ссылается класс, и их загрузку при необходимости.

**INITIALIZATION**

Выполнение статических инициализаторов класса и инициализируются статические переменные. Это происходит при первом обращении к классу. Если во время инициализации происходит исключение, JVM обрабатывает его и может отметить класс как неполностью инициализированный, если не удалось обработать исключение. 
В дальнейшем обращение к такому классу может вызвать исключение ExceptionInInitializerError.