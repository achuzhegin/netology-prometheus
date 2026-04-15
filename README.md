# Домашнее задание к занятию "Docker. Часть 2" - `Чужегин Андрей Александрович`
### Задание 1
**Напишите ответ в свободной форме, не больше одного абзаца текста.**

Установите Docker Compose и опишите, для чего он нужен и как может улучшить лично вашу жизнь.


---
### Решение 1
Позволяет управлять многоконтейнерными приложениями с помощью файла конфигурации YAML.
Docker Compose упрощает запуск и оркестрацию контейнеров в различных средах.
используется для одновременного управления несколькими контейнерами, входящими в состав приложения.

Главное - можно не разбираться что под копотом, и запускать его


### Задание 2

**Выполните действия и приложите текст конфига на этом этапе.** 

Создайте файл docker-compose.yml и внесите туда первичные настройки: 

 * version;
 * services;
 * volumes;
 * networks.

При выполнении задания используйте подсеть 10.5.0.0/16.
Ваша подсеть должна называться: <ваши фамилия и инициалы>-my-netology-hw.
Все приложения из последующих заданий должны находиться в этой конфигурации.

### Решение 2
[docker-compose.yml](prometheus/docker-compose.yml)



---

### Задание 3

**Выполните действия:** 
1. Создайте конфигурацию docker-compose для Prometheus с именем контейнера <ваши фамилия и инициалы>-netology-prometheus. 
2. Добавьте необходимые тома с данными и конфигурацией (конфигурация лежит в репозитории в директории [6-04/prometheus](https://github.com/netology-code/sdvps-homeworks/tree/main/lecture_demos/6-04/prometheus) ).
3. Обеспечьте внешний доступ к порту 9090 c докер-сервера.

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

### Решение 3
[docker-compose.yml](prometheus/docker-compose.yml)

![1](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img1.png)

![2](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img2.png)

### Задание 4 

**Выполните действия:**

1. Создайте конфигурацию docker-compose для Pushgateway с именем контейнера <ваши фамилия и инициалы>-netology-pushgateway. 
2. Обеспечьте внешний доступ к порту 9091 c докер-сервера.

### Решение 4
![Название скриншота](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img3.png)
![Название скриншота](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img4.png)
### Задание 5 

**Выполните действия:** 

1. Создайте конфигурацию docker-compose для Grafana с именем контейнера <ваши фамилия и инициалы>-netology-grafana. 
2. Добавьте необходимые тома с данными и конфигурацией (конфигурация лежит в репозитории в директории [6-04/grafana](https://github.com/netology-code/sdvps-homeworks/blob/main/lecture_demos/6-04/grafana/custom.ini).
3. Добавьте переменную окружения с путем до файла с кастомными настройками (должен быть в томе), в самом файле пропишите логин=<ваши фамилия и инициалы> пароль=netology.
4. Обеспечьте внешний доступ к порту 3000 c порта 80 докер-сервера.
   
### Решение 5
![Название скриншота](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img5.png)
![Название скриншота](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img6.png)
![Название скриншота](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img7.png)

### Задание 6 

**Выполните действия.**

1. Настройте поочередность запуска контейнеров.
2. Настройте режимы перезапуска для контейнеров.
3. Настройте использование контейнерами одной сети.
5. Запустите сценарий в detached режиме.
   
### Решение 6
[docker-compose.yml](prometheus/docker-compose.yml)

### Задание 7 

**Выполните действия.**
1. Выполните запрос в Pushgateway для помещения метрики <ваши фамилия и инициалы> со значением 5 в Prometheus: ```echo "<ваши фамилия и инициалы> 5" | curl --data-binary @- http://localhost:9091/metrics/job/netology```.
2. Залогиньтесь в Grafana с помощью логина и пароля из предыдущего задания.
3. Cоздайте Data Source Prometheus (Home -> Connections -> Data sources -> Add data source -> Prometheus -> указать "Prometheus server URL = http://prometheus:9090" -> Save & Test).
4. Создайте график на основе добавленной в пункте 5 метрики (Build a dashboard -> Add visualization -> Prometheus -> Select metric -> Metric explorer -> <ваши фамилия и инициалы -> Apply.

В качестве решения приложите:

* docker-compose.yml **целиком**;
* скриншот команды docker ps после запуске docker-compose.yml;
* скриншот графика, постоенного на основе вашей метрики.
### Решение 7
[docker-compose.yml](prometheus/docker-compose.yml)
Grafana не смог запустить с порта 80, получилось запустить только с порта 3000
![Название скриншота](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img8.png)
![Название скриншота](https://github.com/achuzhegin/netology-prometheus/blob/main/img/img9.png)

