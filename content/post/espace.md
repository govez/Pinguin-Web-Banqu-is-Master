---
date: "2012-01-17"
author: "Patrice Blondel"
weight: 10
description: Différentes sortes d'espaces
title: Les espaces
linktitle: Les espaces
tags:
- espace
topics:
- typographie
---


Aussi importante que l'orthographe ou la grammaire, la ponctuation ne sert pas uniquement à décorer le texte.   
Elle est régie par des règles typographiques précises à ne pas négliger.     
Mais d'abord, précisons que le mot espace, lorsqu'il est utilisé en typographie, s'utilise au **féminin**.    

<!--more-->

Voici donc un petit aide-mémoire concernant les espaces et la ponctuation.
### La ponctuation simple « . » et « , »

Le point et la virgule répondent aux mêmes règles : pas d'espace avant et une espace après le signe.

### La ponctuation double « ! », « ? », « ; », « : »

Le point d'exclamation, le point d'interrogation, le point virgule et les deux points sont régis par les mêmes règles.    
 La typographie française exige une espace avant et après le caractère.    
Toutefois, la première espace est particulière : elle est insécable, c'est-à-dire qu'elle est forcément 
attachée au texte qui la précède. Le symbole du pourcentage, « % », répond aux mêmes caractéristiques.

### Points de suspension, etc.

Les points de suspension ne sont constitués que de trois points insécables.     
Il faut juste une espace après le dernier point.    
L'abréviation « etc. », qui signifie « et caetera » en latin, ne doit surtout pas être suivie par une multitude de points. 
On ne doit donc pas lui ajouter des points de suspension, puisque l'expression signifie simplement « et ainsi de suite ».

### Apostrophe et trait d'union

Ces deux caractères sont soudés aux lettres : il n'y a pas d'espace avant ni après ces signes de ponctuation. 
Dans les documents imprimés, et avec l’aide de logiciel de mise en pages professionnel, 
on peut insérer une espace fine sécable ou une espace fine insécable.     
Il en est de même pour la plupart des espaces qui existent dans leurs versions sécables ou insécables.    

### L'espace insécable

Dans les documents HTML, l’exemple le plus connu d’espace insécable est l’entité : 
« &amp;nbsp; », celle-ci a les mêmes propriétés que l’espace régulière, avec l’avantage de garder 
sur une même ligne les caractères étant de chaque côté.         
Pour l’espace fine, l’entité « &amp;thinsp; » est supportée par la plupart des navigateurs récents.     
Mais l’entité « &amp;thinsp; » est sécable, ce qui veut dire qu’en fin de ligne les caractères suivants seront poussés 
à la ligne suivante.    

S’il y a bien une espace difficile à reproduire sur Internet, c’est bien l’espace fine insécable.    
Celle-ci n’est tout simplement pas définie dans la norme Unicode.    
Alors que plusieurs opteront pour l’utilisation de l’espace insécable ordinaire « &amp;nbsp; », ce n’est pas la bonne solution.    


Heureusement, Unicode définit le « NARROW NO-BREAK SPACE », utilisant l’entité numérique : « &amp;#8239; ».    
 Cette espace étroite est insécable et peut être utilisée à la perfection comme espace fine insécable dans tout document HTML.

En typographie soignée, on prendra donc soin d’utiliser l’entité « &amp;#8239; » comme espace fine insécable. 