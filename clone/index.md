# Клонирование существующего репозитория

Заходим в проект на GitHub, который нужно клонировать (подключить) к себе на компьютер.

![alt text](image.png)

> В инструкции ранее указано как сгенерировать SSH-ключ и добавить его в свой аккаунт на GitHub.

Нажимем кнопку `Code`, чтобы скопировать ссылку для клонирования.

Выбираем вкладку `SSH` (данный способ более удобный и безопасный, чем HTTPS).

Копируем ссылку, в данном случае она:

```
git@gitlab.com/Laggon/example.git
```

![alt text](image-1.png)

Переходим (если необходимо, то создаем) папку в которую нужно будет клонировать репозиторий (в ней будет создана папка с названием проекта, в данном случае `example`).

![alt text](image-2.png)

Чтобы открыть командную строку в данной папке, в адресной строке указываем команду

```sh
cmd
```

И нажимем `Enter`

![alt text](image-3.png)

Откроется терминал в данной папке

![alt text](image-4.png)

Далее выполняем команду клонирования репозитория по ссылке, которую скопировали ранее из вкладки `Code`

```
git clone git@github.com:Laggon/example.git
```

> Если при создании `SSH-ключа` был указан пароль, то перед выполнением потребуется его ввести

Сообщение при успешном выполнении клонирования

![alt text](image-5.png)

В папке появится папка с репозиторием

![alt text](image-6.png)

Папку можно открыть с помощью `ПКМ - Открыть с помощью VS Code` (если при установке была включена эта опция) или `File - Open Folder` и выбрать папку репозитория (example).

![alt text](image-7.png)