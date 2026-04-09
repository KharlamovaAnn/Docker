# Лабораторная работа 1. 1. Установка и настройка Docker. Работа с контейнерами в Docker

## Цель работы
Освоить процесс установки и настройки Docker, научиться работать с основными командами CLI, контейнерами и образами. Понять принципы контейнеризации для развертывания аналитических сред и сервисов.

## Ход работы

Проверка версии Docker

<img width="729" height="448" alt="Снимок экрана 2026-04-09 220103" src="https://github.com/user-attachments/assets/722873b7-a5dd-47e7-9c2d-0d6d87d3139b" /> <br1/>

Просмотр скачанных образов

<img width="657" height="153" alt="Снимок экрана 2026-04-09 220128" src="https://github.com/user-attachments/assets/f48d3026-7104-426c-81a0-9fa88707b716" /> <br2/>

Просмотр запущенных контейнеров

<img width="653" height="44" alt="Снимок экрана 2026-04-09 220136" src="https://github.com/user-attachments/assets/94da9970-26b2-41c6-83df-e2d0f361ab86" /> <br3/>

Просмотр запущенных контейнеров, включая остановленные

<img width="1031" height="306" alt="Снимок экрана 2026-04-09 220145" src="https://github.com/user-attachments/assets/553c9cbf-7ea9-401c-ac4f-9e4b891e0d9c" /> <br4/>

## Индивидуальное задание
### Вариант 18
#### **БД временных рядов.** Используется для IoT и метрик. Запустить контейнер, зайти в веб-интерфейс (порт 8086) и создать первичного пользователя/организацию.

Запуск контейнера influxdb	
**Создаём исполняемый файл с помощью nano influx.sh.**

<img width="1601" height="915" alt="1" src="https://github.com/user-attachments/assets/73c6780b-31a0-4350-ae40-3e586b9733c7" /> <br5/>

Проверка influxdb	на порту 8086 

<img width="1919" height="1006" alt="2" src="https://github.com/user-attachments/assets/6f15a1fa-f7ed-433d-90df-ad514be10f3a" /> <br6/>

Создание первичного пользователя

<img width="1851" height="985" alt="3" src="https://github.com/user-attachments/assets/cc1d2b03-bff9-4541-aeea-041703c000cd" /> <br7/>


<img width="1856" height="980" alt="4" src="https://github.com/user-attachments/assets/68186221-24a8-436a-868a-6d0ad5b83bc6" /> <br8/>

Остановка контейнера, проверка

<img width="1184" height="436" alt="Снимок экрана 2026-04-07 053947" src="https://github.com/user-attachments/assets/472013f1-bf9f-402b-a0de-ad8c6fe16c9c" />


## Вывод
В ходе выполнения лабораторной работы был изучен функционал Docker, а конкретно: запуск и остановка контейнеров, просмотр образов и запущенных контейнеров.
