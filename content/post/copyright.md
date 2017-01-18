---
author: "Patrice Blondel"
date: 2009-12-15
linktitle: Copyright sur des images
title: Copyright sur des images
description: Protéger ses documents
weight: 10
tags: 
- images
- script
- copyright
topics:
- webmaster
---

Afin d'adapter la résolution de vos photos à votre affichage de site ou pour l'envoi par mail, 
voici un petit script qui vous permettra de modifier la taille d'une image et d'y insérer un copyright.    

<!--more-->


Au préalable, vous devez installer **imagemagick**   
 
	# aptitude install imagemagick

Pour l'utiliser, vous devez vous rendre dans le répertoire à modifier.    
donc en console :    

	$ cd le_répertoire_à_modifier

### Créer le script

	#!/bin/sh
	rm -rf photos_site
	mkdir -p photos_site
	taille="800x600"
	nom="Le pingouin des @lpes"
	police="/usr/share/fonts/truetype/dejavu/DejaVuSans.ttf"
	tpolice=6
	texte="Copyright @ $nom"
	topolice=$(( $tpolice * 3))
	bl=$(( $tpolice / 3))
	for i in *.jpg *.png *.gif *.JPG *.JPEG *.PNG *.GIF
	do
		convert -verbose -size $taille xc:none -gravity SouthEast \
		-pointsize $topolice -font @$police -stroke black -strokewidth $tpolice \
		-draw "text 5,5 '$texte'" -channel RGBA -blur 0x$bl -stroke none \
		-fill white -draw "text 5,5 '$texte'" $i -geometry $taille! \
		-compose dst-over -composite photos_site/$i
	done


Lancer le script (que vous avec copié dans un répertoire **scripts** en lui donnant les droits d'exécution) :    

	$ chmod +x copyright.sh).
	$ ~/scripts/copyright.sh

Dans ce script, vous pouvez modifier : 

- le nom du copyright *(nom)*
- le format de l'image *(jpg, png ...)*
- la taille de l'image *(800x600)*
- le nom du répertoire créé *(photo_site)*
- la police d'écriture utilisée et sa taille *(DejaVuSans 6)*.

Vous devez respecter les proportions pour qu'elle ne soit pas déformée (par exemple 1024x768 -> 800x600)    
Le lancement du script va créer un nouveau répertoire en y mettant les images modifiées.

### Une capture pour visualiser le résultat :

![img](/images/ville_copyright.jpg)