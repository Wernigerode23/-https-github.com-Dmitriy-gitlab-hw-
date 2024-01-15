# Домашнее задание к занятию "`Disaster Recovery. FHRP и Keepalived`" - `Вернигоров Дмитрий'

### Задание 1
Дана схема для Cisco Packet Tracer, рассматриваемая в лекции.
На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.

На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.
Ответ:
[PKT FILE](https://disk.yandex.ru/d/SFXYB-iiphNeRA)
![image](https://github.com/Wernigerode23/-https-github.com-Dmitriy-gitlab-hw-/assets/153208339/b27a4758-7c3b-4d6c-b4ab-b785c8fb7d2c)
![image](https://github.com/Wernigerode23/-https-github.com-Dmitriy-gitlab-hw-/assets/153208339/de98ed75-4ee2-4e2f-84bd-54679eeb9ca5)


### Задание 2

Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного файла.
Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html

 На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived. 
 
1. ![image](https://github.com/Wernigerode23/-https-github.com-Dmitriy-gitlab-hw-/assets/153208339/c0e32705-a8a0-4e83-80b0-382c51ed0e69)

2.конфигурационный файл keepalived
 https://disk.yandex.ru/d/BMyHxbe50p03Sg
3. скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html
- сервер включен
![image](https://github.com/Wernigerode23/-https-github.com-Dmitriy-gitlab-hw-/assets/153208339/d6b6c9a3-8c93-42eb-94e7-ba68c93571b7)
- сервер отключен
  ![image](https://github.com/Wernigerode23/-https-github.com-Dmitriy-gitlab-hw-/assets/153208339/528a6265-3b3b-4866-906a-c64dd3ab5b34)
- второй сервер
  ![image](https://github.com/Wernigerode23/-https-github.com-Dmitriy-gitlab-hw-/assets/153208339/4136cdac-a278-4db8-b19b-f83f0d4b9042)


