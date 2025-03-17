# DatabasesWorks

### Проект для отправления запрсоов в различные базы данных (БД) для получения сводных данных.

### Цели:
- организация отчётности по видам транспорта;
- организация отчётности по автомобильным гонкам;
- организация отчётности по бронированию номеров отелей;
- организация отчётности по работающим в различных подразделениях сотрудникам.

Каждый вариант отчётности происходит относительно соответствующей БД. Код для каждой БД расположен в отдельном файле.

### Задачи:
1. Локальное развёртывание БД;
2. По первой БД - поиск производителей и моделей спортивных мотоциклов мощьностью более 150 лошадиных сил и стоимостью менее $20 тыс.;
3. По первой БД - поиск
    1. автомобилей мощьностью более 150 лошадиных сил, объемом двигателя менее 3 л и стоимостью менее $35 тыс.;
    2. мотоциклов мощьностью более 150 лошадиных сил, объемом двигателя менее 1,5 л и стоимостью менее $20 тыс.;
    3. велосипедов с более 18 передачами и стоимостью менее $4 тыс.;
4. По второй БД - поиск и получение информации
    1. о наименьшей средней позиции автомобилей каждого класса в гонках;
    2. об автомобиле с наименьшей средней позицией в гонках;
    3. о классах автомобилей с наименьшей средней позицией в гонках и общем кол-ве проведённых гонок с участием автомобилей этих классов;
    4. о лучших автомобилях в гонках относительно своих классов;
    5. о классах с большим количеством лучших автомобилей в гонках;
5. По третьей БД - организация анализа:
    1. клиентов, бровировавших более двух номеров в разных отелях;
    2. клиентов, бровировавших более двух номеров в разных отелях на сумму более 500 долларов;
    3. предпочтений клиентов относительно их бронирований в отелях;
6. По четвёртой БД - поиск сотрудников
    1. подчиненных Ивану Иванову вместе с их подчиненными, подчиненными подчиненных и т. д. с выводом их привяки к проектам и заданиям;
    2. подчиненных Ивану Иванову вместе с их подчиненными, подчиненными подчиненных и т. д. с выводом их привяки к проектам и заданиям, кол-ва их подчиненных и кол-ва задач, над которыми они работают;
    3. являющихся менеджерами и имеющих подчиненных.

---

### Структуры БД:
1. По видам транспорта: в данной БД хранятся сущности
    1. «Виды транспорта», содержащая информацию о производителе, модели и типе транспорта;
    2. «Автомобили», содержащая информацию об идентификационном номере автомобиля, модели, объеме бака в литрах, мощности в лошадиных силах, стоимости и виде коробки переключения передачи;
    3. «Мотоциклы», содержащая информацию об идентификационном номере мотоцикла, модели, объеме бака в литрах, мощности в лошадиных силах, стоимости и типе мотоцикла;
    4. «Велосипеды», содержащая информацию о серийном номере, модели, количестве передач, стоимости и типе велосипеда;
2. По автомобильным гонкам: в данной БД хранятся сущности
    1. «Классификация», содержащая информацию о классе и типе автомобиля, стране-производителе, количестве дверей, объеме бака в литрах и весе автомобиля;
    2. «Автомобили», содержащая информацию о названии, классе и годе выпуска автомобиля;
    3. «Гонки», содержащая информацию о названии и дате гонки;
    4. «Результаты», содержащая информацию об автомобиле, гонке, в которой этот автомобиль участвовал, и месте, которое получила машина за гонку;
3. По бронированию номеров отелей: в данной БД хранятся сущности
    1. «Отели», содержащая информацию об идентификаторе отеля, его названии и местоположении;
    2. «Комнаты», содержащая информацию об идентификаторе комнаты, идентификаторе отеля, которому принадлежит номер, типе комнаты, стоимости и вместительности номера;
    3. «Покупатели», содержащая информацию об идентификаторе покупателя, его имени, или ФИО, почте и телефоне;
    4. «Бронирования», содержащая информацию об идентификаторе бронирования, идентификаторах комнаты и покупателя, датах въезда в и выезда из комнаты
4. По организации отделений компании: в данной БД хранятся сущности
    1. «Отделения», содержащая информацию об идентификаторе отделения и его наименования;
    2. «Роли», содержащая информацию об идентификаторе роли и ее названии;
    3. «Сотрудники», содержащая информацию об идентификаторе сотрудника, его имени, или ФИО, должности, идентификаторах управляющего, отделения и роли;
    4. «Проекты», содержащая информацию об идентификаторе проекта, его наименовании, датах начала и окончания работы над проектом и идентификатор департамента;
    5. «Задачи», содержащая информацию об идентификаторе задачи, ее названии, назначении на содрудника и идентификаторе проекта.

---

### Реализованные функции:
1. Выполнение запросов поиска в БД относительно всех заданий:
    1. Запросы хранятся в БД в виде представлений;
    2. Запросы выполняются не относительно сущностей, а относительно представлений, которые выполняют запросы относительно сущностей БД;
2. Управление данными сущности «Виды транспорта» первой БД

### Нереализованные функции:
1. Управление данными сущносей
    1. первой БД: «Автомобили», «Мотоциклы», «Велосипеды»
    2. втоорой БД: «Классификация», «Автомобили», «Гонки», «Результаты»
    3. третьей БД: «Отели», «Комнаты», «Покупатели», «Бронирования»
    4. четвертой БД: «Отделения», «Роли», «Сотрудники», «Проекты», «Задачи»

---

### Инструкция установки проекта:
1. Необходимо установить следующее программное обеспечение (ПО):
    1. [Java 8 update 441 (64-bit)](https://www.java.com/download/)
    2. [Java Development Kit (JDK) 23 (64-bit)](https://www.oracle.com/java/technologies/downloads/)
    3. [PostgreSQL](https://www.postgresql.org/)
2. В проекте содержится зависимость [PostgreSQL JDBC Driver](https://mvnrepository.com/artifact/org.postgresql/postgresql), необходимая для запуска
3. Стоит проверить название всех баз данных: должно быть «test1», «test2», «test3» и «test4» для `Vehicles.sql`, `Races.sql`, `Bookings.sql` и `Departments.sql` соответственно
4. Нужно инпортировать файлы SQL-запросов в БД
5. Клонируйте [текущий репозиторий](https://github.com/Tyoma-Pi/DatabasesWorks/) командой `git clone`

### Инструкция запуска и тестирования проекта
1. Откройте файл `Main.java` в `Visula Studio Code`
2. запустите этот файл клавишей `F5`
3. Следуйте описанию, которое выводится в программе
