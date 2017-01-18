---
author: "Patrice Blondel"
date: 2015-06-18
linktitle: Capture d'une image dans une vidéo
title: Capture d'une image dans une vidéo
description: Choisr une image "poster"
weight: 10
tags: 
- vidéo
- images
- html5
topics:
- webmaster
---

Il peut être utile de choisir une image dans une vidéo afin de choisir l'image d'accueil.    
Les explications qui suivent nécessite un système Linux.    

<!--more-->


### Installons les outils
	# apt-get install libav-tools    

Pour une image 320X240 capturée au bout de 10 secondes de lecture de la vidéo.
    
	$ avconv -i video.flv -f mjpeg -ss 10 -vframes 1 -s 320x240 vignette.jpg    

#### Explications
Dans cette commande, je choisis :    

- la vidéo où je veux capturer l'image ici : **video.flv**
- le codec : ce sera du *jpg*
- la taille de l'image (pour connaître les dimensions de la vidéo : **$ avconv -i video.flv**)
- le nom du fichier de sortie : *vignette.jpg*
- le moment de la capture : dans mon cas *10 secondes*
