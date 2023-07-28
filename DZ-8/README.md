Урок 8. Основы HTTP/HTTPS и DNS

1. Доделать свой сертификат
2. Настроить сеть согласно информации на схеме
    (https://disk.yandex.ru/d/Vaxkf2X0RG9NGw .)
    Сымитировать "Интернет" с помощью OSPF. Приватных сетей в маршрутизации быть не должно.
    Для компьютеров из Office 1 предоставить доступ в "Интернет" с помощью PAT.
    Открыть доступ из "Интернета" к серверам из Office 2 c помощью Port Forwarding.
    Для компьютеров из Office 1 должны открываться разные сайты по HTTP и HTTPS из Office 2 по одному доменному имени.
    Предоставить скриншоты открытых разных сайтов по одному доменному имени.
    Предоставить скриншот таблицы NAT трансляций с Router3.
    Предоставить скриншот таблицы маршрутизации с Router0.

Решение задач:

1. Доменное имя я получил: vladimirvpn.ddns.net
    соответственное можно зайти на https://vladimirvpn.ddns.net:943/admin - и попасть на web-интерфейс OpenVPN
    
    Попытка получения сертификата к сожалению провалилась!
    Сначала была выдана такая ошибка:
        Certbot can obtain and install HTTPS/TLS/SSL certificates. By default, it will attempt to use a webserver both for obtaining and installing the certificate. certbot: error: unrecognized arguments: sudo certbot
    * скриншот забы сразу сделать, а позже (после нескольких безуспешных попыток) страница обновилась и все сообщения пропали
    Позже, при повторной попытке выпало уже другое сообщение об ошибке:
        An unexpected error occurred:
        There were too many requests of a given type :: Error creating new order :: too many failed authorizations recently: see https://letsencrypt.org/docs/failed-validation-limit/
        Ask for help or search for solutions at https://community.letsencrypt.org. See the logfile /var/log/letsencrypt/letsencrypt.log or re-run Certbot with -v for more detailsю
    Но буду продолжать пробовать еще !!! Если успею - то перезапишу все файлы
    ...Возможно нужно поменять сервер с виртуальной машиной...

2. Настройка сети - завершена!
    Все IP присвоены и настроены. OSPF и NAT настроены
    Серверы сделаны типа "http://yandex.ru" (ip 10.0.0.10) и "https://yandex.ru" (ip 10.0.0.11)
    DNS севрес настроен, работает!
    все скриншоты в формате JPG

    Скриншот таблицы NAT трансляций с Router1 (который подключен к Office2 к серверам "яндекс") показан - DZ_8-2-4
    но на Router0 (который подключен в сети Office1) транляции NAT не отображаются... хотя все настроено! см скриншот DZ_8-2-5