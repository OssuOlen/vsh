Tegin kloonid 2 arvutist
ESIMENE DB SERVER-------
Tõmbasin ühte mariadb serveri
apt install mariadb-server
Siis tegin seal samas sellise käsu 
mysql_secure_installation
Tegin restarti teenusele 
Service mysql restart
mysql -u root -p
CREATE DATABASE wordpress;
CREATE USER 'WPuser'@'localhost' IDENTIFIED BY 'qwerty';
GRANT ALL PRIVILEGES ON wordpress.* TO 'WPuser'@'localhost';
CREATE USER 'WPuser'@'10.0.2.15' IDENTIFIED BY 'qwerty';
GRANT ALL PRIVILEGES ON wordpress.* TO 'WPuser'@'10.0.2.15';
exit
sisestasin need käsud mysqlis
TEINE WORDPRESS SERVER----------

