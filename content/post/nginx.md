---
date: "2016-11-14"
author: "Patrice Blondel"
weight: 10
description: Un autre serveur Web
title: Nginx
linktitle: Nginx
tags:
- serveur
topics:
- réseau
---


**Nginx** est un serveur web qui a vu le jour en 2002, en Russie.    
Il s’est vraiment développé à partir de 2006 lorsqu'il a été traduit du russe en anglais.    
Nginx représente 20 % des serveurs ; c’est bien moins que son principal concurrent Apache (60 %) 
mais ce n'est pas négligeable.   
  
<!--more-->    

Alors pourquoi installer Nginx plutôt qu’Apache ?    
La réponse est évidente : **les performances !**    
Nginx est un serveur dit « asynchrone » cela signifie qu’il peut exécuter plusieurs actions simultanément, 
ce n’est pas le cas d’Apache.    

- Nginx est plus rapide ;
- Il permet de supporter plus d’utilisateurs simultanément ;
- Il consomme moins de mémoire.    

J'ai donc décidé d'installer Nginx sur ma machine et de l'utiliser comme serveur web en local.    

### Installation de nginx et PHP 7.0 FPM

	# apt-get install nginx php7.0 php7.0-fpm php7.0-gd php7.0-mysql php7.0-cli php7.0-common php7.0-curl php7.0-opcache php7.0-json php7.0-imap
#### Vérifiez votre version de PHP
	$ php -v
Chez moi ça donne ça : 
```php
PHP 7.0.12-1 (cli) ( NTS )
Copyright (c) 1997-2016 The PHP Group
Zend Engine v3.0.0, Copyright (c) 1998-2016 Zend Technologies
    with Zend OPcache v7.0.12-1, Copyright (c) 1999-2016, by Zend Technologies
```
#### Vérifions pour nginx    
	# nginx -v
	nginx version: nginx/1.10.2



Rendez-vous sur la page *http://localhost* pour vérifier que votre serveur web fonctionne :     

<!-- nginx -->
<a href="#img2" class="trigger">
![img](/images/nginx.png)   
</a>

<!-- lightbox nging -->
<div class="lightbox" id="img2">
<img src="/images/nginx.png">
<a href="#" class="close">Fermer</a>
</div>

## Ça fonctionne ;-)


### Configuration de PHP 7.0 FPM
	# nano /etc/php/7.0/fpm/pool.d/www.conf
On vérifie la bonne configuration du type :    

	
	user = www-data
	group = www-data
	listen = /run/php/php7.0-fpm.sock
	listen.owner = www-data     

Il nous reste à renseigner le fichier */etc/nginx/nginx.conf*


	user www-data;
	worker_processes auto;
	pid /run/nginx.pid;
	include /etc/nginx/modules-enabled/*.conf;
	 
	events {
	    worker_connections 768;
	    # multi_accept on;
	}
	 
	http {
	 
	    ##
	    # Basic Settings
	    ##
 
	    sendfile on;
	    tcp_nopush on;
	    tcp_nodelay on;
	    keepalive_timeout 65;
	    types_hash_max_size 2048;
	    # server_tokens off;
	 
	    # server_names_hash_bucket_size 64;
	    # server_name_in_redirect off;
	 
	    include /etc/nginx/mime.types;
	    default_type application/octet-stream;
	 
	    ##
	    # SSL Settings
	    ##
	 
	    ssl_protocols TLSv1 TLSv1.1 TLSv1.2; # Dropping SSLv3, ref: POODLE
	    ssl_prefer_server_ciphers on;
	 
	    ##
	    # Logging Settings
	    ##
 	
	    access_log /var/log/nginx/access.log;
	    error_log /var/log/nginx/error.log;
	 
	    ##
	    # Gzip Settings
	    ##
	 
	    gzip on;
	    gzip_disable "msie6";
	 
	    # gzip_vary on;
	    # gzip_proxied any;
	    # gzip_comp_level 6;
	    # gzip_buffers 16 8k;
	    # gzip_http_version 1.1;
	    # gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;
	 
	    ##
	    # Virtual Host Configs
	    ##
	 
	    include /etc/nginx/conf.d/*.conf;
	    include /etc/nginx/sites-enabled/*;
	}


Ainsi que le fichier */etc/nginx/sites-available/default*    


	# Default server configuration
	#
	server {
	    listen 80 default_server;
	    listen [::]:80 default_server;
	    root /var/www/html;
	 
	    # Add index.php to the list if you are using PHP
	    index index.html index.htm index.nginx-debian.html index.php;
	 
	    server_name _;
	 
	    location / {
		# First attempt to serve request as file, then
		# as directory, then fall back to displaying a 404.
		try_files $uri $uri/ =404;
	    }
	    # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
	     
	    location ~ \.php$ {
		include snippets/fastcgi-php.conf;
		fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
	    }
	} 


**nota** : j'y ai ajouté la configuration pour la ré-écriture de Pluxml (mon CMS préféré) dans ce même fichier.  
  
	# re-ecriture url pour Pluxml
    	rewrite ^/(?<pluxml>pluxml[^/]*)/(?<pattern>(?:(?:article|static|categorie)\d*|tag|archives)(/.*)?)$ /$pluxml/index.php?$pattern;
    	rewrite ^/(?:<pluxml>pluxml[[^/]*)/feed/(?<feed>.*)$ /$pluxml/feed.php\?$feed;
 
    	location ~ ^/pluxml[^/]*/(?:data/medias/|themes/[^/]*/(?:css|img)/|core/lib/js.src/).* {
       	 try_files $uri $uri/ =404;
    	}
    	location ~ ^/pluxml[^/]*/core/lib/.*\.js {
        	try_files $uri $uri/ =404;
    	}
    	location ~ ^/pluxml[^/]*/(?:data/|themes/|core/lib/).* {
        	deny all;
    	}
    	location ~ ^/pluxml[^/]*/config.php {
       	 deny all;
    	}

Vérifions l'utilisation de PHP en créant un fichier phpinfo.php dans /var/www/html    
	# cd /var/www/html/
	# nano phpinfo.php
Ajoutez-y le code :    
	
	<?php phpinfo(); ?>
Vérifions en allant chercher la page *http://localhost/phpinfo.php avec votre navigateur*    
Chez moi ça donne ça :   

<!-- phpinfo -->
<a href="#img3" class="trigger">
![img](/images/phpinfo.png)   
</a>

<!-- lightbox phpinfo -->
<div class="lightbox" id="img3">
<img src="/images/phpinfo.png">
<a href="#" class="close">Fermer</a>
</div>
