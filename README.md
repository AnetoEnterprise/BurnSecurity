# BurnSecurity
BurnSecurity est un système de sécurité des médias permettant aux sites internet marchands ou aux particuliers de vendre les fichiers sécurisé aux internautes afin de permettre aux artistes de lutter contre les pirates de leurs produits.

Le système à deux types de sécurisation des fichiers multimédias (Audio, Vidéo et Autres) local et sur internet. Pour ceux qui utilisent BurnSecurity en local comme système de sécurisation, ils peuvent sécuriser et vendre leurs supports amovibles (CD/DVD, USB, Carte SD) aisément sans l’aide d’un site internet marchand utilisant ce système de sécurité des médias.


Installation sous Ubuntu18 (VPS)

Deziper le fichier BurnSecurityLinux.zip puis lancer votre terminal et tapez les commandes :

cd BurnSecurityLinux

cp -r ./AppsFinal/* /usr/lib/cgi-bin

cp -r ./AppsFinal/* /usr/lib/cgi-bin

sudo mkdir -p /var/www/html/votresite

cp -r ./Docs/* /var/www/html/ votresite

chown www-data:www-data -R /var/www/html/*



Installation sous CentOS 7.1 (VPS)

Deziper le fichier BurnSecurityLinux.zip puis lancer votre terminal et tapez les commandes :

cd BurnSecurityLinux

cp -r ./AppsFinal/* /var/www/cgi-bin

sudo chmod 755 /var/www/cgi-bin/burnsecurity.cgi

sudo chmod 755 /var/www/cgi-bin/config.cf

sudo mkdir -p /var/www/html/ votresite

cp -r ./Docs/* /var/www/html/ votresite

chown apache:apache -R /var/www/html/*
