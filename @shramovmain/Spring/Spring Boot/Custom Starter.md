1. **Создание нового Gradle-модуля**
	Установка artifactId (имени модуля, строку, которая описывает содержимое артефакта) и groupId (последовательность пакетов до местонахождения модуля)
	Например artifactId: common-logger-starter

2. **Настройка модуля**
	Настройка build.gradle модуля (например, редактирование зависимостей)

3. **Создание и настройка класса c Propties (обычный класс .java)**
	POJO-класс (@Data, @NoArgsConstructor)
	@ConfigurationProperties(prefix = "префикс для Properties")
	Префикс служит именем для настройки полей этого класса через application.properties основного проекта![[Pasted image 20240504182540.png]]

4. **Создание директории с классами, которые в качестве бинов будет предоставлять стартер.**
	Создание директории и добавление в неё классов 

5. **Создание класса Авто-конфигурации**
	@Configuration
	@EnableConfigurationProperties(Указывается класс пропертей стартера .class)
	@Conditional(С указанием условий, для создания бинов)![[Pasted image 20240504183247.png]]
	Создание @Bean методов, которые будут возвращать бины

6. **Создание файла spring.factories**
	В пути **resources/META-INF/spring.factories**![[Pasted image 20240504183008.png]]

7. **Добавить зависимость в application.properties основного проекта**
	Например: implementation project(':common-logger-starter')