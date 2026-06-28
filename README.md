# Домашнее задание к занятию 4 «Оркестрация группой Docker контейнеров на примере Docker Compose»

## Задача 1
https://hub.docker.com/r/rrchip/custom-nginx

## Задача 2
1.
![alt text](image.png)

2.
![alt text](image-1.png)

3.
![alt text](image-2.png)

4.
![alt text](image-3.png)

Общее.

![alt text](image-4.png)

## Задача 3

1-3
![alt text](image-5.png)

docker attach подключается к основному процессу контейнера с PID 1.\
Ctrl+c посылает SIGKILL главному процессу приаттаченного контейнера

4-6
![alt text](image-6.png)

7-9\
![alt text](image-7.png)
![alt text](image-11.png)

10
![alt text](image-12.png)
Изменен внутренний порт веб-сервера Nginx с 80 на 81 напрямую в конфигурационных файлах «на лету». \
Однако подсистема Docker ничего об этом изменении не знает. При запуске контейнера Docker жестко зафиксировано правило перенаправления: трафик с порта 8080 хоста должен уходить на порт 80 внутри контейнера.\
Сейчас запросы с хоста (через порт 8080) продолжают стучаться на порт 80 контейнера, но там их больше никто не ждет, так как Nginx теперь слушает порт 81.

11
![alt text](image-9.png)

12
![alt text](image-10.png)

## Задача 4

![alt text](image-13.png)

## Задача 5

1
![alt text](image-15.png)

Запустился файл compose.yaml так как он предпочтительный. docker-compose.yamlи docker-compose.yml так же поддерживаются для обратной совместимости с более ранними версиями. Если оба файла существуют, Compose предпочитает файл compose.yaml.

2
![alt text](image-14.png)
![alt text](image-16.png)

3
![alt text](image-17.png)

4
![alt text](image-18.png)
![alt text](image-19.png)

5
![alt text](image-20.png)

6
![alt text](image-21.png)

7
![alt text](image-22.png)
Docker Compose обнаружил, что в данной рабочей директории (в рамках текущего проекта) ранее был запущен контейнер portainer. Однако в текущем конфигурационном файле (docker-compose.yaml, который теперь стал активным) описание этого сервиса отсутствует. Такие контейнеры Compose считает "осиротевшими".
![alt text](image-23.png)