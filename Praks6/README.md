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
Kasutasin installimiseks seda juhendit https://www.vpsserver.com/community/tutorials/30/installing-wordpress-on-debian-8-server/
läksin kausta cd /var/www/html/
tegin apt install php7.0-*
service apache2 restart
tõmbasin sinna wget http://wordpress.org/latest.zip
tõmbasin asja et seda unzippida saaksin sudo aptitude install unzip
unzippisin file unzip -q latest.zip
muutsin õiguseid chown -R www-data:www-data /var/www/html/wordpress
chmod -R 755 /var/www/html/wordpress
tegin mingi uue kasuta kuhu kõik läheb 
mkdir -p /var/www/html/wordpress/wp-content/uploads
cd /var/www/html/wordpress/
cp wp-config-sample.php wp-config.php
nano wp-config.php
selles failis muutsin äta useri,parooli,andmebaasi nime ja hostname, hostname kohale pain localhost
KOLMAS KLIENDI MASIN--------
Kliendi arvutile panin ubuntu 16.4 graafilise versiooni ja määrasin sellele 4GB RAM ja 20GB ketta mahtu
