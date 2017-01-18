---
author: "Patrice Blondel"
date: 2017-01-08
linktitle: Scroll to top
title: Scroll to top
description: Un retour haut de page
weight: 10
tags:
- haut de page
- css
- javascript
topics:
- webmaster
---

Une flèche qui permet un retour "haut de page", assez pratique pour les articles longs.   
Elle permet un accès rapide au menu, sans avoir à utiliser la molette de la souris.    <!--more-->
### Comment procéder ?   
Nous utiliserons le javascript et le CSS pour cela.  
Téléchargeons [jquery.js](http://code.jquery.com/jquery-1.5.2.js) puis plaçons-le dans le répertoire **/static/js**.    
Ajoutons également une image de flèche (que je nomme *top.png*) dans le répertoire **/static/images**.   

<div style="clear:both;"></div>

Écrivons maintenant le code javascript ainsi que le code CSS à la fin du fichier */themes/nom_du_theme/layouts/partials/header.html* ; 
cela permettra cet ajout sur toutes les pages du blog. 


	<script src="/js/jquery.js" type="text/javascript"></script>	
	<script type="text/javascript">
  		//<![CDATA[
		$(window).scroll(function() {
  		if($(window).scrollTop() == 0){
   	 	$('#scrollToTop').fadeOut("fast");
  		} else {
    		if($('#scrollToTop').length == 0){
     	 	$('body').append('<div id="scrollToTop">'+
        	'<a href="#"><img src="/images/top.png" alt="" /></a>'+
        	'</div>');
   	 	}
   	 	$('#scrollToTop').fadeIn("fast");
  		}
		});
		$('#scrollToTop a').live('click', function(event){
  		event.preventDefault();
  		$('html,body').animate({scrollTop: 0}, 'slow');
		});
  		//]]>
	</script>	
	<style type="text/css">		
		#scrollToTop a{
    			display: block;
    			font-size: 1em; 
    			text-decoration: none;   	
    			position: fixed;
    			right: 10px;
    			bottom: 10px;    	
    		}	
		#scrollToTop a:hover{
			text-decoration:none;	
    		}	
		#scrollToTop img{
			padding:0;	
    		}	
		#scrollToTop a img{
			border: none;	
    		}
	</style>