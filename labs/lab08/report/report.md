---
## Front matter
title: "Отчёт по лабораторной работе №8"
subtitle: "дисциплина: Архитектура компьютеров"
author: "Ведьмина Александра Сереевна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение навыков написания программ с использованием циклов и обработкой
аргументов командной строки.

# Задание

1. Изучить теорию по организации стека
2. Ознакомиться с реализацией циклов в NASM
3. Выполнить задание для самостоятельной работы

# Теоретическое введение

Стек — это структура данных, организованная по принципу LIFO. Его основная функция - сохранение адресов возврата и передачи аргументов при вызове процедур. Кроме того, в нём выделяется память для локальных переменных и могут временно храниться значения регистров. Вершина стека - адрес последнего добавленного элемента, противоположный конец стека именуется дном.
В работе со стеками есть две основные операции: добавление элемента в вершину, извлечение элемента из вершины.

# Выполнение лабораторной работы

Создаю каталог lab08, перехожу в него и создаю там файл lab8-1.asm.

![Создание lab8-1.asm](image/Screenshot from 2023-11-28 10-07-46.png){#fig:001 width=100%}

В созданный файл ввожу текст программы вывода значений регистра eсх.

![Ввод программы в lab8-1.asm](image/Screenshot from 2023-11-28 10-09-18.png){#fig:002 width=100%}

Создаю исполняемый файл и проверяю его работу.

![Запуск lab8-1](image/Screenshot from 2023-11-28 10-13-52.png){#fig:003 width=100%}

Изменяю текст программы в данном файле, добавляя именение значения регистра ecx в цикле.

![Изменение программы в lab8-1.asm](image/Screenshot from 2023-11-28 10-15-27.png){#fig:004 width=100%}

Cоздаю исполняемый файл и запускаю его. 

![Запуск изменённого lab8-1](image/Screenshot from 2023-11-28 10-16-41.png){#fig:005 width=100%}

Цикл получился бесконечным. Вновь вношу изменения в lab8-1.asm, добавляя команды push и pop.

![Повтороное изменение программы в lab8-1.asm](image/Screenshot from 2023-11-28 10-18-06.png){#fig:006 width=100%}

Создаю исполняемый файл и запускаю его. Теперь число проходов соответствует значению N, введенному с клавиатуры.

![Запуск вновь изменённого lab8-1](image/Screenshot from 2023-11-28 10-19-03.png){#fig:007 width=100%}

Создаю файл lab8-2.asm и ввожу в него текст программы, выводящей на экран аргументы командной строки.

![Ввод программы в lab8-2.asm](image/Screenshot from 2023-11-28 10-20-20.png){#fig:008 width=100%}

Создаю исполняемый файл и запускаю его, указав "аргумент1 аргумент 2 'аргумент 3'". Таким образом, программой будет обработано три аргумента.

![Запуск lab8-2](image/Screenshot from 2023-11-28 10-21-40.png){#fig:009 width=100%}

Далее создаю файл lab8-3.asm и ввожу текст программы, вычисляющую сумму аргументов командной строки.

![Ввод программы в lab8-3.asm](image/Screenshot from 2023-11-28 10-22-46.png){#fig:010 width=100%}

Создаю исполняемый файл и запускаю его.

![Запуск lab8-3](image/Screenshot from 2023-11-28 10-24-00.png){#fig:011 width=100}

Затем изменяю текст программы так, чтобы она вычисляла произведение аргументов командной строки.

![Изменение программы в lab8-3.asm](image/Screenshot from 2023-11-28 10-42-09.png){#fig:012 width=100%}

Создаю исполняемый файл и запускаю его.

![Запуск изменённого lab8-3](image/Screenshot from 2023-11-28 10-41-47.png){#fig:013 width=100}

# Выполнение заданий для самостоятельной работы

Для выполнения заданий для самостоятельной работы создаю файл sumrub.asm.

![Создание файла sumrub.asm](image/Screenshot from 2023-11-28 10-42-45.png){#fig:014 width=100}

Ввожу в него программу, которая будет выводить сумму значений функции. Номер моего варианта - 4, поэтому я буду реализовывать 2*(х-1). 

![Ввод программы в sumrub.asm](image/Screenshot from 2023-11-28 11-12-49.png){#fig:015 width=100}

Создаю исполняемый файл и запускаю его.

![Запуск sumrub](image/Screenshot from 2023-11-28 11-12-33.png){#fig:016 width=100}

# Выводы

В ходе лабораторной работы я приобрела навыки написания программ, в которых используются циклы и обработка аргументов командной строки.
