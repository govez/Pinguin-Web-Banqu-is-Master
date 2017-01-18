---
author: "Patrice Blondel"
date: 2008-05-07
linktitle: Transfert de fichiers avec ssh
title: Transfert de fichiers avec ssh
description: Relier deux machines
weight: 10
tags: 
- ssh
topics:
- réseau
---


Comment transférer des fichiers ou des répertoires entre des machines d'un même réseau.     
Cette méthode est très utile pour transférer ou copier de petits fichiers entre vos machines 
sans utiliser de clé USB mais en passant par le routeur.    

<!--more-->

**Préalable** : SSH doit être installé sur toutes les machines.    

Donc sous Debian/Ubuntu,    

	#apt-get install ssh

Pas besoin de solutions lourdes "client-serveur" du type FTP ou NFS pour déplacer 
un fichier ou un dossier d'une machine à l'autre de manière sécurisée.    

Utilisons scp : (secure copy) en mode console.    
#### Exemple :
Je veux transférer le fichier mon_fichier sur la machine distante machine_distante dans mon répertoire */home/utilisateur*.    
La machine distante peut être identifiée par son adresse IP.   
    
	$ scp mon_fichier utilisateur@machine_distante:/home/utilisateur/    

Le mot de passe ssh pour l'utilisateur me sera demandé et le fichier copié.     
Pour copier un répertoire complet, il faut utiliser l'option « -r » (récursive).     
Exemple : Je veux transférer le répertoire mon_repertoire sur la machine distante machine_distante 
dans mon répertoire */home/utilisateur*.    

	$ scp -r mon_repertoire utilisateur@machine_distante:/home/utilisateur/

Donc, vraiment très simple ; une fois de plus on peut remarquer la puissance des commandes en mode console.
