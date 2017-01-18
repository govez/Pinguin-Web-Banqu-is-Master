---
author: "Patrice Blondel"
date: 2011-04-09
linktitle: Un diaporama
title: Un diaporama
description: Faire défiler des images
weight: 10
tags: 
- javascript
- images
- diaporama

topics:
- webmaster
---

Je voulais, depuis déjà un moment, trouver la solution pour insérer ce blog statique un diaporama.    
Voici donc une première solution (sûrement à améliorer) ; mais ... ça fonctionne.    

<!--more-->


### Paysages d'Irlande

<div id="gallery"> 
	
<a href="#" class="show">
<img src="/images/diaporama/borddemer.png" alt="Bord de mer"  
class="&lt;h3&gt;Le bord de mer&lt;/h3&gt; sous un ciel nuageux."/></a>
  
     
<a href="#">
<img src="/images/diaporama/plage.png" alt="La plage" 
class="&lt;h3&gt;La plage&lt;/h3&gt; illuminée."/></a>

<a href="#">
<img src="/images/diaporama/rochers.png" alt="Les rochers" 
class="&lt;h3&gt;Les rochers&lt;/h3&gt; "/></a>

<div class="caption"><div class="content"></div></div>
</div>
<div class="clear"></div>

#### Comment faire ?

**Voici le code qui permet d'afficher le diaporama :**    

	<div id="gallery">
	
	<a href="#" class="show">
	<img src="url_image1" alt="image1"  
	class="&lt;h3&gt;titre&lt;/h3&gt; texte."/></a>
	     
	<a href="#">
	<img src="url_image2" alt="image2" 
	class="&lt;h3&gt;titre&lt;/h3&gt; texte"/></a>

	<a href="#">
	<img src="url_image3" alt="image3" 
	class="&lt;h3&gt;titre&lt;/h3&gt; "/></a>

	<div class="caption"><div class="content"></div></div>
	</div>
	<div class="clear"></div>

J'ai mis les images en 800X600 mais il est possible de la préciser dans le code avec *width="taille"*.    

** Je place le javascript à la fin de l'article (il ne sera pas souvent utilisé).**
### Javascript

	<script>
	$(document).ready(function() {        
	slideShow();	  
	});	  
	function slideShow() {	  
	$('#gallery a').css({opacity: 0.0});	      
	$('#gallery a:first').css({opacity: 1.0});	      
	$('#gallery .caption').css({opacity: 0.7});	  
	$('#gallery .caption').css({width: $('#gallery a').find('img').css('width')});	      
	$('#gallery .content').html($('#gallery a:first').find('img').attr('class'))	.animate({opacity: 0.7}, 400);	      
	setInterval('gallery()',6000);	      
	}	  
	function gallery() {	      
	var current = ($('#gallery a.show')?  $('#gallery a.show') : $('#gallery a:first'));	  
	var next = ((current.next().length) ? ((current.next().hasClass('caption'))? 
	     $('#gallery a:first') :current.next()) : $('#gallery a:first'));  	      
	var caption = next.find('img').attr('class'); 	      
	next.css({opacity: 0.0})
	.addClass('show')
	.animate({opacity: 1.0}, 1000);	  
	current.animate({opacity: 0.0}, 1000)
	.removeClass('show');	      
	$('#gallery .caption').animate({opacity: 0.0}, 
	{ queue:false, duration:0 }).animate({height: '1px'}, { queue:true, duration:300 }); 	      
	$('#gallery .caption').animate({opacity: 0.7},100 ) .animate({height: '50px'},500 );	      
	$('#gallery .content').html(caption);		  
	}
	</script>

### CSS
J'ajoute au fichier .css de mon thème la mise en forme de ce diaporama :

	.clear {
	    clear:both;
	}	 
	#gallery {
	   	position:relative;
		margin: auto;
		width: 800px;
		height:600px;
		margin-bottom:20px;
		}
	#gallery a {
		float:left;
		position:absolute;
	    	}	     
	#gallery a img {
		border:none;
	    	}	     
	#gallery a.show {
		z-index:500
	    	}	 
	#gallery .caption {
		z-index:600; 
		background-color:#000; 
		color:#fff; 
		height:50px; 
		width:100%; 
		position:absolute;
		bottom:0;
		left:0px;
	    	}	 
	#gallery .caption .content {
		margin:0;
		padding-left: 1em ;
		font-size:0.9rem;
	    	}	     
	#gallery .caption .content h3 {
		margin:0;
		padding:0;
		color:#1DCCEF;
		font-size:1.0rem;
	    	}

À vous de l'adapter en réglant tailles et couleurs.


<!--le script-->
<script>
$(document).ready(function() {      
      
//Exécute le diaporama
slideShow();
  
});
  
function slideShow() {
  
//opacité des images à 0
$('#gallery a').css({opacity: 0.0});
      
//afficher la première image (opacité 1)
$('#gallery a:first').css({opacity: 1.0});
      
//fond d'écran semi-transparent pour la légende
$('#gallery .caption').css({opacity: 0.7});
  
//Redimensionnement de la légende à la taille de l'image
$('#gallery .caption').css({width: $('#gallery a').find('img').css('width')});
      
//afficher la légende de la première image
$('#gallery .content').html($('#gallery a:first').find('img').attr('class'))
.animate({opacity: 0.7}, 400);
      
//lancer le diaporama, 6000 = image suivante après 6 secondes
setInterval('gallery()',6000);
      
}
  
function gallery() {
      
//s'il n'y a pas d'image saisir la première
var current = ($('#gallery a.show')?  $('#gallery a.show') : $('#gallery a:first'));
  
//obtenir l'image suivante, si fin du diaporama, retour au début
var next = ((current.next().length) ? ((current.next().hasClass('caption'))? 
     $('#gallery a:first') :current.next()) : $('#gallery a:first'));   
      
//obtenir la légende de l'image suivante
var caption = next.find('img').attr('class'); 
      
//fixer la disparition graduelle pour l'image suivante, exposition plus élevée
next.css({opacity: 0.0})
.addClass('show')
.animate({opacity: 1.0}, 1000);
  
//masquer l'image actuelle
current.animate({opacity: 0.0}, 1000)
.removeClass('show');
      
//fixer l'opacité à  0 et  la hauteur à 1px
$('#gallery .caption').animate({opacity: 0.0}, 
{ queue:false, duration:0 }).animate({height: '1px'}, { queue:true, duration:300 }); 
      
//animer la légende, opacité à 0.7 et hauteur à 100px, avec un effet de glissement
$('#gallery .caption').animate({opacity: 0.7},100 ) .animate({height: '50px'},500 );
      
//affichage du contenu
$('#gallery .content').html(caption);
          
}
</script>

