Tegu on vorguserverite haldus ainega
mu arvuti nr on 14
vm ip on: 172.23.13.50/60
kasutasin Debian 8.10 netinst mille võtsin https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-9.6.0-amd64-netinst.iso
kasutasin kaske:
apt update
apt upgrade
apt install git
apt install apache2
ja siis tegin kausta kuhu asju kirjutada
 muutsin ära /var/www/html/index.html faili
<!DOCTYPE html>
<html>
<head>
<title>Oscari Veebileht</title>
</head>
<body>

<style>
body {
background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRiLaSW8L_uscDoLyjgaOyktYvy_SCABApWHirm$
color:pink;
}
</style>
<center>
<h1>ISP217</h1>
<p>karl-oscar.neevits@khk.ee</p>
<a href="./public_html">
<p>Public fail kaust</p>
</a>
<iframe src="https://pa1.narvii.com/6166/15aa46dd14fc3d9cde90e426a5120716547388ae_hq.gif" width="500" height="500" f$
</center>
</body>
</html>
---------------
tegin mkdir /var/www/public_html
tegin seal kaustas file.txt
kirjutasin sinna sisse vajaliku

tegin resa apache2 asjale
service apache2 restart


