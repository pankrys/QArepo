


#  **Тест-план функционала Explorer**

Идея:

Протестировать работоспособность функционала выбор папки для синхронизации на разных операционных системах. 

Ссылка на спецификацию:  

Чек-лист:


    [Чек-лист](https://docs.google.com/spreadsheets/u/0/d/1xCoKv3-ANt8kwDYpbMxfXE_MecX-Mgt2tbTYDAUD4-Q/edit)

Тест-кейсы:



## 1. **EXPL001 Смена активной папки в процессе работы**

  _Дата создания:_ 11-06-2022

  _Дата изменения:_ 11-06-2022

  _Создатель:_ Задоров Дмитрий

  _Идея:_ при смене активной папки в процессе работы должна выполниться синхронизация новой папки в направлении Local Workstation -> CloudStorage 

  _Тип:_ Положительный

### Данные:

1. Тестовая папка с комплектом файлов №1 ($testdir1)
2. Тестовая папка с комплектом файлов №2 ($testdir2)

### _Шаги выполнения:_



1. Открываем интерфейс Explorer
2. Указываем путь к $testdir1
3. Нажимаем сохранить
4. Переходим в Web-интерфейс
5. Убеждаемся что синхронизирована $testdir1 (_не лишний ли шаг?_)
6. Открываем интерфейс Explorer
7. Указываем путь к $testdir2
8. Нажимаем сохранить
9. Переходим в Web-интерфейс

#### 	_Ожидаемый результат:_ В Web-интерфейсе отображается содержимое $testdir2



## 2. **EXPL002 Изменение прав доступа к папке в процессе работы**

  _Дата создания:_ 11-06-2022

  _Дата изменения:_ 11-06-2022

  _Создатель:_ Задоров Дмитрий

  _Идея:_ Изменение прав доступа к папке во время работы приложения не должно приводить к потере файлов в CloudStorage

  _тип:_ негативный
    

### Данные:

1. Тестовая папка с комплектом файлов ($testdir)
2. Учетная запись Windows полным доступом к тестовой папке и правом запуска Explorer (testuser1 : password)

### 	_Шаги выполнения:_



1. Запускаем приложение от учетной записи из testuser1
2. Открываем интерфейс Explorer
3. Указываем путь к $testdir
4. Нажимаем сохранить
5. Переходим в Web-интерфейс
6. Убеждаемся что синхронизирована $testdir
7. Открываем проводник Windows
8. ПКМ по $testdir -> забираем права на чтение и запись
9. Переходим в Web-интерфейс

####  _Ожидаемый результат:_



1. В Web-интерфейсе остались синхронизированные файлы $testdir 

    _Примечание:_


		Создать тикет на улучшение: Показывать всплывающее сообщение в трее при невозможности синхронизации.	



