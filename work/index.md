# Работа с GitHub

## Milestones (этапы)

Для добавления переходим в Issues (или Pull requests) - Milestone - New milestone

Указать название, например:

```text
Подготовка проекта
```

![alt text](images/image.png)

Также создать milestone для `Cпринт 2` и так далее.

## Issues (задачи)

Переходим в Issues - New Issue

Заполняем информацию о задаче:

* Title - Составить описание и техническое задание
* Description - ... (указано на рисунке)
* Assigness (ответственный за выполнение задачи), можно указать сразу себя или выбрать другого участника команды
* Labels (метки) - выбрать соответствующие метки (можно изменить на свои), в данном случае подходит `documentation`
* Milestone (этап) - в данном случае "Подготовка проекта"

![alt text](images/image-1.png)

## Pull requests

PR (Pull request) используется для внесения изменений из одной ветки (в которой решается задача (issue)) в другую ветку (обычно в основную - main).

Для этого определяется с выбором задачи над которой будет вестись работа, например

```text
Составить описание и техническое задание (#1)
```

![alt text](images/image-2.png)

Открываем папку проекта в VS Code.

Слева внизу можно увидеть название текущей ветки.

![alt text](images/image-3.png)

Необходимо быть на актуальном коммите ветки main. Для этого слева внизу рядом с названием ветки можно нажать Synchronize Changes.

![alt text](images/image-4.png)

Или выполнить только вытягивание (pull) изменений: Source Control - More Actions - Pull, Push - Pull

![alt text](images/image-5.png)

После этого убедиться, что ваша ветка находиться на том же коммите, что и в origin

![alt text](images/image-6.png)

Теперь нужно создать ветку для работы над задачей #1

Можно нажать слева внизу на текущую ветку, и выбрать Create new branch

![alt text](images/image-7.png)

Ввести название новой ветки, обычно указывается в стиле (tech-spec или docs/tech-spec), укажем spec

![alt text](images/image-8.png)

Увидеть, что теперь подключена новая ветка можно внизу слева и в Git Graph.

![alt text](images/image-9.png)

В соответствии с выбранной задачей добавим файл `Техническое задание.md`

![alt text](images/image-10.png)

Также внесем изменения в файл `README.md` в соответствии с задачей

![alt text](images/image-11.png)

Далее переходим в Source Control и хорошей практикой является минимальный просмотр вносимых изменений в файл, чтобы случайно не добавить лишние файлы/текст/код.

![alt text](images/image-12.png)

После проверки отмечаем файлы с помощью `+` напротив их имени. В список Staged Changes.

![alt text](images/image-13.png)

Указываем в Message суть вносимых изменений

![alt text](images/image-14.png)

В Git Graph можем увидеть, что новый коммит был добавлен только в текущую ветку (spec), но не в main

![alt text](images/image-15.png)

Теперь опубликуем ветку с помощью Public Branch. И увидим, что эта ветка также есть в удаленном репозитории (GitHub).

![alt text](images/image-16.png)

После публикования ветки GitHub сразу предлагает создать для нее PR - Compare & pull request

![alt text](images/image-17.png)

Иначе можно перейти в Pull requests - New pull request

И выбрать compare - spec (откуда брать изменения), а base - оставить main (куда вносить измения)

![alt text](images/image-18.png)

Ниже можно увидеть сравнение веток (вносимые изменения)

Их можно изменить в дальнейшем

![alt text](images/image-19.png)

Создаем PR - Create pull request

Заполняем информацию о PR:

* Title - суть изменений для задачи (может совпадать с названием задачи)
* Description - указываем дополнительную информаци, если необходимо
* Reviewers - запрашиваем ревью (можно позже)
* Assignees (ответственный) - обычно тот же человек, что и в задаче
* Labes (метки) - обычно те же, что и в задаче
* Milestone (этап) - обычно такой же как и в задаче

![alt text](images/image-20.png)

Также справа указать связанную задачу: Development

![alt text](images/image-21.png)

### Ревью (Review)

В верхней панели PR:

* Conversation - история активности, комментарии
* Commits (коммиты) - которые внесены в ветке (может быть несколько)
* Checks - относиться к CI/CD
* Files changed (изменения)

![alt text](images/image-22.png)

Ревью выполняется во вкладке Files changed

![alt text](images/image-23.png)

Так как эта задача связана с markdown-файлами, стоит также посмотреть итоговый вариант для этого можно перейти из подзаголовка PR в ветку `spec` (либо на странице Code переключить ветку).

Если PR связан с программным кодом стоит развернуть проект локально или на сервере, чтобы проверить работоспособность.

По стилю написания или работоспособности можно добавить комментарии:

* к строке/строкам
* к файлу
* общий комментарий (далее можно будет указать)

Ревью бывает 3-х типов:

* Comment - комментарий
* Approve - одобрение изменений
* Request changes - требуется исправления (стоит указать один или несколько комментариев)

![alt text](images/image-24.png)

Если ревьюер требует внести исправления, то необходимо исправить и запросить снова ревью.

Если необходимо можно указать комментарий с уточняющими вопросами или предложением другого варианта исправления.

![alt text](images/image-25.png)

Если PR одобрен, то отображается зеленая галочка.

![alt text](images/image-26.png)

После одобрения PR, можно смержить изменения в основную ветку.

Для этого во вкладке Conversation (внизу) перейти к Changes approved.

Можно выполнить обычный Merge pull request (но в реальных проекта более предпочтительный вариант Squash and merge или Rebase and merge).

И выпонить Merge

![alt text](images/image-27.png)

Если необходимо, то изменить сообщение и нажать Confirm merge

![alt text](images/image-28.png)

После мерджа (слияния изменений) в основную ветку, можно удалить ветку в которой велась работа: Delete branch (потом, если необходимо можно ее восстановить).

![alt text](images/image-29.png)

Теперь в основной ветке имеются изменения из PR

![alt text](images/image-30.png)

В локальном проекте можно выполнить Synchronize Changes (синхронизация изменений) или Pull (вытягивание изменений). Можно выполнить на следующем шаге.

![alt text](images/image-31.png)

Слева внизу можем изменить ветку на main. И выполнить синхронизацию или вытягивание.

И теперь можем увидеть, что в основной ветке есть изменения из ветки `spec`

![alt text](images/image-32.png)
