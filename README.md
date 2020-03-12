# BurnSecurity
BurnSecurity est un système de sécurité des médias permettant aux sites internet marchands ou aux particuliers de vendre les fichiers sécurisé aux internautes afin de permettre aux artistes de lutter contre les pirates de leurs produits.

Le système à deux types de sécurisation des fichiers multimédias (Audio, Vidéo et Autres) local et sur internet. Pour ceux qui utilisent BurnSecurity en local comme système de sécurisation, ils peuvent sécuriser et vendre leurs supports amovibles (CD/DVD, USB, Carte SD) aisément sans l’aide d’un site internet marchand utilisant ce système de sécurité des médias.




# Installation sous Ubuntu18 (VPS)

Deziper le fichier BurnSecurityWebLinuxCGI.zip puis lancer votre terminal et tapez les commandes :

cd BurnSecurityLinux

cp -r ./AppsFinal/* /usr/lib/cgi-bin

cp -r ./AppsFinal/* /usr/lib/cgi-bin

sudo mkdir -p /var/www/html/votresite

cp -r ./Docs/* /var/www/html/ votresite

chown www-data:www-data -R /var/www/html/*






# Installation sous CentOS 7.1 (VPS)

Deziper le fichier BurnSecurityWebLinuxCGI.zip puis lancer votre terminal et tapez les commandes :

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


![alt tag](https://github.com/AnetoEnterprise/BurnSecurity/raw/master/image3.png)
