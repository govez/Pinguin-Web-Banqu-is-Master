---
date: "2010-10-20"
author: "Patrice Blondel"
weight: 10
description: L'encodage web
title: Les caractères spéciaux
linktitle: Les caractères spéciaux
tags:
- caractères spéciaux
topics: 
- typographie
---


En informatique, les caractères alphabétiques sont associés à des codes binaires, 
c'est à dire composés d'une suite de 1 et de 0.     
Il existe plusieurs façon de traduire les caractères en codes binaires :    

<!--more-->

- En ***ASCII**, les caractères sont codés sur 7 bits, soit un code composé de sept chiffres 
qui sont tous égaux à 0 ou à 1. Il permet donc de représenter 27 soit 128 caractères différents.     
128 caractères sont suffisant pour mémoriser notre alphabet, 
les chiffres, des élements de ponctuation (...), mais pas suffisant pour stocker nos caractères spéciaux (accents, cédilles...)    
- En **ISO 8859-1** (souvent appelée Latin-1), les caractères sont codés sur 8 bits. 
Il permet donc de représenter 28 soit 256 caractères différents. 256 caractères sont suffisants
 pour mémoriser notre alphabet latin avec les caractères spéciaux (accents, cédilles...)    
- L'**ISO 8859-15** (souvent appelée Latin-9) est une variante réactualisée du Latin-1. 
Toujours codée sur 8 bits, il ajoute notamment le caractère euro (€) et les caractères œ et Œ 
à la place de certains caractères peu utilisés.    
- Le **Windows-1252** (parfois appelé AINSI) est un encodage propre aux ordinateurs Windows. 
S'il est lui aussi codé sur 8 bits, certains caractères diffèrent des codages ISO vu ci-dessus.    
- Le **MacRoman** est un encodage propre aux ordinateurs Apple Macintosh. S'il est lui aussi codé sur 8 bits, 
certains caractères diffèrent des codages ISO et Windows-1252 vu ci-dessus.    
- L'**UTF-8** est un encodage dit "Unicode". 
L'**Unicode** vise à donner à tout caractère quelque soit son alphabet (latin, cyrillique, asiatique...) 
un code unique et compatible sur toutes les plateformes (Windows, Mac, Unix).    
- L'**UTF-8** est codé sur 8 à 32 bits ce qui permet d'encoder un nombre de caractères quasi illimité. 
Voir en fin de page pour en savoir plus.

### Les caractères spéciaux en HTML

En HTML, tous les caractères spéciaux peuvent être remplacés par un code commençant par **&**
(esperluète ou « et commercial ») et terminant par ; (point virgule).     
En voici une liste non exhaustive :


Code | Résultat
| :--- | :--- |
&amp;nbsp; | &nbsp;[espace insécable]
&amp;quot; | &quot;
&amp;lt; | &lt;
&amp;gt; | &gt;
&amp;laquo; | &laquo;
&amp;raquo; | &raquo;
&amp;amp; | &amp;
&amp;euro; | &euro;
&amp;yen; | &yen;
&amp;copy; | &copy;
&amp;reg; | &reg;


Les caractères accentués ou encore les lettres avec cédilles sont également des caractères spéciaux. 
Chacun a donc sa représentation en HTML.    
### Les caractères accentués minuscules

Code | Résultat
| :--- | :--- |
&amp;agrave; | &agrave;
&amp;acirc; | &acirc;
&amp;eacute; | &eacute;
&amp;egrave; | &egrave;
&amp;ecirc; | &ecirc;
&amp;icirc; | &icirc;
&amp;iuml; | &iuml;
&amp;oelig; | &oelig;
&amp;ugrave; | &ugrave;
&amp;ucirc; | &ucirc;
&amp;ccedil; | &ccedil;


### Les caractères accentués majuscules

Code | Résultat
| :--- | :--- |
&amp;Agrave; | &Agrave;
&amp;Acirc; | &Acirc;
&amp;Eacute; | &Eacute;
&amp;Egrave; | &Egrave;
&amp;Ecirc; | &Ecirc;
&amp;Icirc; | &Icirc;
&amp;Iuml; | &Iuml;
&amp;OElig; | &OElig;
&amp;Ugrave; | &Ugrave;
&amp;Ucirc; | &Ucirc;
&amp;Ccedil; | &Ccedil;



### L'avantage de l'UTF-8

En utilisant l'UTF-8 dans nos pages, on s'affranchit de la conversion des caractères spéciaux en code HTML. 
Un "e" avec accent aigu pourra donc être écrit directement "é" et non "&amp;eacute;" dans notre code source.    

Il vous faudra ensuite, si ce n'est pas déjà le cas, préciser dans l'entête de votre page 
l'encodage choisi grâce à une balise **meta** :

Ajouter le code suivant entre les balises *&lt;head&gt;*  et *&lt;/head&gt;*

	<meta charset="UTF-8">

