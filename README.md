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
