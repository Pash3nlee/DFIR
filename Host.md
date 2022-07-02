#### Создание криминалистического триажа:

```
$MFT, $Extend\,
C:\Windows\Prefetch\
C:\Windows\System32\config\{SAM, SYSTEM, SOFTWARE}
C:\Windows\appcompat\Programs\{AMCACHE.HVE, RecentFileCache.bcf}
C:\Users\%username%\NTUSER.DAT
C:\Users\%username%\AppData\
C:\Windows\TEMP\
C:\Windows\ProgramData\
C:\Windows\System32\Tasks\Task_Name\
C:\Windows\System32\winevt\Logs\
C:\Windows\System32\sru\SRUDB.dat
C:\Windows\System32\wbem\Repository\OBJECTS.DATA
```

#### Изучение файловой системы:

##### $MFT
Главная файловая  таблица

```MFTECMD.exe-f E:\$MFT --at—csv E:\OUT```
```Open with TimeLine Explorer```

##### $USNJRNL
*Записывает информацию о манипуляциях с файлами*

```MFTECMD.exe-f E:\$Extend\$UsnJrnl:$J --at—csv E:\OUT```
```Open with TimeLine Explorer```

##### Prefetch файлы
*Хэшпути к исполняемому файлу и его имя, количество запусков и временные метки, файлы и каталоги на которые ссылался исполняемый файл*

```PECmd.exe -f E:\SH.EXE-89D7F45B.pf```

##### System resource usage monitor
*SRUDB.dat -база данных формата ESE, связь пользователей и запущенных ими процессов, статистика использования сети, статистика используемых ресурсов, информация о длительности работы приложения.*

```C:\Windows\System32\sru\SRUDB.dat```
```Для просмотра и интерпретации содержимого можно использовать SRUM-DUMP.```

##### Objects.data
*Хранит WMI активность (Сбор данных на локальном или удаленном хосте, закрепление, распространение по сети)*

```Wmi-parser.exe -i E:\Objects.data```
```Открывать можно с помощью Hex Editor```
