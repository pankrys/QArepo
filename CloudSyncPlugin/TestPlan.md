<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.321 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β33
* Tue Jul 05 2022 21:10:46 GMT-0700 (PDT)
* Source doc: Тест план Cloud sync plugin
----->


**Тест-план функционала Cloud sync plugin**

Идея:

Протестировать работоспособность функционала Cloud sync plugin в соответствии со спецификациями 

Ссылка на спецификацию:  

 

Чек-лист: 

Тест-кейсы: 



1. **CSP001 Проверка очистки очереди закачки в случае смены папки синхронизации в explorer**

    _Дата создания:_ 11-06-2022


    _Дата изменения:_ 11-06-2022


    _Создатель:_ Задоров Дмитрий


    _Идея:_ при смене активной папки в процессе работы должна выполниться синхронизация новой папки, при этом очередь в памяти для 
отправки старых данных должна быть очищена 


    _Тип:_ Отрицательный


    _Данные:_

1. Виртуальная машина с установленным плагином (VM1)
2. Тестовая папка с комплектом больших файлов №1 ($testdir1) (размер 2GB)
3. Тестовая папка с комплектом файлов №2 ($testdir2) (размер 100 Mb)
4. Доступ к тестовому серверу с установленным экземпляром Cloud-server (cloud)

	_Шаги выполнения:_



1. На VM1 устанавливаем скорость сетевого интерфейса в 10 мегабит
2. При помощи функционала Explorer выбираем  $testdir1
3. При помощи любой утилиты, следящей за объемом потребляемой памяти процессом, ожидаем увеличения потребляемой памяти > 1 Gb
4. По достижении этого значения, при помощи функционала Explorer выбираем  $testdir2

	_Ожидаемый результат:_ Потребляемая память процессом плагина уменьшилась до уровня максимум 100Mb + 30MB (допустим, что 
процесс обычно потребляет столько в процессе работы)  

