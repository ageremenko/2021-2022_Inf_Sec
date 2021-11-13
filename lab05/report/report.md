---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №5"
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

Изучение механизмов изменения идентификаторов, применения
SetUID- и Sticky-битов. Получение практических навыков работы в кон-
соли с дополнительными атрибутами. Рассмотрение работы механизма
смены идентификатора процессов пользователей, а также влияние бита
Sticky на запись и удаление файлов.

# Выполнение лабораторной работы

1. Вошёл в систему от имени пользователя guest(рис. [-@fig:001]).


![Вход в систему под guest](images/1.png){ #fig:001 width=70% }


2. Создал программу simpleid.c(рис. [-@fig:002]):


![Создание simpleid.c](images/2.png){ #fig:002 width=70% }


3. Скомплилировал программу и убедился, что файл программы создан([-@fig:003]).


![Компиляция](images/3.png){ #fig:003 width=70% }


4. Выполнил программу simpleid(рис. [-@fig:004]).


![Выполнение программы](images/4.png){ #fig:004 width=70% }


5. Выполнил системную программу id(рис. [-@fig:005]).


![Выполнение id](images/5.png){ #fig:005 width=70% }


6. Усложнил программу, добавив вывод действительных идентификаторов(рис. [-@fig:006])
 

![Усложнение программы](images/6.png){ #fig:006 width=70% }


7. Скомпилировал и запустил simpleid2.c(рис. [-@fig:007])


![Компиляция и запуск](images/7.png){ #fig:007 width=70% }


8. От имени суперпользователя выполнил команды(рис. [-@fig:008])


![Изменение прав](images/8.png){ #fig:008 width=70% }


9. Использовал sudo (рис. [-@fig:009])


![Использование sudo](images/9.png){ #fig:009 width=70% }


10. Выполнил проверку правильности установки новых атрибутов и смены владельца файла simpleid2. (рис. [-@fig:010])


![Выполнение проверки](images/10.png){ #fig:010 width=70% }


11. Запустил simpleid2 и id (рис. [-@fig:011])


![Запуск simpleid2 и id](images/11.png){ #fig:011 width=70% }


12. Проделал тоже самое относительно SetGID-бита (рис. [-@fig:012])


![Аналогичные действия для SetGID-бита](images/12.png){ #fig:012 width=70% }


13. Создал программу readfile.c


![Создание readfile.c](images/13.png){ #fig:013 width=70% }


14. Откомпилировал её


![Компиляция readfile.c](images/14.png){ #fig:014 width=70% }


# Выводы

Проделав данную лабораторную работу я изученил механизмы изменения идентификаторов, применения
SetUID- и Sticky-битов. Полученил практические навыки работы в кон-
соли с дополнительными атрибутами. Рассмотрел работы механизма
смены идентификатора процессов пользователей, а также влияние бита
Sticky на запись и удаление файлов.