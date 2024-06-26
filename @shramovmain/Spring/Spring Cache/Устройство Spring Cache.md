**Кэширование**  - процесс сохранения результатов дорогостоящих операций для последующего использования из оперативной памяти.
Управляется **CacheMenager**
По умолчанию кэш сохраняется в ConcurrentHashMap

**@EnableCaching**
Запускает постпроцессор, который проверяет каждый Bean на наличие кэшируемых аннотаций в общедоступных методах.
***~** Вешается над классом конфигурации.*

**@CacheConfig** 
Определяет в параметрах общие настройки кэширования на уровне класса.
***~** Вешается над классом с аннотируемыми методами.*

**@Cacheable**
Указывает метод, результат которого должен быть сохранён в кэш. 
***~** Вешается над методом.*

Основные параметры:
- **value** - имя кэша, в котором будет храниться результат.
- **key** - ключ, под которым будет хранится результат.
- **condition** - условие, при котором результат метода будет сохранён в кэш.

**@CachePut**
Обновляет значение в кэше с результатом метода.
Основные параметры идентичны @Cacheable
***~** Вешается над методом*

**@CacheEvict**
Удаляет одно или несколько значений из кэша.
***~** Вешается над методом*

Основные параметры: 
- **allEntries** - удаляет все значения из указанного кэша (если true)
- **beforeInvocation** - удаляет значение из кэша до вызова метода (если true)