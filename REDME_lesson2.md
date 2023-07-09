# Контейнеризация (семинары)


![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/super_conteiner.jpeg)
## Урок 2. LXC-подсистемная контейнеризация (linux Containers)

### **Информация о проекте**
1) запустить контейнер с ubuntu, используя механизм LXC
2) ограничить контейнер 256 Мб ОЗУ и проверить, что ограничение работает

**Задание**

* 
Команда sudo apt install lxc debootstrap bridge-utils lxc-templates используется для установки нескольких пакетов,
связанных с контейнерами Linux (LXC) и их зависимостями.

1 lxc: этот пакет предоставляет основные функции LXC, позволяя создавать контейнеры Linux и управлять ими.
2 debootstrap: этот пакет представляет собой инструмент, используемый для установки дистрибутива Linux на основе Debian
  внутри контейнера. Это помогает в создании начальной структуры файловой системы и установке необходимых пакетов.
3 bridge-utils: этот пакет содержит утилиты для настройки и управления сетевыми мостами в Linux.
  Он обычно используется вместе с LXC для настройки сети для контейнеров.
4 lxc-templates: этот пакет включает набор шаблонов для создания различных типов контейнеров LXC. Эти шаблоны предоставляют
  предварительно настроенные настройки для различных дистрибутивов Linux, что упрощает создание контейнеров на основе конкретных дистрибутивов. 
```
 sudo apt install lxc debootstrap bridge-utils lxc-templates
```
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/install_lxc.png)
Установили пакеты LXC 

*
Создаем LXC контейнер с образом(имиджом) ubuntu
```
 sudo lxc-create -n testLXC -t ubuntu
```
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/create_lxc_conteiner.png)
пакеты устанавливались 30 минут!!!

* Далee делаем ограничения по памяти в 256М командой:
```
sudo lxc-cgroup -n testLXC memory.max 256m 
```
* Запускаем контейнер командой:
```
sudo lxc-start -n  testLXC 
```
* Заходим в контейнер командой:
```
sudo lxc-attach -n  testLXC 
```
* Смотрим сколько доступно памяти, команда:
```
free -m  
```
** Видим что оперативная память ограничена 256М
![picture for containerization](https://github.com/DRain777/Containerization/blob/algoritm/source/proof.png)

Студент Geek Brains Кочев Денис











