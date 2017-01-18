---
author: "Patrice Blondel"
date: 2011-11-20
linktitle: L'art Ascii
title: L'art Ascii
description: Utiliser le code ASCII
weight: 10
tags: 
- ascii

topics:
- humour
---

L'art ASCII consiste à réaliser des images uniquement à l'aide des lettres et caractères spéciaux contenus dans le code ASCII.
La forme la plus simple d'art ASCII est la combinaison de deux ou trois caractères pour exprimer une émotion en texte. 
Ce sont les smileys (ou émoticônes).    
<!--more-->
#### Par exemple, un smiley
<pre>:'(</pre>

signifie « triste ».         
Il est possible de composer des figures plus complexes qui utilisent plusieurs lignes :
#### Un autre exemple, ma signature

<pre> (@<  
 //\  
//  ) 
v__/__ </pre>

le pingouin des @lpes     

    
Enfin, il est possible de réaliser des compositions très élaborées ; cela devient un art.    
#### Le logo de Gimp
<pre>

 	  	 .                     /.           
          \`.                 / |           
           \ `.             .'  .           
            \  `.         .'    .           
             \   `- - - ''     /            
              _..   .--.      .             
             :    `:   _|     |             
         .--.`._(@;`._(@;     .             
        : )  \               .              
         \    :          |  /               
           -.-          ; .'                
             ``-= ....-'-"                  
 _____ _             ____ ___ __  __ ____   
|_   _| |__   ___   / ___|_ _|  \/  |  _ \  
  | | | '_ \ / _ \ | |  _ | || |\/| | |_) | 
  | | | | | |  __/ | |_| || || |  | |  __/  
  |_| |_| |_|\___|  \____|___|_|  |_|_|     

</pre>

Vous pouvez donc, avec un simple éditeur de texte, créer vos logos, signatures ou dessins en Ascii.     
Si vous n'avez pas le talent requis (ce qui est mon cas), vous pouvez utiliser divers outils pour vous aider.    

#### Les générateurs Ascii
Ils sont nombreux (je ne mets que deux exemples mais vous en trouverez une multitude en cherchant dans google) :    

- [Ascii generator](http://www.network-science.de/ascii/) : le plus basique, il passe du texte en mode ascii en sélectionnant le type de police, un reflet, la taille, …
- [Picascii](http://picascii.com/) : permet de transformer une image en Ascii.    

 

#### Figlet : l'ascii art en ligne de commande

Figlet ne dessine pas mais va transformer votre texte en Ascii.    

**Installons :**    

	# aptitude install figlet
L'utilisation en console est simple :    

	$ figlet govez     
nous renvoie :

<pre>
  __ _  _____   _____ ____
 / _` |/ _ \ \ / / _ \_  /
| (_| | (_) \ V /  __// / 
 \__, |\___/ \_/ \___/___|
 |___/                    
            
</pre>

Pour voir les styles disponibles :    
   
	$ showfigfonts

Pour les utiliser :     

	$ figlet -f smscript govez

#### le résultat :

<pre>
 _,  _        _  __  
/ | / \_|  |_|/ / / _
\/|/\_/  \/  |_/ /_/ 
 (|               (| 

</pre>

### Des vidéos en Ascii

Il est possible avec Mplayer de lire des vidéos en Ascii.    
Il faut utiliser l'option « aa » ou « caca » (pour la couleur).    
  
	$ mplayer -quiet -vo aa mavideo.flv
## Bon amusement
