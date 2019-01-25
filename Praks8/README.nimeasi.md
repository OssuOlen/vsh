Tegin uue kausta nimega oscar.ee kausta /var/www/ 
tegin veel index-html faili
muutsin ära õigused kaustadel käskudega
chown -R www-data /var/www/oscar.ee
chgrp -R www-data /var/www/oscar.ee
Siis muutsin apache2 default confi nime /etc/apache2/sites-available/000-defauld.conf /etc/apache2/sites-avalable/apache.oscar.conf
Muutsin ära confis mõned read...
DocumentRoot /var/www/oscar.ee
ServerName apache.oscar.ee
ServerAlias oscar.ee
DocumentRoot /var/www/html/www ##
        <Directory />
                Options FollowSymLinks
                AllowOverride None
        </Directory>
        <Directory /var/www/html/www> ##
                Options Indexes FollowSymLinks MultiViews
                AllowOverride None
                Order allow,deny
                allow from all
        </Directory>

Käivitasin lehe a2ensite apache.oscar.ee
tegin veel igaksjuhuks service apache2 restart 
ja lehekülg töötas...
