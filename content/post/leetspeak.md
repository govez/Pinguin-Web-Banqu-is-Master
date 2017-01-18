---
date: "2016-06-30"
author: "Patrice Blondel"
weight: 10
description: Le langage des geeks
title: l337 5p34k p0ur l35 633k5
linktitle: l337 5p34k p0ur l35 633k5
tags:
- geek
topics: 
- humour
---

 Le **Leet speak** (en leet speak : 1337 5p34k), de l'anglais « elite speak » (littéralement, « langage de l'élite »), 
est un système d'écriture utilisant les caractères alphanumériques ASCII d'une manière peu compréhensible 
pour le néophyte (appelé noob ou newbie) pour s'en démarquer.    
<!--more-->

Le principe est d'utiliser des caractères graphiquement voisins des caractères usuels, 
par exemple « 5 » au lieu de « S », « 7 » au lieu de « T » et, 
pour les extrémistes, « |_| » au lieu de « U » ou « |< » au lieu de « K », sans respect de l'orthographe ou des majuscules.    

Ce système d'écriture se retrouve chez certains geeks ou utilisateurs de jeux en réseau.    

### Vous voulez jouer les geeks ?

Voici un convertisseur qui vous permettra de prendre une certaine distance avec les noobs. **80n 4mU53m3n7 !**   
#### Convertisseur Leet speak


<script type="text/javascript">
function flipper() {
 var result = flipString(document.f.original.value.toLowerCase());
 document.f.flipped.value = result;
}

function flipString(aString) {
 var last = aString.length - 1;
 var result = new Array(aString.length)
 for (var i = last; i >= 0; --i) {
  var c = aString.charAt(i)
  var r = flipChar[c]
 	 result[i] = r != undefined ? r : c

  
 }
 return result.join('')
}

var flipChar = {
a : '4',
b : '8',
c : 'C', 
d : 'D',
e : '3',
f : 'F', 
g : '9',
h : 'H',
i : '1', 
j : 'j',
k : 'K',
l : 'L',
m : 'm',
n : 'n',
o : '0',
p : 'P',
q : 'k',
r : 'r',
s : '5',
t : '7',
u : 'U',
v : 'v',
w : 'w',
x : 'x',
y : 'y',
z : 'Z',


}	
	
for (i in flipChar) {
  flipChar[flipChar[i]] = i
}
</script>

<form name="f" method="GET"><br>

<table cellpadding=0 cellspacing=0>
<tr>
<td valign="top">Tapez votre texte :</td>
<td><textarea rows="5" cols="50" name="original" onkeyup="flipper()"></textarea></td>
</tr>
<tr>
<td valign="top">Résultat en Leet speak :&nbsp; &nbsp; &nbsp; &nbsp;</td>
<td> <textarea rows="5" cols="50" name="flipped" style="background:#CCC"></textarea></td>
</tr>
</table>