# zabbix
**Задание 1.**  
![изображение](https://github.com/Copakaban/zabbix/assets/118304300/b990d28c-4329-48a1-a6a3-d163b6f44df5)
Устанавливаем БД:  
`apt install postgresql -y`  
Устанавливаем zabbix-server и web-server:  
`wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4+debian11_all.deb`  
`dpkg -i zabbix-release_6.0-4+debian11_all.deb`  
`apt update`  
`apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts`  
`sudo -u postgres createuser --pwprompt zabbix`  
`sudo -u postgres createdb -O zabbix zabbix`  
`zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix`  
Редактируем в файле (прописываем свой пароль) /etc/zabbix/zabbix_server.conf строку DBPassword=  
Перезапускаем zabbix, apache2:  
`systemctl restart zabbix-server apache2`  
`systemctl enable zabbix-server apache2`  

**Задание 2.**  
![изображение](https://github.com/Copakaban/zabbix/assets/118304300/302f1806-061e-4b0d-9bef-98247abae4e9)  
![изображение](https://github.com/Copakaban/zabbix/assets/118304300/3e889025-761c-4367-9938-22b001e66267)  
![изображение](https://github.com/Copakaban/zabbix/assets/118304300/01703654-52fd-4bca-a221-eb0fbdb178b1)  

**Задание 3*.**  
Первоначально работу делал на рабочем компьютере, на виртуалку поставил zabbix сервер, на хостовую виндовую машину поставил агент, получилось их подружить, данные пошли, сделал скрин и успокоился. Позже, когда полностью прочитал задание, понял, что не тот скрин сделал. Но т.к. работаю вахтами, на работе окажусь теперь только через месяц.
