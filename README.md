# BurnSecurity
BurnSecurity est un système de sécurité des médias permettant aux sites internet marchands ou aux particuliers de vendre les fichiers sécurisé aux internautes afin de permettre aux artistes de lutter contre les pirates de leurs produits.

Le système à deux types de sécurisation des fichiers multimédias (Audio, Vidéo et Autres) local et sur internet. Pour ceux qui utilisent BurnSecurity en local comme système de sécurisation, ils peuvent sécuriser et vendre leurs supports amovibles (CD/DVD, USB, Carte SD) aisément sans l’aide d’un site internet marchand utilisant ce système de sécurité des médias.




# Installation sous Ubuntu18 (VPS)

Deziper le fichier BurnSecurityLinux.zip puis lancer votre terminal et tapez les commandes :

cd BurnSecurityLinux

cp -r ./AppsFinal/* /usr/lib/cgi-bin

cp -r ./AppsFinal/* /usr/lib/cgi-bin

sudo mkdir -p /var/www/html/votresite

cp -r ./Docs/* /var/www/html/ votresite

chown www-data:www-data -R /var/www/html/*






# Installation sous CentOS 7.1 (VPS)

Deziper le fichier BurnSecurityLinux.zip puis lancer votre terminal et tapez les commandes :

cd BurnSecurityLinux

cp -r ./AppsFinal/* /var/www/cgi-bin

sudo chmod 755 /var/www/cgi-bin/burnsecurity.cgi

sudo chmod 755 /var/www/cgi-bin/config.cf

sudo mkdir -p /var/www/html/ votresite

cp -r ./Docs/* /var/www/html/ votresite

chown apache:apache -R /var/www/html/*


![alt tag](https://github.com/AnetoEnterprise/BurnSecurity/raw/master/image1.png)

Apres cette procédure, vous verrez les fichiers et dossier ci-après :
![alt tag](https://github.com/AnetoEnterprise/BurnSecurity/raw/master/image4.png)

Vous pouvez modifier le nom du dossier DestDir mais à condition d’éditer le fichier de configuration config.cf depuis le répertoire /var/www/cgi-bin/ en tapant la commande :

Sudo nano /var/www/cgi-bin/config.cf

![alt tag](https://github.com/AnetoEnterprise/BurnSecurity/raw/master/image2.png)
Le répertoire DIR est seul qui permettra à BurnSecurity d’importer et de sécurisé les fichiers media, les deux lignes restantes convertissent le .MP3 a .K7 et .MP4 a .V7 les deux formats qui serons en lectures sécurisée avec le plugin K7Player.

NB : Vous pouvez le changer a .WAV :: .K7 et .OGG :: .V7 ou .WEBM :: .V7

Les trois fichiers PHP restant, vous pouvez les modifier à votre guise :
![alt tag](https://github.com/AnetoEnterprise/BurnSecurity/raw/master/image5.png)

Index.php :

<form enctype = "multipart/form-data" action = "/cgi-bin/burnsecurity.cgi" method = "post">
<p>TYPE :<select name = "typefichier">
<option value=".MP3">.MP3</option>
<option value=".MP4">.MP4</option>
</select></p>
<table><tr><td>PRIX :<br/><input type = "text" name = "prix" placeholder="00.1" /></td><td>TYPE MONNAIE :<br/><select name = "typemonnaie">
<option value="USD">USD</option>
<option value="EUR">EUR</option>
</select>
</td></tr></table>
FICHIER :
<p><input type = "file" name = "fichier" /></p>
POSTER :
<p><input type = "file" name = "poster" /></p>
TITRE :
<p><input type = "text" name = "titre" /></p>
ARTISTE :
<p><input type = "text" name = "artiste" /></p>
ALBUM :
<p><input type = "text" name = "album" /></p>
<input type = "hidden" name = "iduser" value="deasd2EU7359K" />
<input type = "hidden" name = "pageerror" value="http://127.0.0.1/burnsecurity/pageerror.php" />
<input type = "hidden" name = "pagesucess" value="http://127.0.0.1/burnsecurity/pagesucess.php" />
<input type = "hidden" name = "distributeur" value="AnetoEnterprise Inc." />
<input type = "hidden" name = "paypalidpaiment" value="deasd2EU7359Kdeasd2EU7359Kdeasd2EU7359Kdeasd2EU7359K" />
<p><input type = "submit" value = "IMPORTER" /></p>
</form>

Pageerror.php :

<?php
$logGet=$_POST["logGet"];

echo $logGet;
?>


Pagesucess.php :

<?php
$logGet=$_POST["logGet"];
$titre=$_POST["titre"];
$artiste=$_POST["artiste"];
$album=$_POST["album"];
$iduser=$_POST["iduser"];
$fichier=$_POST["fichier"];
$fichier_court=$_POST["fichier_court"];
$poster=$_POST["poster"];
$prix=$_POST["prix"];
$typemonnaie=$_POST["typemonnaie"];
$distributeur=$_POST["distributeur"];

echo'
<a href="/burnsecurity/DestDir/'.$fichier.'">
<table><tr><td>
<img src="/burnsecurity/DestDir/'.$poster.'" style="width:200px;height:200px;border:0px solid;border-radius:100px;"/>
</td><td>
Titre : '.$titre.'
<br/>
Artiste : '.$artiste.'
<br/>
Album : '.$album.'
<br/>
Distributeur : '.$distributeur.'
<br/>
Prix : '.$prix.''.$typemonnaie.'
</td></tr></table>
</a>
<audio src="/burnsecurity/DestDir/'.$fichier_court.'" controls></audio>
';
?>

![alt tag](https://github.com/AnetoEnterprise/BurnSecurity/raw/master/image3.png)
