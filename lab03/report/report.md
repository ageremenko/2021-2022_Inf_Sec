---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №3"
subtitle: "дисциплина: Информационная безопасность"
author: "Ерёменко Артём Геннадьевич, НПИбд-01-18"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: false # List of figures
lot: false # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей

# Выполнение лабораторной работы

1. В установленной операционной системе создал учётную запись пользователя guest2 (использую учётную запись администратора): (рис. [-@fig:001]).


![Создание учётной записи guest2](images/1.png){ #fig:001 width=70% }


2. Задал пароль для пользователя guest2 (использую учётную запись администратора)(рис. [-@fig:002]):


![Установка пароля для guest2](images/2.png){ #fig:002 width=70% }


3. Добавил пользователя guest2 в группу guest.([-@fig:003]).


![Добавление пользователя в группу](images/3.png){ #fig:003 width=70% }


4. Осуществил вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли.(рис. [-@fig:004]-[-@fig:005]).


![Вход в систему от пользователя guest](images/4.png){ #fig:004 width=70% }

![Вход в систему от пользователя guest2](images/5.png){ #fig:005 width=70% }


5. Для обоих пользователей командой pwd определил директорию, в которой нахожусь. Сравнил её с приглашениями командной строки.(рис. [-@fig:006]-[-@fig:007]).


![Вывод команды pwd для guest](images/6.png){ #fig:006 width=70% }

![Вывод команды pwd для guest2](images/7.png){ #fig:007 width=70% }


6. Уточнил пользователя, группу, кто входит в неё
и к каким группам принадлежит он сам (рис. [-@fig:008]-[-@fig:009]). Определил командами
groups guest и groups guest2, в какие группы входят пользователи guest и guest2. Сравните вывод команды groups с выводом команд id -Gn и id -G. (рис. [-@fig:010]-[-@fig:011])


![Проверка uid и gid у guest](images/8.png){ #fig:008 width=70% }

![Проверка uid и gid у guest2](images/9.png){ #fig:009 width=70% }

![Вывод команд groups, id -Gn и id -G у guest](images/10.png){ #fig:010 width=70% }

![Вывод команд groups, id -Gn и id -G у guest](images/11.png){ #fig:011 width=70% }


7. Сравнил полученную информацию с содержимым файла /etc/group. (рис. [-@fig:012])


![Cодержимое файла /etc/group](images/12.png){ #fig:012 width=70% }


8. От имени пользователя guest2 выполнил регистрацию пользователя
guest2 в группе guest.(рис. [-@fig:013]).


![Регистрация пользователя guest2 в группе guest](images/13.png){ #fig:013 width=70% }


9. От имени пользователя guest изменил права директории /home/guest,
разрешив все действия для пользователей группы (рис. [-@fig:014]).


![Изменение прав директории](images/14.png){ #fig:014 width=70% }


10. От имени пользователя guest снял с директории /home/guest/dir1
все атрибуты(рис. [-@fig:015]).


![Снятие всех прав](images/15.png){ #fig:015 width=70% }


11. Заполнил таблицу «Установленные права и разрешённые действия»
(см. табл. 1), выполняя действия от имени владельца директории (файлов), определив опытным путём, какие операции разрешены, а какие нет.
Если операция разрешена, заносил в таблицу знак «+», если не разрешена, знак «-».


		
Права директории | Права файла_____ | Создание файла | Удаление файла | Запись в файл | Чтение файла | Смена директории | Просмотр файлов в директории | Переименование файла | Смена атрибутов файла
------------- | ------------ | -- | ---- | ------ | ------ | ------ | ---------- | ------ | ---                       
d------ (000) |	-------(000) |  - |	-    |	-     |	-      |    -   |   -        |	-     | -
d--x--- (010) |	-------(000) |	- |	-    |	-     |	-      |	+   |	-        |	-     |	-
d--x--- (010) |	---x---(100) |	- |	-    |	-     |	-      |	+   |	-        |	-     |	-
d--x--- (010) |	--w----(200) |	- |	-    |	+     |	-      |	+   |	-        |	-     |	-
d--x--- (010) |	--wx---(300) |	- |	-    |	+     |	-      |	+   |	-        |	-     |	-
d--x--- (010) |	-r-----(400) |	- |	-    |	-     |	+      |	+   |	-        |	-     |	-
d--x--- (010) |	-r-x---(500) |	- |	-    |	-     |	+      |	+   |	-        |	-     |	-
d--x--- (010) |	-rw----(600) |	- |	-    |	+     |	+      |	+   |	-        |	-     |	-
d--x--- (010) |	-rwx---(070) |	- |	-    |	+     |	+      |	+   |	-        |	-     |	- 
d-w---- (020) |	-------(000) |	- |	-    |	-     |	-      |	-   |	-        |	-     |	-
d-wx--- (030) |	-------(000) |	+ |	+    |	+     |	+      |	+   |	-        |	+     |	+
d-wx--- (030) |	---x---(100) |	+ |	+    |	+     |	+      |	+   |	-        |	+     |	+
d-wx--- (030) |	--w----(200) |	+ |	+    |	+     |	+      |	+   |	-        |	+     |	+
d-wx--- (030) |	--wx---(300) |	+ |	+    |	+     |	+      |	+   |	-        |	+     |	+
d-wx--- (030) |	-r-----(400) |	- |	+    |	+     |	+      |	+   |	-        |	+     |	+
d-wx--- (030) |	-r-x---(500) |	+ |	+    |	-     |	+      |	+   |	-        |	+     |	+
d-wx--- (030) |	-rw----(600) |	+ |	+    |	+     |	+      |	+   |	-        |	+     |	+
d-wx--- (030) |	-rwx---(070) |	+ |	+    |	+     |	+      |	+   |	-        |	+     |	+
dr----- (040) |	-------(000) |	- |	-    |	-     |	-      |	-   |	+        |	-     |	-
dr-x--- (050) |	-------(000) |	- |	-    |	-     |	-      |	+   |	+        |	-     |	-
dr-x--- (050) |	---x---(100) |	- |	-    |	-     |	-      |	+   |	+        |	-     |	+
dr-x--- (050) |	--w----(200) |	- |	-    |	+     |	-      |	+   |	+        |	-     |	+
dr-x--- (050) |	--wx---(300) |	- |	-    |	+     |	-      |	+   |	+        |	-     |	+
dr-x--- (050) |	-r-----(400) |	- |	-    |	-     |	+      |	+   |	+        |	-     |	+
dr-x--- (050) |	-r-x---(500) |	- |	-    |	-     |	+      |	+   |	+        |	-     |	+
dr-x--- (050) |	-rw----(600) |	- |	-    |	+     |	+      |	+   |	+        |	-     |	+
dr-x--- (050) |	-rwx---(070) |	- |	-    |	+     |	+      |	+   |	+        |	-     |	+
drw---- (060) |	-------(000) |	- |	-    |	-     |	-      |	-   |	+        |	-     |	+
drwx--- (070) |	-------(000) |	+ |	+    |	-     |	-      |	+   |	+        |	+     |	+
drwx--- (070) |	---x---(100) |	+ |	+    |	-     |	-      |	+   |	+        |	+     |	+
drwx--- (070) |	--w----(200) |	+ |	+    |	+     |	-      |	+   |	+        |	+     |	+
drwx--- (070) |	--wx---(300) |	+ |	+    |	+     |	-      |	+   |	+        |	+     |	+
drwx--- (070) |	-r-----(400) |	+ |	+    |	-     |	+      |	+   |	+        |	+     |	+
drwx--- (070) |	-r-x---(500) |	+ |	+    |	-     |	+      |	+   |	+        |	+     |	+
drwx--- (070) |	-rw----(600) |	+ |	+    |	+     |	+      |	+   |	+        |	+     |	+
drwx--- (070) |	-rwx---(070) |	+ |	+    |	+     |	+      |	+   |	+        |	+     |	+

Табл. 1


12. На основании заполненной таблицы определил те или иные минимально необходимые права для выполнения пользователем guest2 операций
внутри директории dir1, заполнил табл. 2.

Операция               | Минимальные права на директорию | Минимальные права на файл
---------------------- | ----------------- | --------------
Создание файла         | d-wx--- (030)     | -------(000)
Удаление файла         | d-wx--- (030)     | -------(000)
Запись в файл          | d--x--- (010)     | --w----(020)
Чтение файла           | d--x--- (010)     | -r-----(040)
Переименование файла   | d-wx--- (030)     | -------(000)
Создание поддиректории | d-wx--- (030)     | -------(000)
Удаление поддиректории | d-wx--- (030)     | -------(000)

Табл. 2

# Выводы

Проделав данную лабораторную работу я получил практические навыки работы в консоли с атрибутами файлов для групп пользователей