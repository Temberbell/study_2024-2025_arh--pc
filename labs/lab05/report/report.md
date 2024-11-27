---
## Front matter
title: "Лабораторная работа №5"
subtitle: "Основы работы с
Midnight Commander (mc). Структура программы на
языке ассемблера NASM. Системные вызовы в ОС
GNU Linux"
author: "Мочалкина Софья Васильевна"

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

Приобретение практических навыков работы в Midnight Commander. Освоение инструкций
языка ассемблера mov и int.

# Задание



1.Открыть Midnight Commander

2.Создать папку lab05 и внутри нее создать файл lab5-1.asm

3.Открыть файл lab5-1.asm, ввести информацию из листинга 5.1 и сохранить изменения

4.Убедится что файл содержит информацию

5.Оттранслировать текст файла lab5-1.asm, выполнить компановку объектного файла

6.Запустить файл

7.Скачать и скопировать файл in_out.asm с помощью клавиши f5

8.С помощью клавиши f6 скопировать файл lab5-1.asm с именем lab5-2.asm

9.Исправить файл lab5-2.asm в соответствии с листингом 5.2

10.В файле lab5-2.asm заменить подпрограмму sprintLF на sprint

11.Создать исполняемый файл и проверить его работу

12.Создать копию файла lab5-1.asm и внести изменения, чтобы выводила введенная строка на экран

13.Создать копию файла lab5-2.asm и внести изменения, чтобы выводила введенная строка на экран


# Теоретическое введение

![Название рисунка](теория1.png){#fig:001 width=100%}
![Название рисунка](теория2.png){#fig:001 width=100%}
![Название рисунка](теория3.png){#fig:001 width=100%}
![Название рисунка](теория4.png){#fig:001 width=100%}
![Название рисунка](теория5.png){#fig:001 width=100%}
![Название рисунка](теория6.png){#fig:001 width=100%}

# Выполнение лабораторной работы

1. Открываю Midnight Commander (см рис 1)

![Midnight Commander(рис.1)](image/Midnight_Commander.png){#fig:001 width=100%}

2. С помощью функциональной клавиши F7 создаю папку lab05 (рис. 2) 


![Создание папки lab05](image/создание_папки.png){#fig:001 width=100%}

3. Пользуясь строкой ввода и командой touch создаю файл lab5-1.asm (рис.3)

![создание файла lab5-1.asm(рис. 3)](image/создаём_файл1.png){#fig:001 width=100%}


4. С помощью функциональной клавиши F4 открываю файл lab5-1.asm для редактирования во встроенном редакторе. (рис. 4).

![Новый файл lab5-1 (рис.4)](image/открытие_1.png){#fig:001 width=100%}

5. Ввожу текст программы из листинга (рис. 5). С помощью функциональной клавиши F3 открываю файл lab5-1.asm для просмотра. Убеждаюсь, что файл содержит текст программы.

![Введённый текст(рис. 5)](image/ввожу_текст.png){#fig:001 width=100%}

6. Транслирую текст программы lab5-1.asm в объектный файл. Выполняю компо-
новку объектного файла и запускаю получившийся исполняемый файл. (рис. 6)

![Выполнение файла lab5-1 (рис. 6)](image/запуск1.png){#fig:001 width=100%}

7. Скачиваю файл in_out.asm со страницы курса в ТУИС. Копирую файл in_out.asm в каталог с файлом lab5-1.asm с помощью функциональной клавиши F5 (рис. 7).

![Копируем файл in_out.asm](image/копирование1.png){#fig:001 width=100%}
![Скопированный файл](image/копирование2.png){#fig:001 width=100%}

8. С помощью функциональной клавиши F6 создаю копию файла lab5-1.asm с именем
lab5-2.asm. (рис. 8)

![создаём lab5-2](image/создание_файла2.png){#fig:001 width=100%}

9. Исправляю текст программы в файле lab5-2.asm с использование подпрограмм из
внешнего файла in_out.asm в соответствии с листингом 5.2. Создаю исполняемый файл и проверяю его работу.(рис 9-10)

![Исправленный текст программы (рис. 9)](image/ввожу_текст2.png){#fig:001 width=100%}

![Работа файла lab5-2.asm(рис.10)](image/запуск2.png){#fig:001 width=100%}

10. Самостоятельная работа.

1. Создаю копию файла lab5-1.asm.(рис 11) Вношу изменения в программу (без использова-
ния внешнего файла in_out.asm), так чтобы она работала по следующему алгоритму:
• вывести приглашение типа “Введите строку:”;
• ввести строку с клавиатуры;
• вывести введённую строку на экран. (рис12)

![Копия файла lab5-1.asm.(рис 11)](image/создание_файла3.png){#fig:001 width=100%}

![Изменения](image/изменения_в_файле1.png){#fig:001 width=100%}

2. Получаю исполняемый файл и проверяю его работу. На приглашение ввести строку
ввожу свою фамилию. (рис. 13)

![Работа файла lab5-3 (рис. 13)](image/вывод3.png){#fig:001 width=100%}

3. Создаю копию файла lab5-2.asm.(рис. 14) Исправляю текст программы с использованием подпрограмм из внешнего файла in_out.asm, так чтобы она работала по следующему
алгоритму:
• вывести приглашение типа “Введите строку:”;
• ввести строку с клавиатуры;
• вывести введённую строку на экран. (рис. 15)

![Копия файла lab5-2.asm.(рис 14)](image/создание_файла4.png){#fig:001 width=100%}

![Изменения](image/изменения_в_файле2.png){#fig:001 width=100%}

4. Создаю исполняемый файл и проверяю его работу.

![Название рисунка](image/вывод4.png){#fig:001 width=100%}

# Выводы

В процессе выполнения лабораторной работы я ознакомилась со структурой программы на языке ассемблера NASM

# Список литературы{.unnumbered}

1. GDB: The GNU Project Debugger. — URL: https://www.gnu.org/software/gdb/.
2. GNU Bash Manual. — 2016. — URL: https://www.gnu.org/software/bash/manual/.
3. Midnight Commander Development Center. — 2021. — URL: https://midnight-commander.
org/.
4. NASM Assembly Language Tutorials. — 2021. — URL: https://asmtutor.com/.
5. Newham C. Learning the bash Shell: Unix Shell Programming. — O’Reilly Media, 2005. —
354 с. — (In a Nutshell). — ISBN 0596009658. — URL: http://www.amazon.com/Learning-
bash-Shell-Programming-Nutshell/dp/0596009658.
6. Robbins A. Bash Pocket Reference. — O’Reilly Media, 2016. — 156 с. — ISBN 978-1491941591.
7. The NASM documentation. — 2021. — URL: https://www.nasm.us/docs.php.
8. Zarrelli G. Mastering Bash. — Packt Publishing, 2017. — 502 с. — ISBN 9781784396879.
9. Колдаев В. Д., Лупин С. А. Архитектура ЭВМ. — М. : Форум, 2018.
10. Куляс О. Л., Никитин К. А. Курс программирования на ASSEMBLER. — М. : Солон-Пресс,
2017.
11. Новожилов О. П. Архитектура ЭВМ и систем. — М. : Юрайт, 2016.
12. Расширенный ассемблер: NASM. — 2021. — URL: https://www.opennet.ru/docs/RUS/nasm/.
13. Робачевский А., Немнюгин С., Стесик О. Операционная система UNIX. — 2-е изд. — БХВ-
Петербург, 2010. — 656 с. — ISBN 978-5-94157-538-1.
14. Столяров А. Программирование на языке ассемблера NASM для ОС Unix. — 2-е изд. —
М. : МАКС Пресс, 2011. — URL: http://www.stolyarov.info/books/asm_unix.
15. Таненбаум Э. Архитектура компьютера. — 6-е изд. — СПб. : Питер, 2013. — 874 с. —
(Классика Computer Science).
16. Таненбаум Э., Бос Х. Современные операционные системы. — 4-е изд. — СПб. : Питер,
2015. — 1120 с. — (Классика Computer Science)
