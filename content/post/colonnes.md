---
date: "2016-11-18"
author: "Patrice Blondel"
weight: 10
description: Afficher le texte sur plusieurs colonnes
title: Multicolonnage 
linktitle: Multicolonnage 
tags:
- css
- colonnes
topics:
- typographie
---


Afin que le texte soit plus lisible, il est necessaire d'afficher le contenu sur plusieurs colonnes 
(comme dans la presse écrite).  
**Le CSS3 permet cette réalisation de façon très simple.**      
<!--more-->  

<p class="deuxcolonnes">
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt 
ut laoreet dolore magna aliquam erat volutpat.    
Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis 
nisl ut aliquip ex ea commodo consequat.    
Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, 
vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim 
qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.    
Nam liber tempor cum soluta nobis eleifend option congue nihil imperdiet doming id quod mazim 
placerat facer possim assum.    
Typi non habent claritatem insitam; est usus legentis in iis qui facit eorum claritatem.    
Investigationes demonstraverunt lectores legere me lius quod ii legunt saepius.
</p>


Il suffit de déterminer une classe pour ces nouveaux paragraphes et de les écrire sous la forme :   

	<p class="deuxcolonnes">Contenu du texte réparti sur 2 colonnes</p>



### Renseignons le css 

```css
/* Multicolonnage */ 

p.deuxcolonnes {
    -webkit-column-count: 2; /* Chrome, Safari, Opera */
    -moz-column-count: 2; /* Firefox */
    column-count: 2;
    -webkit-column-gap: 2em; /* Chrome, Safari, Opera */
    -moz-column-gap: 2em; /* Firefox */
    column-gap: 2em;
}
```