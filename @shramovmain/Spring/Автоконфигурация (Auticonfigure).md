В зависимости spring-boot-autoconfigure
	- Папки с классами с Conditional
	- spring.factories со ссылками на эти классы

![[Pasted image 20240603153507.png]]
...

![[Pasted image 20240603153714.png]]
...

Доступ к нему осуществляется через аннотацию @SpringBootApplication
![[Pasted image 20240603153900.png]]

У @SpringBootApplication есть @EnableAutoConfiguration
![[Pasted image 20240603154008.png]]

У @EnableAutoConfiguration есть @Import({AutoConfigurationImportSelector.class})
![[Pasted image 20240603154101.png]]

У AutoConfigurationImportSelector есть метод 
getAutoConfigurationImportFilters, который подтягивает зависимости из КОНСТАНТЫ FACTORIES_RESOURCE_LOCATION
![[Pasted image 20240603154158.png]]![[Pasted image 20240603155035.png]]

![[Pasted image 20240603155114.png]]
