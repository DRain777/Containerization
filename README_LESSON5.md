# Контейнеризация (семинар)
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/super_conteiner.jpeg)

## Урок 5 DOCKER COMPOSE,DOCKER SWARM

# Задание 
Задание 1:
* 1 создать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД
* 2 далее необходимо создать 3 сервиса в каждом окружении (dev, prod, lab)
* 3 по итогу на каждой ноде должно быть по 2 работающих контейнера
* 4 выводы зафиксировать

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


