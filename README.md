**support bot v2.0 с Инлаин кнопками**

**Author:** @ArchieWh1te

**Language:** Python 3.8

**framework for Telegram** Aiogram 2.23.1 

**License:** Free

[![PyPI](https://img.shields.io/pypi/v/aiogram?label=aiogram&logo=telegram&logoColor=aiogram)](https://pypi.org/project/aiogram/)
![PyPI](https://img.shields.io/pypi/v/python-dotenv?label=python-dotenv&logo=python-dotenv&logoColor=python-dotenv)
![PyPI](https://img.shields.io/pypi/v/SQLAlchemy?label=SQLAlchemy&logo=sqlite)
![PyPI](https://img.shields.io/pypi/v/gino?label=gino)
![PyPI](https://img.shields.io/pypi/v/asyncpg?label=asyncpg&logo=asyncpg)
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/aiogram?color=green&logo=python&logoColor=green)
### Бот Технической поддержки 
![title](https://habrastorage.org/r/w1560/getpro/habr/upload_files/18e/2dd/c68/18e2ddc682f08268b6e89e1c0949fcae.png)

**Описание:**

Бот технической поддержки — это упорядоченная и технологичная организация деятельности предприятия для ведения переговоров между пользователем и сотрудниками технической поддержки. 
Написаный на фреймворке AioGram на языке Python. 

**Действующие лица:**

+ Ваши Пользователи (клиенты),

+ Закрытый Чат Поддержки (где сидят те, кто будет отвечать на вопросы Пользователей),

+ Бот (которому Пользователи будут писать свои вопросы).

**Вот так это все будет работать:**

1. Вы публикуете ссылку на Бота.
2. Пользователи регистрируются в нём указывая данные которые попросит бот.
3. После регистрации Пользователи пишут в него свои вопросы через кнопку `Задать вопрос`.
4. Бот пересылает их сообщения в ваш Чат Поддержки.
5. В этом чате вы или ваши помощники отвечают на сообщение (через  инлаин кнопку `Ответить`).
6. Бот пересылает ответ обратно пользователю от своего лица, скрывая аккаунт отвечающего.

**Регистрация пользователей:**

1. Регистрация пользователей проходит через бота по кнопке Регистрация.
2. Бот попросил ввести данные Фамилию, Имя, номер телефона и организацию(магазин).
3. После регистрации данные запишутся в БД таблицы PostgreSQL.
4. Пользователь(клиенты) смогут задать вопрос по кнопке `Задать вопрос`.

**Регистрация администраторов (сотрудники Технической поддержки):**

1. Регистрация сотрудников ТП в БД происходит по команде `/newadmin`.
2. После этого надо установить через **PgAdmin** в таблице `admins` в столбце `flag` вместо `noadmin` значение `admin` (делается один раз для главного админа)

![clist](screen/admin/noadmin.png)
![clist](screen/admin/admin.png)
3. Чтобы дать права остальным сотрудникам нужно использовать команду `/флаг ID_пользователя`

**Запуск бота**

Все зависимости хранятся в файле `requirements.txt`

Для запуска бота используйте файл *```app.py```*

**Команды админа:**

```
/ответ id ТЕКСТ  - ответить пользователю от имени бота

/бан id причина  - забанить пользователя у бота

/разбан id  - снять бан пользователя

/нотис  - отправить уведомление всем сотрудникам ТП

/профиль ID-Пользователя  - Посмотреть профиль пользователя

/флаг ID-Администратора  - Дать права Администратора

/унфлаг ID-Администратора  - Снять права Администратора

/магазин ID-Пользователя НазваниеОрганизации  - Сменить организацию у пользователя

/удалить ID-Пользователя  - Удалить пользователя из БД

/фамилия ID-Пользователя Фамилия_Пользователя - Сменить Фамилию у пользователя

/имя ID-Пользователя Фамилия_Пользователя - Сменить Имя у пользователя

/номер ID-Пользователя Номер_Пользователя - Сменить номер у пользователя
```
**Для работы вам потребуется:**

1)установить все зависимости из *requirements.txt*

2)Установить **PostgreSQL** и настроить его 

3)Отредактировать файл **.env** там указываете конфигурацию для подключения к **PostgreSQL** и токкен для бота.
```
BOT_TOKEN=тутваштоккен

ip=localhost

PGUSER=пользовательПостгресса

PASSWORD=парольотпользователяБД

DATABASE=имяБД
```
4)Изменить настройки в файле **config** на свои параметры в переменной *admins*

``admins = [
   тут айдишники администраторов]
``
## Видео
**Регистрация пользователя**

[![Register user](https://img.youtube.com/vi/YkVXT6cjICw/hqdefault.jpg)](https://youtu.be/YkVXT6cjICw)

**Подача заявки в группу ТП и ответ на неё**

[![Add application in bot form text](https://img.youtube.com/vi/3iXDVqx3fSg/hqdefault.jpg)](https://youtu.be/3iXDVqx3fSg)


## Скриншоты

**Админский блок**

*Регистрация администратора*

![newadmin](screen/admin/newadmin.png)

*После регистрации как администратор*

![newadmin_before](screen/admin/newadmin2.png)

*Команды админа*

![clist](screen/admin/clist.png)

*Команды админа из панели*

![clistpanel](screen/admin/clistpanel.png)

*Панель управления Администратора*

![adminpanel](screen/admin/adminpanel.png)

*Дать права администратора*

![flag](screen/admin/flag.png)

*Ответ через кнопку Ответить*

![answer](screen/admin/answer.png)

*Уведомление о запуске бота*

![notification](screen/admin/notification.png)

**Пользовательский блок**

*Команда /start*

![start](screen/user/start.png)

![start](screen/user/kb_start.png)

*Регистрация Фамилия:*

![familia](screen/user/familia.png)

*Регистрация Имя:*

![name](screen/user/name.png)

*Регистрация Номер:*

![phone](screen/user/phone.png)

*Регистрация Организация(Магазин):*

![magazin](screen/user/magazin.png)

*Завершение регистрации*

![exitreg](screen/user/exitreg.png)

*Команда /start после регистрации*

![start_2](screen/user/start2.png)

*Когда бот не видит команд*

![echo](screen/user/echo.png)

*После нажатия на кнопку Задать вопрос*

![kb_answer](screen/user/kb_answer.png)

*Подача заявки*

![zayavka](screen/user/zayavka.png)

![zayavka2](screen/user/zayavka_2.png)

*Ответ от сотрудников ТП*

![otvet_adm](screen/user/otvet_ot_admina.png)

*После ответа от ТП Закрытие заявки*

![new_answer](screen/user/new_answer.png)

*Если заявку не закрыли то продолжаем диалог*

![ne_zakrita](screen/user/nezakrita.png)