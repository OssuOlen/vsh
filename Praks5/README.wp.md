Kasutasin installimiseks seda juhendit https://www.vpsserver.com/community/tutorials/30/installing-wordpress-on-debian-8-server/
läksin kausta cd /var/www/html/
tõmbasin sinna wget http://wordpress.org/latest.zip
tõmbasin asja et seda unzippida saaksin sudo aptitude install unzip
unzippisin file unzip -q latest.zip
muutsin õiguseid chown -R www-data:www-data /var/www/html/wordpress
chmod -R 755 /var/www/html/wordpress
tegin mingi uue kasuta kuhu kõik läheb 
mkdir -p /var/www/html/wordpress/wp-content/uploads
muutsin õigused sellel kaustal
chown -R www-data:www-data /var/www/html/wordpress/wp-content/uploads
tegin database mysql -u root -p
CREATE DATABASE wordpress_sample;
CREATE USER wp_user@localhost IDENTIFIED BY 'wp_password';
GRANT ALL PRIVILEGES ON wordpress_sample.* TO wp_user@localhost;
FLUSH PRIVILEGES;
exit
võtsin lahti oma wordpressi lehe https://172.23.13.50/wordpress/
tegin ära installi
panin nimeks admin ja parooliks qwerty
ja kõik töötas
