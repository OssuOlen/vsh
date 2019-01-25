DOKUWIKI
Tegin enamus asju selle õpetuse järgi https://www.howtoforge.com/tutorial/debian-dokuwiki-apache-installation/
kõigepealt sisestasin käsu apt-get update
kirjutasin wget https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz
Sain faili dokuwiki-stable.tgz
tar xzvf dokuwiki-stable.tgz
kopeerisin need failid html kausta 
cp -rf dokuwiki-2017-04-22b/* /var/www/html/
cp dokuwiki-2017-0b-22b/.htaccess.dist /var/www/html/
Muutsin ära õigused 
chown -R www-data:www-data /var/www/html/
Vaatasin kuidas kõik õigused tulid
ls –al /var/www/html/
avasin browserist https://172.23.13.50/dokuwiki/ ja tegin ära kasutaja ja installi asja
sisestasin järgmised käsud
rm -rf /var/www/html/install.php
chown -R root:root /var/www/html/
chown -R www-data:root /var/www/html/data/
chown -R www-data:root /var/www/html/lib/plugins/
chown -R www-data:root /var/www/html/lib/tpl/
chown -R www-data:root /var/www/html/conf/local.php*
chown -R www-data:root /var/www/html/conf/users.auth.php
chown -R www-data:root /var/www/html/conf/acl.auth.php
chown -R www-data:root /var/www/html/conf/plugins.local.php*
Nendega ma muutsin hunniku õiguseid, et asjad töötaksid
läksin uuesti https://172.23.13.50/dokuwiki/
Ja mulle tuli ette sisselogimise leht
logisin sisse ja kijutasin sinna midagi ja peale seda salvestasin....
