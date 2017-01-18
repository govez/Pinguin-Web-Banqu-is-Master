---
author: "Patrice Blondel"
date: 2017-01-13
linktitle: Un site qui fait bonne impression
title: Un site qui fait bonne impression
description: Créer un fichier print.css
weight: 10
tags: 
- impression
- css

topics:
- webmaster
---

C'est un peu gênant d'imprimer des articles sur des sites ou des blogs et de consommer du papier 
pour avoir des choses inutiles (à l'impression) ; le menu, la barre latérale, les commentaires ou le pied de page.    

Il existe pourtant un moyen de différencier l'affichage et l'impression.    
<!--more-->

Il suffit de créer un fichier *print.css* et de dire à la page d'en-tête de le lire pour imprimer.  
Je prendrai en exemple ce site en pages statiques (**Hugo**)    
Copions ce fichier *print.css* (imcomplet dans l'exemple) dans le répertoire **/themes/blackburn/static/css/**


	/* Enlever des affichages */
	.lightbox,
	.tags_article,
	.categories_article,
	.post-date,
	.prev-next-post,
	.prev-next-post .prev,
	.prev-next-post .next,
	#menu,
	.pagination,
	.icone_calendrier{
		display:none;
	}	
	.content {
		width:100%;
		margin:0;
		padding: 0;
	}
	#layout {
		padding-left: 0; /* left col width "#menu" */
		left: 0;
	}
	#layout.active .menu-link {
		left: 0;
	}
	.header{
		margin-top:-3.5em;
	}
	...

Appelons ce fichier CSS en renseignant le fichier */theme/layouts/partials/head.html*

	<link rel="stylesheet" href="/css/print.css" media="print" />

À vous maintenant de faire quelques réglages pour la tailles des polices,les couleurs ...    

Chez moi : [aperçu avant impression](/images/printcss.pdf)

