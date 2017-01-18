---
date: "2015-08-03"
author: "Patrice Blondel"
weight: 10
description: Lire de la musique dans les pages Web
title: Un lecteur audio
linktitle: Un lecteur audio
tags:
- musique
- css
topics: 
- webmaster
---

En HTML5, la balise &lt;audio&gt; permet de lire un seul fichier son (mp3, ogg etc.).    
Je me suis aidé du tutoriel [Monnaie Libre](http://www.monnaielibre.creationmonetaire.info/lecteur-html5/) pour améliorer ce lecteur.    
<!--more-->

Le code permettant de lire un fichier son prend cette forme :    

	<audio controls="controls">
	<source src="titre.mp3" type="audio/mp3" />
	Votre navigateur ne supporte pas la balise HTML5 audio.
	</audio>    

Pour utiliser ce même lecteur avec plusieurs fichiers sons différents, il faut « bidouiller » un peu :    

#### 1. Modifier le fichier header.php de votre site en ajountant juste avant *&lt;/head&gt;*

<script>
function loadSong(elt, e) {
if(!e) var e = window.event;
document.getElementById("player").src=elt.href;
document.getElementById("player").load();
document.getElementById("player").play();
return false;
}
window.onload = function() {
links = document.getElementById("playlist").getElementsByTagName("a");
for(var i = 0; i<links.length; i++) {
links[i].onclick=function(e) { return loadSong(this, e); };
}
}
</script>

	<script>
	function loadSong(elt, e) {
	if(!e) var e = window.event;
	document.getElementById("player").src=elt.href;
	document.getElementById("player").load();
	document.getElementById("player").play();
	return false;
	}
	window.onload = function() {
	links = document.getElementById("playlist").getElementsByTagName("a");
	for(var i = 0; i<links.length; i++) {
	links[i].onclick=function(e) { return loadSong(this, e); };
	}
	}
	</script>

#### 2. Code à ajouter dans votre article    
```html
<div>
<audio tabindex="0" id="player" controls="controls">
</audio>
<ul id="playlist">
<li><a href="fichier1.mp3" onclick="loadSong()">fichier2</a></li>
<li><a href="fichier2.mp3" onclick="loadSong()">fichier2</a></li>
<li><a href="fichier2.mp3" onclick="loadSong()">fichier2</a></li>
</ul>
</div
```    
#### 3. Renseigner le fichier theme.css de votre thème    
```css
/* lecteur audio */
#player {
	margin: 0;
	padding: 0;
	font-family: sans;
	font-size: 12px;
	width: 210px;
	} 
#playlist {
	border: solid 5px #555;
	font-family: sans;
	font-size: 12px;
	background-color: #777;
	list-style: none;
	margin: 0px;
	padding: 0px;
	width: 210px;
	}	 
#playlist li:nth-child(even) {
	background-color: #888;
	}
#playlist li:nth-child(odd) {
	background-color: #777;
	}       
#playlist li a,
#playlist li a:visited,
#playlist li a:hover {
	color: white;
	padding-left: 2px;
	padding-right: 2px;
	text-decoration: none;
	}
```

Vous devez obtenir un lecteur de ce type.  
<div>
<audio tabindex="0" id="player" controls="controls">
</audio>
<ul id="playlist">
<li><a href="http://pingouindesalpes.com/sons/black_dog.mp3" onclick="loadSong()">Blackdog [Led Zeppelin]</a></li>
<li><a href="http://pingouindesalpes.com/sons/dancing_days.mp3" onclick="loadSong()">Dancing Days [Led Zeppelin]</a></li>
<li><a href="http://pingouindesalpes.com/sons/ten_years_gone.mp3" onclick="loadSong()">Ten Years Gone [Led Zeppelin]</a></li>
</ul>
</div>    

Un clic sur le titre démarre le « player »    
À vous de modifier le CSS pour obtenir le look souhaité.  
  
Une bonne occasion de ré-écouter Led Zeppelin    


