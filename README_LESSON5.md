# Контейнеризация (семинар)
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/super_conteiner.jpeg)

## Урок 5 DOCKER COMPOSE,DOCKER SWARM

# Задание 
Задание 1:
* 1 Создать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД
* 2 Далее необходимо создать 3 сервиса в каждом окружении (dev, prod, lab)
* 3 По итогу на каждой ноде должно быть по 2 работающих контейнера
* 4 Выводы зафиксировать

* 1 Для создания сервиса,из двух разных контейнеров(веб-приложение и базы данных)
   Будем использовать Docker-compose- это инструмент для определения и управления
   многоконтейнерными приложениями.запишем данные в COMPOSE.YML через редактор nano  
```
nano compose.yml
```
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/1nano_compose.png)

* Запускаем docker-compose командой: 
```
 docker compose up -d
```
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/2docker_ps.png)



* 2 Чтобы создать три службы в каждой среде (dev, prod, lab) с помощью Docker Compose
* project/ Создаем структуру каталогов   
* ├── dev/
* │    └── docker-compose.yml
* ├── prod/
* │    └── docker-compose.yml
* └── lab/
*    └── docker-compose.yml

```
mkdir -p project/{dev,prod,lab}
```
```
touch project/dev/docker-compose.yml project/prod/docker-compose.yml project/lab/docker-compose.yml
```
* Заполняем  файлы docker-compose.yml в каждой директории
  
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/3_lesson5.png)

* Через команду cd заходим в папку project/ выбираем 1 из трех сервисов dev,prod,lab 
   через команду cd заходим в директорию, запускаем сервис этой командой:
   ```
   docker compose up 
   ``` 
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/4_lesson5.png)
 # В каждой папки dev,prod,lab по 2 работающих контейнера.

# Задание 2*:
* 1 нужно создать 2 ДК-файла, в которых будут описываться сервисы
* 2 повторить задание 1 для двух окружений: lab, dev
* 3 обязательно проверить и зафиксировать результаты, чтобы можно было выслать преподавателю 



Задание 2:

* 1 Создание 2 файла Docker Compose для описания сервисов:

* a Создайте файл `docker-compose.lab.yml` со следующим содержимым:


version: '3'
services:
web:
image:
container_name: web

db:
image:
container_name: db

* b Создайте файл `docker-compose.dev.yml` со следующим содержимым:

version: '3'
services:
web:
image:
container_name: web

db:
image:
container_name: db

* 2 Повторение задания 1 для двух окружений (lab, dev):

* Выполните команду `docker-compose -f docker-compose.lab.yml up -d` для запуска контейнеров в *окружении lab.

* Аналогично, выполните команду `docker-compose -f docker-compose.dev.yml up -d` для запуска *контейнеров в окружении dev.

* Таким образом, будут запущены по 2 контейнера (веб и БД) на каждой ноде для каждого окружения


