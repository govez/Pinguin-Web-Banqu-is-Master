---
author: "Patrice Blondel"
date: 2017-01-10
linktitle: Déployer hugo avec rsync
title: Déployer hugo avec rsync
description: Une commande pour mettre son site àjour
weight: 10
tags:
- webmaster
- réseau
- ssh
topics:
- réseau

---

On peut bien sûr mettre à jour le site avec un clien ftp (filezilla par exemple), mais c'est un peu fastidieux.    
La meilleure solution est d'utiliser [rsync](https://technique.arscenic.org/transfert-de-donnees-entre/article/rsync-synchronisation-distant-de).    
 
<!--more-->
Rsync permet en une commande de mettre son site à jour.    

	hugo && rsync -r public/* govez@ftp.tuxfamily.org:/home/debiandoc/pingouindoc.tuxfamily.org-web/htdocs/hugo/