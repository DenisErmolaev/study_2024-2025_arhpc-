---
## Front matter
title: "Отчёт по лабораторной работе 2"
subtitle: "Система контроля версий Git"
author: "Ермолаев Денис Николаевич НБИбд-01-24"

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

Изучить идеологию и применение систем контроля версий, приобрести практические навыки по работе с системой Git.

# Порядок выполнения лабораторной работы

## Настройка Github

Для начала я создал учётную запись на сайте GitHub по адресу https://github.com/. После создания аккаунта я заполнил свои основные данные, такие как имя пользователя и email. Это нужно для того, чтобы Git мог идентифицировать мои действия при работе с репозиторием.
Далее я настроил SSH ключ для безопасного доступа к репозиториям. Для этого я сгенерировал пару SSH ключей с помощью команды:

ssh-keygen -C "Мое Имя <мой_email@mail.com>".

Полученный публичный ключ был добавлен в мой аккаунт GitHub для последующей аутентификации.

## Базовая настройка git

После настройки учётной записи на GitHub, я выполнил предварительную конфигурацию git. В терминале я ввёл следующие команды для настройки имени пользователя и электронной почты:

git config --global user.name "Мое Имя"

git config --global user.email "мой_email@mail.com"

Это нужно для того, чтобы каждый мой commit был подписан моими данными.

Для корректного отображения сообщений в git я также настроил параметр utf-8, введя команду:

git config --global core.quotepath false.

(рис. [-@fig:001])

![Базовая настройка git](image/01.png){ #fig:001 width=70%, height=70% }

## Создание SSH ключа


Для того чтобы безопасно подключаться к репозиторию, я сгенерировал SSH ключ с помощью команды:

ssh-keygen -C "Мое Имя <мой_email@mail.com>".

SSH ключ позволяет мне осуществлять безопасную аутентификацию на сервере 
без необходимости каждый раз вводить пароль. 
Полученный публичный ключ был загружен на GitHub в 
разделе "SSH and GPG keys". (рис. [-@fig:002])

![Создание SSH ключа](image/02.png){ #fig:002 width=70%, height=70% }

## Создание рабочего пространства и репозитория курса на основе шаблона

Я создал рабочее пространство для лабораторной работы, следуя предложенной структуре. Каталоги были созданы с помощью команды:

mkdir -p ~/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab02/. 

Эта структура позволяет легко управлять файлами лабораторных работ.(рис. [-@fig:003])

![Создание рабочего пространства](image/03.png){ #fig:003 width=70%, height=70% }

## Создание репозитория на основе шаблона

Для упрощения работы, я создал репозиторий на основе шаблона курса через 
веб- интерфейс GitHub. Я использовал готовый шаблон, который предоставил преподаватель, выбрав опцию "Use this template". 
Это помогло мне быстро настроить все необходимые файлы и каталоги.(рис. [-@fig:004])

![Клонирование репозитория](image/04.png){ #fig:004 width=70%, height=70% }

## Настройка каталога курса

Перейдя в каталог курса, я удалил ненужные файлы, такие как package.json, и создал необходимые каталоги для курса. 
Затем я выполнил первичную настройку структуры репозитория с помощью команд:

git add .

git commit -am "feat(main): make course structure" 

git push origin master

Эти действия загрузили структуру курса в центральный репозиторий на GitHub.
(рис. [-@fig:005], [-@fig:006], [-@fig:007], [-@fig:008], )

![Настройка каталога курса](image/05.png){ #fig:005 width=70%, height=70% }

![Настройка каталога курса](image/06.png){ #fig:006 width=70%, height=70% }

![Настройка каталога курса](image/07.png){ #fig:007 width=70%, height=70% }

![Настройка каталога курса](image/08.png){ #fig:008 width=70%, height=70% }

## Задание для самостоятельной работы

Для задания по самостоятельной работе я создал отчёт по выполнению лабораторной работы и разместил его в каталоге lab02. Затем я загрузил все файлы на GitHub с помощью команды:

git push.

# Выводы

В ходе выполнения лабораторной работы я получил практические навыки работы с системой контроля версий Git. Я освоил основные команды, настроил рабочее пространство и репозиторий, а также успешно загрузил результаты на GitHub.
