[Назад к главной странице курса](https://github.com/icg-course/syllabus)
# Инструкция по использованию Git для сдачи лабораторных работ по интерактивной компьютерной графики

Для всех лабораторных работ предусмотрена онлайн-сдача на сайте GitHub. Для этого нужно проделать ряд шагов, описанных ниже. Следует отметить, что данная инструкция не может претендовать не только на полноту описания возможностей Git, но даже на полноценное введение, поскольку не описывает и 10% его самых базовых функций. Для более глубокого понимания сути и принципов работы с Git обратитесь к ссылкам в конце данной инструкции.

_Примечание_: Ниже приведены консольные команды системы контроля версий Git. Существует также большое количество GUI-клиентов этой системы, их использование допускается, но не рекомендуется при отсутствии опыта работы с ними.

Схема работы с системой Git для сдачи лабораторных работ в графическом виде приведена на следующем рисунке.

![Workflow](https://github.com/Fynduk/MetodaPoGity/blob/master/img/githubInstruction.png)

Далее в этой инструкции детально описаны шаги, необходимые для выполнения и сдачи лабораторных работ. В процессе чтения инструкции можно возвращаться к вышеприведенному рисунку для более наглядного восприятия.

## Настройка рабочей среды

Необходимо создать аккаунт на сайте GitHub, если у вас его еще нет. Это можно сделать на главной странице https://github.com/ Бесплатный аккаунт позволяет создавать неограниченное количество публичных репозиториев. Рекомендуется использовать реальный e-mail, поскольку через него будут осуществляться оповещения по ходу курса.

_Для чего используется в реальной жизни_: GitHub — крупнейший сервис для хостинга исходного кода и совместной разработки ПО, построенный на системе управления версиями Git.

Далее следует установить клиент системы управления версиями Git для вашей ОС. https://git-scm.com/downloads Он будет необходим для взаимодействия с сервером GitHub, а именно создания локальных репозиториев и отправки лабораторных работ на сервер. При установке в Windows необходимо выбрать опцию Use Git from the Windows Command Prompt, для того чтобы иметь возможность выполнять команды git из стандартного интерпретатора команд Windows cmd.exe.

_Для чего используется в реальной жизни_: Git — распределенная система управления исходными кодами программ. Используется для совместной работы с текстовой информацией. Позволяет хранить несколько версий документов и при необходимости переходить между ними. Также имеется возможность создания параллельных версий наборов документов с собственной хронологией, их объединение и множество других возможностей совместной разработки.

После установки требуется настроить клиент. Для этого из консоли требуется выполнить команды:

1.

```bash
git config --global user.name "ВАШЕ ИМЯ ПОЛЬЗОВАТЕЛЯ"
```

ВАШЕ ИМЯ ПОЛЬЗОВАТЕЛЯ — имя, которым будут подписаны ваши изменения. Рекомендуется выбрать такое имя, чтобы оно совпадало с вашим именем пользователя на GitHub.

2.

```bash
git config --global user.email "ВАШ EMAIL"
```

ВАШ EMAIL — адрес электронной почты, который указан в вашем профиле на GitHub.

## Тренировка работы с Git и GitHub

Если есть желание потренироваться в использовании приемов работы с GitHub, можно использовать в качестве песочницы репозиторий [db-course/students](https://github.com/db-course/students). В его описании указано, для чего он предназначен и как с помощью него можно отработать навыки перед сдачей лабораторных работ.

## Подготовка к выполнению лабораторной работы

Необходимо форкнуть (fork) приватный репозиторий, относящийся к лабораторной работе, которую вы хотите сдать. Для этого необходимо зайти в репозиторий, соответствующий работе (например, icg-course/icg_labwork3 для 3-й ЛР), и нажать кнопку Fork.

![Fork](https://github.com/Fynduk/MetodaPoGity/blob/master/img/fork.png)

Через несколько секунд на сервере GitHub будет создана ваша копия репозитория проекта.

![Forking](https://github.com/Fynduk/MetodaPoGity/blob/master/img/forking.png)

Вы будете работать с ней, внося изменения в виде кода лабораторной работы, а затем для сдачи работы делать pull-request (запрос на включение) в исходный репозиторий, где его будет просматривать и оценивать преподаватель.

_Для чего используется в реальной жизни_: форк репозитория проекта — создание копии проекта на сервере. Это может преследовать разные цели:

* Внесение собственного вклада в развитие чужого проекта. Для этого можно вносить соответствующие улучшения в свою копию проекта, а впоследствии путем использования pull-request (запроса на включение) предложить принять их в исходный проект его хозяину.

* Создание собственного проекта на базе существующего.

После создания форка на сервере GitHub нужно клонировать его на свой собственный компьютер. Откройте интрепретатор команд (cmd.exe), перейдите к каталогу, в котором будете выполнять лабораторные работы (например d:\db\lr), и выполните команду

```bash
git clone https://github.com/ВАШЕ ИМЯ/ИМЯ РЕПОЗИТОРИЯ С ЛР
```

Например, если студент с именем пользователя ivanov собирается клонировать репозиторий с 3-й ЛР, для того чтобы сдать ее, необходимо выполнить команду

```bash
git clone https://github.com/ivanov/icg_labwork3
```

Будет создан локальный каталог (в данном случае icg_labwork3), содержащий файл-шаблон лабораторной работы (имеет название index.html) и README.md (текстовый файл с описанием репозитория в формате markdown). Можно приступать к редактированию html-страницы(index.html).

## Выполнение лабораторной работы

Изменения следует вносить в .html-файл, расположенный в локальном клоне вашего репозитория. Эта локальная копия также представляет собой репозиторий, который связан с исходным ссылкой origin (источник). Все изменения, которые вы вносите в файл, следует сначала сохранять в локальном репозитории, а затем направлять в репозиторий-источник (ваш форк, лежащий на сервере GitHub).

Вы изменили файл, сохранили его и хотите записать его состояние в локальный репозиторий. Для этого нужно сначала поместить его в индекс (stage) — промежуточный список файлов, который затем будет зафиксирован в качестве текущего состояния. Необходимо выполнить команду

```bash
git add имя_файла
```

Например, для записи состояния всех файлов в локальный репозиторий, необходимо выполнить команду

```bash
git add .
```

Она добавит в индекс файл/файлы(при использовании '.'), который вы укажете. Проверить состояние индекса можно командой

```bash
git status
```

Если изменения в файлы с момента предыдущей фиксации не вносились, статус будет пустым. Если есть неиндексированные изменения (были изменены отслеживаемые файлы, уже добавленные в индекс файлы или добавлены новые файлы), то соответствующие файлы будут отмечены красным цветом. После внесения командой add состояния файла в индекс соответствующий файл будет отображен зеленым цветом как готовый к фиксации.

Фиксация состояния файла (commit) выполняется командой

```bash
git commit -m "ОПИСАНИЕ СОСТОЯНИЯ"
```

Здесь ОПИСАНИЕ СОСТОЯНИЯ — ваше сообщение, описывающее, что именно вы сохраняете. Например, так:

```bash
git commit -m "Добавлены новые узлы сложных геометрических объектов"
```

После выполнения команды commit изменения зафиксированы в локальном репозитории.

_Для чего используется в реальной жизни_: commit (коммит) — снимок состояния проекта в конкретный момент времени, также может быть рассмотрен как список изменений, внесенный разработчиком в предыдущее состояние проекта. Цель системы контроля версий — обеспечение доступа пользователей к состоянию проекта в любой момент времени. Список коммитов представляет собой историю изменений конкретной ветки проекта. Можно получить к нему доступ командой git log. При публикации на сервер публикуются не только сами файлы, но и все их версии со связанными с ними изменениями. Например, список изменений репозитория с описанием этого курса можно посмотреть здесь: https://github.com/icg-course/syllabus/commits/master

Нет четкой рекомендации, сколько коммитов необходимо делать для одной лабораторной работы. 

Можно наращивать изменения постепенно и документировать их, например:

```bash
git status
(нет изменений)
```

_...редактирование файлов..._

```bash
git status
(есть неиндексированные изменения, выделены красным цветом)
git add измененные_файлы
git status
(все изменения индексированы, выделены зеленым цветом)
```

_...увидели, что пропущена точка с запятой, редактирование файлов..._

```bash
git status
(есть неиндексированные изменения, выделены красным цветом)
git add измененные_файлы
git status
(все изменения индексированы, выделены зеленым цветом)
git commit -m "Добавлены геометрические примитивы"
```

_...редактирование файлов..._

```bash
git status
(есть неиндексированные изменения, выделены красным цветом)
git add измененные_файлы
git status
(все изменения индексированы, выделены зеленым цветом)
git commit -m "Добавлены материалы"
```

С другой стороны, можно отредактировать файл полностью, проиндексировать и закоммитить его. Это немного противоречит философии системы контроля версий, поскольку будет всего две версии вашего репозитория, начальная и исходная, без промежуточных, но допускается в учебных работах.

Если в лабораторной работе требуется приложить дополнительные файлы (например, снимок экрана), которых не было в репозитории, то они добавляются путем копирования в рабочую директорию, добавления в индекс (`git add имя_файла`) и фиксации (`git commit -m ...`).

## Сдача лабораторной работы

Для сдачи работы необходимо переписать (опубликовать) историю изменений (коммитов) из локального репозитория на сервер, в созданный вами репозиторий-форк. Напомним, на него указывает ссылка origin.

Для публикации истории служит команда push:

```bash
git push origin gh-pages
```

В ней указывается, в какой репозиторий происходит публикация (origin — репозиторий-источник, который был клонирован) и какой ветви (gh-pages — побочная ветвь). У проекта может быть несколько ветвей, но главной будет ветка master.

При публикации у вас могут быть затребованы учетные данные сайта GitHub, чтобы проверить, обладаете ли вы достаточными правами.

Публикация коммитов на сервер может быть не окончательной, вы можете продолжать работать над файлами, фиксировать изменения и публиковать их столько, сколько будет необходимо.

Чтобы сдать работу, необходимо отослать историю ваших изменений в центральный репозиторий этой работы в организации icg-course. Там их увидит и оценит преподаватель.

Выполнить push вы не сможете, т.к. не обладаете правами на запись в центральный репозиторий данной работы. Вместо этого вы можете отправить запрос на включение изменений (pull-request), и преподаватель получит уведомление о нем.

_Для чего используется в реальной жизни_: pull-request (запрос на включение) — основной способ вклада в проекты в открытым исходным кодом лицами, не являющимися членами проекта, но имеющими желание помочь. Помимо того, pull-request'ы могут использоваться внутри команды разработчиков проекта для обсуждения внесения изменений из одних ветвей проекта в другие.

Для создания pull-request'а зайдите на страницу своего репозитория и нажмите кнопку New pull request.

![Pull request 1](https://github.com/Fynduk/MetodaPoGity/blob/master/img/pullrequest1.png)

На появившейся странице будут отображены изменения, которые вы внесли в файлы репозитория. Нажмите Create pull request.

![Pull request 2](https://github.com/Fynduk/MetodaPoGity/blob/master/img/pullrequest2.png)

Далее вам будет предложено написать заголовок и комментарий к своему запросу. В заголовке напишите свою фамилию, инициалы, группу.

![Comment on pull request](https://github.com/Fynduk/MetodaPoGity/blob/master/img/comment_on_pullrequest.png)

Кнопка Create pull request внизу отправит ваш запрос на рассмотрение преподавателю.

Преподаватель сможет оставлять комментарии к вашему pull-request'у (например, для уточнения или указания на ошибки).

![Conversation](https://github.com/Fynduk/MetodaPoGity/blob/master/img/conversation.png)

Вы можете также отвечать на комментарии.

При появлении новых событий, связанных со сдачей работы, в правом верхнем углу страницы сайта будет отображено уведомление.

![Alert](https://github.com/Fynduk/MetodaPoGity/blob/master/img/alert.png)

Если вам необходимо доделать работу или исправить ошибки, то следует выполнить изменения в рабочем каталоге, зафиксировать их в локальном репозитории (подраздел "Выполнение лабораторной работы" данной инструкции) и опубликовать их в своем репозитории на GitHub (команда push). Эти изменения автоматически появятся в pull-request'е и будут доступны для рассмотрения преподавателем. После этого необходимо обязательно оставить в беседе комментарий, извещающий о сделанных вами изменениях, чтобы преподаватель увидел его.

В случае успешной сдачи преподаватель отмечает это соответствующим комментарием.

## Travis CI

Для успешной сдачи лабораторной работы, необходим пройти автоматическое тестирование программного обеспечения. Принцип достаточно прост: на отдельной машине работает некая служба, в обязанности которой входит получение исходного кода проекта, его сборка, тестирование, логирование, а также возможность предоставить для анализа данные выполнения перечисленных операций. Тестирование будет выполнено автоматически после добавления pull-request'а. 

![Travis CI](https://github.com/Fynduk/MetodaPoGity/blob/master/img/travis_ci_proc.png)

После проверки, если есть ошибки в коде Travis CI расскажет об этом(Details - для просмотра ошибок)

![Travis CI Failed](https://github.com/Fynduk/MetodaPoGity/blob/master/img/travis_ci_failed.png)

В случае успешной проверки, преподаватель увидит это и проверит вашу работу.

![Travis CI Done](https://github.com/Fynduk/MetodaPoGity/blob/master/img/travis_ci_done.png)

![Happy End](https://github.com/Fynduk/MetodaPoGity/blob/master/img/happy_end.png)
### Материалы на русском языке для самостоятельного углубленного изучения

* https://githowto.com/ru
* https://git-scm.com/book/ru/v1
* http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/ru/
* https://tproger.ru/translations/most-common-git-screwupsquestions-and-solutions/

[Назад к главной странице курса](https://github.com/icg-course/syllabus)