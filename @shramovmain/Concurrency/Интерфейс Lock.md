Интерфейс, предоставляющий альтернативный способ синхронизации потоков (отличный от Synchronized)

- Работает быстрее Synchronized, т.к. использует объект Unsafe и позволяет добавлять condition для выхода из потока блокировка.

- В случае Lock, обязанность блокирования монитора выносится в отдельный класс, который лежит в объекте, как поле.
	Блокироваться будет объект Lock, а не не сам объект.
	Нужно не забывать вызывать unlock в finaly блоке, чтобы точно снять блокировку.

**Condition**
	Условия, предоставляющие одному потоку возможность приостанавливать выполнение потока (ждать), пока другой поток не уведомит о том, что какое-то условие состояния стало выполнилось (стало истинным).

**StampedLock** и **ReentrantReadWriteLock** - это два механизма блокировки в Java, которые используются для управления доступом к общим ресурсам в многопоточной среде.

**ReentrantReadWriteLock**
	Реализация интерфейса ReadWriteLock, который также поддерживает функциональность ReentrantLock. Основные особенности ReentrantReadWriteLock:

- **Чтение и запись**: ReentrantReadWriteLock поддерживает пару связанных блокировок, одну для операций только для чтения и одну для записи.
- **Реентерабельность**: Этот механизм блокировки позволяет как читателям, так и писателям повторно приобретать блокировки на чтение или запись.
- **Понижающее преобразование блокировки**: ReentrantReadWriteLock также позволяет понижать блокировку с записи на чтение.

**StampedLock** был введен в Java 8 и представляет собой механизм блокировки, который поддерживает три режима для контроля доступа на чтение/запись. Основные особенности StampedLock:

- **Оптимистичное чтение**: Метод `tryOptimisticRead()` возвращает ненулевую метку только в том случае, если блокировка в данный момент не удерживается в режиме записи.
- **Чтение и запись**: Методы `readLock()` и `writeLock()` блокируются, ожидая неэксклюзивного и эксклюзивного доступа соответственно.
- **Преобразование режимов**: StampedLock поддерживает методы, которые условно обеспечивают преобразования между тремя режимами.
- **Не реентерабельный**: StampedLock не является реентерабельным.

Оба механизма блокировки имеют свои преимущества и могут быть использованы в зависимости от конкретных требований к приложению. Однако важно помнить, что использование этих механизмов требует глубокого понимания многопоточности и синхронизации в Java.