---
author: "Patrice Blondel"
date: 2013-01-12
linktitle: Limiter l'accès à un répertoire Web
title: Limiter l'accès à un répertoire Web
description: Protéger des données
weight: 10
tags: 
- htaccess
- sécurité

topics:
- réseau
---

Le serveur apache propose un outil qui permet de limiter l'accès (par un mot de passe) à un répertoire Web.    
Cet outil, c'est **htaccess**.   

<!--more-->

Les fichiers *.htaccess* sont des fichiers de configuration du serveur Apache. 
Ils se présentent sous la forme suivante :    
un simple fichier nommé *.htaccess* (pas d’extension, juste le nom « htaccess » avec un point au début pour le cacher.    

Si ce .htaccess contient ceci :    

	Order allow,deny
	Deny from all

l’accès au dossier dans lequel il est sera purement et simplement interdit.

Il est également possible de restreindre l’accès à un login et mot de passe.     
Cela se fait avec un fichier *.passwds* (qui contient les identifiants et les mots de passe)

### Un exemple : protéger un répertoire par un mot de passe

Il s'agit d'une des applications les plus utiles du fichier .htaccess car elle 
permet de définir de façon sûre (à l'aide d'un login et d'un mot de passe) 
les droits d'accès à des fichiers par certains utilisateurs.  
  
#### Syntaxe :

	AuthUserFile (emplacement du fichier de mot de passe)
	AuthName "Accès protégé" 
	AuthType Basic 
	Require valid-user 

La commande **AuthUserFile** permet de définir l'emplacement du fichier 
contenant les logins et les mots de passe des utilisateurs autorisés à l'accès.     
Ce fichier ne se place pas obligatoirement dans le répertoire à protéger.    
Comme vous pouvez le constater, l’appel au fichier .passwds doit se faire avec un chemin absolu 
(chemin depuis la racine du serveur appelé chemin canonique absolu).    
Ce chemin absolu se détermine avec la fonction PHP realpath(), qui utilisée dans un dossier, 
vous indiquera le chemin absolu vers ce dernier.    
Si vous la mettez dans un fichier PHP nommé *chemin.php* :

	<!--?php
	echo realpath('chemin.php'); 
	?-->


Son ouverture dans une page web vous indiquera ce chemin canonique absolu.    

#### Crypter les mots de passe

Apache fournit un outil permettant de générer facilement des mots de passe cryptés, 
il s'agit de l'utilitaire **htpasswd**.

#### Créer un nouveau fichier de mots de passe

	$ htpasswd -c (chemin du fichier de mot de passe) utilisateur

Le mot de passe sera demandé en ligne de commande avec une confirmation.

#### Fonctionnement

Il suffit maintenant de mettre en ligne ces fichiers dans le répertoire à protéger.    

**NB** : Dans le cas d'un serveur Apache en local, vous devez vérifier : 
que dans **/etc/apache2/sites-available/default**, la ligne *AllowOverride AuthConfig* est bien présente.    

	<Directory /var/www/>
  	Options Indexes FollowSymLinks MultiViews
  	AllowOverride AuthConfig
  	Order allow,deny
  	allow from all
  	...
	</Directory>


Il faut également s'assurer que dans le fichier **httpd.conf** que la ligne *AllowOverride All* est bien là 
afin de permettre les restrictions d'accès.

#### Un exemple

[Un espace à accès limité](http://pingouindoc.tuxfamily.org/securise/ ) : le login est « govez » et le mot de passe « hanvoile ».