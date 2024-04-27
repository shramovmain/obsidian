
**Executor**
	Простой интерфейс, который предоставляет метод `execute(Runnable)`, позволяющий выполнить задачу в асинхронном режиме

**ExecutorService**
	Расширяет интерфейс Executor, добавляя методы для управления жизненным циклом потоков и методы, которые могут создать `Future` для отслеживания прогресса одной или нескольких задач.

**Методы ExecutorService:**

**newSingleThreadExecutor()**
	Создает пул, который состоит из единственного рабочего потока. Все задачи выполняются последовательно в порядке их поступления.

**newFixedThreadPool(int nThreads)**
	Создает пул потоков с фиксированным числом потоков.
	Если все потоки заняты, новые задачи будут ожидать в очереди.

**newCachedThreadPool()**
	Создает пул потоков, который создает новые потоки по мере необходимости, но повторно использует ранее созданные потоки, когда они становятся доступными.

**newScheduledThreadPool(int corePoolSize)**
	Создает пул потоков, который может планировать команды для выполнения после заданного периода времени или для периодического выполнения.