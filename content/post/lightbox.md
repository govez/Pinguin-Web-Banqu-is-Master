---
author: "Patrice Blondel"
date: 2017-01-07
linktitle: Une lighbox en CSS
title: Une lighbox en CSS
description: Un meilleur affichage des images
weight: 10
tags: 
- images
- javascript
topics:
- webmaster

---

L’effet **lightbox** permet d’afficher des images, du contenu, des pages au premier plan d’une page Web sans avoir 
à quitter la page.     
Il assombrit le reste de la page et met en évidence le contenu en surbrillance.<!--more-->
   
Comment obtenir une lightbox uniquement en css (pas de jquery, pas de javascript). 

<!-- plage -->
<a href="#img2" class="trigger">
![home](/images/plage_mini.jpg)   
</a>

<!-- lightbox plage -->
<div class="lightbox" id="img2">
<img src="/images/plage.jpg">
<a href="#" class="close">Fermer</a>
</div>


#### Fonctionnement

Une image et sa miniature (plage.jpg et plage_mini.jpg) ont été placées dans le répertoire **/static/images**.

#### Le code    

	<!-- plage -->
	<a href="#img2" class="trigger">
	![home](/images/plage_mini.jpg)   
	</a>
	
	<!-- lightbox plage -->
	<div class="lightbox" id="img2">
	<img src="/images/plage.jpg">
	<a href="#" class="close">Fermer</a>
	</div>
		

#### Le CSS
Je l'ajoute au css de mon thème    

	<style type="text/css">
	.lightbox {
	    position: fixed;
	    top: 0;
	    left: 0;
	    visiblity: hidden;
	    z-index: 9999;
	    width: 100%;
	    height: 100%;
	    text-align: center;
  	    z-index: 9999;
	/* Les couleurs */
	    background: rgb(255,0,0);
	    background: transparent\9;
	    background: rgba(0, 0, 0, 0.8);
	    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr=#4cFF0000,endColorstr=#4cFF0000);
	    zoom: 1;
	/* effet de fermeture */
	    -webkit-transition: all 0.6s ease-in-out;
	    -moz-transition: all 0.6s ease-in-out;
	    -ms-transition: all 0.6s ease-in-out;
	    -o-transition: all 0.6s ease-in-out;
	    transition: all 0.6s ease-in-out;
	    -webkit-transform: rotate(0deg) scale(0);
	    -moz-transform: rotate(0deg) scale(0);
	    -ms-transform: rotate(0deg) scale(0);
	    -o-transform: rotate(0deg) scale(0);
	    transform: rotate(0deg) scale(0);
	    -webkit-transform-origin: right top;
	    -moz-transform-origin: right top;
	    -o-transform-origin: right top;
	    transform-origin: right top;
	}

	.lightbox:target {
	     opacity: 1;
 	     visiblity: visible;
	/* effet d'ouverture */
	    -webkit-transition: all 0.6s ease-in-out;
	    -moz-transition: all 0.6s ease-in-out;
	    -ms-transition: all 0.6s ease-in-out;
	    -o-transition: all 0.6s ease-in-out;
	    transition: all 0.6s ease-in-out;
	    -webkit-transform: rotate(0deg) scale(1);
	    -moz-transform: rotate(0deg) scale(1);
	    -ms-transform: rotate(0deg) scale(1);
	    -o-transform: rotate(0deg) scale(1);
	    transform: rotate(0deg) scale(1);
	    -webkit-transform-origin: left bottom;
	    -moz-transform-origin: left bottom;
	    -o-transform-origin: left bottom;
	    transform-origin: left bottom;
	}
	/* Image de taille maximale */
	.lightbox img {
	    max-width: 90%;
	    height: 95%;
	}
	/* Ajout du bouton "fermer" */
	.lightbox .close {
	    position: absolute;
	    top: 2%;
	    right: 2%;
	    color: #AAA;
	}
	</style>




