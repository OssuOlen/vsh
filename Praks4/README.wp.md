Kasutasin juhendit https://www.digitalocean.com/community/tutorials/how-to-create-a-ssl-certificate-on-apache-for-debian-8

kuna mul oli juba apache2 olemas siis tegin esimesena sudo a2enmod ssl
sudo a2ensite default-ssl ja service apache2 restart

Peale seda tegin kausta mkdir /etc/apache2/ssl
Kui kaust oli tegtud siis kirjutasin sellise asja: openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt
Tuli ette mingi küsimustik ja panin samad vastused nagu juhendis olid
Country Name (2 letter code) [AU]:US
State or Province Name (full name) [Some-State]:New York
Locality Name (eg, city) []:NYC
Organization Name (eg, company) [Internet Widgits Pty Ltd]:DigitalOcean
Organizational Unit Name (eg, section) []:SSL Certificate Test
Common Name (e.g. server FQDN or YOUR name) []:example.com               
Email Address []:test@example.com

Peale seda tegin chmod 600 /etc/apache2/ssl/*

Kuna mul ei olnud sellist faili nagu default-ssl.conf siis ma tegin selle /etc/apache2/sites-enabled/default-ssl.conf
ja lisasin sinna sisse netist tõmmatud faili sisu
Muutsin ära paar asja
<IfModule mod_ssl.c>
    <VirtualHost _default_:443>
        ServerAdmin webmaster@localhost
        ServerName 172.23.13.50:443
        DocumentRoot /var/www/html

        . . .
        SSLEngine on

        . . .

        SSLCertificateFile /etc/apache2/ssl/apache.crt
        SSLCertificateKeyFile /etc/apache2/ssl/apache.key
Tegin apachele restarti service apache2 restart

Kirjutasin openssl s_client -connect 172.23.13.50:443 et testida kas asi töötab
ja see töötas...
