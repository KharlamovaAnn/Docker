# Лабораторная работа 1. 1. Установка и настройка Docker. Работа с контейнерами в Docker

## Цель работы
Освоить процесс установки и настройки Docker, научиться работать с основными командами CLI, контейнерами и образами. Понять принципы контейнеризации для развертывания аналитических сред и сервисов.

## Ход работы

Проверка версии Docker

<img width="747" height="528" alt="image" src="https://github.com/user-attachments/assets/3b3ae362-4853-4ff6-b15c-2ea6c9862de9" /> <br1/>

Просмотр скачанных образов

<img width="569" height="57" alt="Снимок экрана 2026-04-07 054233" src="https://github.com/user-attachments/assets/ea5de1ad-e4e5-4d0f-9f4d-925c707be76d" />

Просмотр запущенных контейнеров

<img width="830" height="125" alt="image" src="https://github.com/user-attachments/assets/7f1b897c-b369-4f60-94c7-4bbcd290601a" /> <br3/>

Просмотр запущенных контейнеров, включая остановленные

<img width="1053" height="523" alt="image" src="https://github.com/user-attachments/assets/0763bd6b-4592-4f1a-920b-ad6e0b4ac5d7" /> <br4/>

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
