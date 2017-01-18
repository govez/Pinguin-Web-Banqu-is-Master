---
author: "Patrice Blondel"
date: 2015-07-20
linktitle: Intégrer une vidéo en html5
title: Intégrer une vidéo en html5
description: Un meilleur affichage des vidéos
weight: 10
tags: 
- vidéo
- html5
topics:
- webmaster
---

En HTML5, une balise dédiée permet l'intégration de la vidéo.     
il est donc beaucoup plus aisé d'intégrer de la vidéo (aussi facile que pour une image).     
<!--more-->

Le webmaster n'a pas à se soucier de savoir si l'utilisateur possède les bons codecs ; ceux-ci sont inclus de manière native.     

### Utilisation de la balise &lt;video&gt;

src | L'URL du conteneur de la vidéo
| :---: | :--- |
width, height| Les dimensions de l'image
poster | L'URL d'une image à afficher en remplacement de la vidéo, en attendant qu'elle soit disponible. On utilise une frame de la vidéo
videoHigh, videoHeight | Ce sont les dimensions originelles de l'image. Des attributs en lecture seule qui sont lus en JavaScript, pour fournir une information sur la vidéo
autobuffer | Vaut *true* ou *false*, la valeur vrai déclenche le chargement en mémoire de la vidéo en même temps que la page, une option choisie quand on suppose qu'elle sera obligatoirement vue
autoplay | Vaut *true* ou *false*, la valeur vrai démarre la vidéo quand la page est chargée
loop | Vaut *true* ou *false*, la valeur vrai fait tourner la vidéo en boucle
controls | Vaut *true* ou *false*, la valeur vrai indique que la barre de contrôle par défaut s'affiche, sinon le site définit sa propre barre


### Un exemple

<video width="100%" poster="http://pingouindesalpes.com/videos/cupsong.jpg" controls="controls">
  <source src="http://pingouindesalpes.com/videos/cupsong.mp4"  type="video/mp4"  />
  Choisissez un navigateur plus récent compatible html5
</video>    
<em>The Cup Song</em>


#### Syntaxe

```html
<video width="largeur" height="hauteur" poster="url_de_l_image_d_accueil" controls="controls">
  <source src="url_de_la_vidéo" type="video/mp4" />
  Choisissez un navigateur plus récent compatible html5
</video>
```

