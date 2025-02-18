# Разработка веб приложения «Emograph» на JavaSpring

Проект был реализован с использованием современных технологий веб-разработки, таких как Java Spring Framework, Thymeleaf, Bootstrap и PostgreSQL.


### В процессе разработки были достигнуты следующие цели:
- Ежедневные записи: Пользователь может создавать записи о своих чувствах, описывать свои переживания и выражать свои мысли.
- Просмотр и редактирование записей в своём дневнике.
- Просматривать справочник чувст, для подсказки заполнения своих записей.
- Конфиденциальность и безопасность: Для защиты личных данных пользователей приложение обеспечивает возможность установки пароля.


### Дальнейшее развитие приложения предусматривает добавление нового функционала, а именно:

- Отслеживание настроения: Приложение позволит пользователю оценивать своё настроение каждый день, использовать разные шкалы (например, от 1 до 5 или отлично, хорошо, удовлетворительно, плохо, ужасно).
- Статистика и анализ: Пользователь сможет просматривать статистику своего настроения за определенный период времени, а также анализировать связь между своими эмоциями и внешними факторами (какие события или обстоятельства влияют на его настроение).
- Уведомления и напоминания: Приложение сможет отправлять пользователю уведомления, напоминая о важности записи своих чувств и настроения.


### Планируемые улучшения технической составляющей приложения:

- Покрытие тестами кода приложения.
- Доработка кода в части возможности разделения функционала по Роли пользователя.
А именно, USER и ADMIN. Упрощенный интерфейс для пользователей с ролью USER (не будет доступа к редактированию Справочника и просмотру списка всех пользователей.)


# Внимание! Прочитать перед запуском приложения.

### Необходимо развернуть Docker-контейре по инструкции ниже(или использовать установленную базу данных Postgres на своём компьютере):

Разворачивание Docker-контейнеров представляет собой процесс запуска и управления контейнерами на целевом хосте. Для этого используется Docker-демон, который управляет жизненным циклом контейнеров, такими как создание, запуск, остановка и удаление.
Основные шаги разворачивания Docker-контейнеров:
1.	Установка Docker: Сначала необходимо установить Docker на целевом хосте. Для этого можно воспользоваться официальным сайтом Docker, где доступны инструкции по установке для различных операционных систем.
2.	Создание Docker-образа: Docker-образ представляет собой шаблон, на основе которого создается контейнер. Образ содержит все необходимые зависимости и конфигурации приложения. Образ можно создать с помощью Dockerfile, который описывает шаги по сборке образа.
3.	Создание контейнера: После создания образа необходимо создать контейнер на его основе. Это делается с помощью команды docker run. Например, для запуска контейнера на основе созданного образа:
Команда docker run используется для создания и запуска контейнера на основе Docker-образа. 

```powerShell
docker run --name diplom-postgres -e POSTGRES_PASSWORD=admin -e POSTGRES_DB=diplom_db -d -p 5432:5432 postgres
```

## Давайте разберем каждый параметр данной команды:
-	--name diplom-postgres: Устанавливает имя контейнера как diplom-postgres. Это удобно для идентификации контейнера при его управлении.
-	-e POSTGRES_PASSWORD=admin: Устанавливает переменную окружения POSTGRES_PASSWORD со значением admin для задания пароля для пользователя postgres в базе данных PostgreSQL.
-	-e POSTGRES_DB=diplom_db: Устанавливает переменную окружения POSTGRES_DB со значением diplom_db для создания базы данных с именем diplom_db в PostgreSQL.
-	-d: Запускает контейнер в фоновом режиме (detached mode).
-	-p 5432:5432: Пробрасывает порт 5432 из контейнера на хостовую машину. Первое число (5432) - порт на хостовой машине, второе число (5432) - порт в контейнере, на котором работает PostgreSQL.
-	postgres: Имя Docker-образа, на основе которого будет создан контейнер. В данном случае, это официальный образ PostgreSQL из Docker Hub.

После выполнения этой команды будет создан и запущен контейнер с именем diplom-postgres, в котором будет работать PostgreSQL с базой данных diplom_db и паролем admin, пробрасывая порт 5432 для доступа к базе данных извне контейнера.

Далее запускаем исполняемый файл приложения - DiplomApplication






