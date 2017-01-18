+++
title = "memento"
date = "2017-01-07"
description = "Aide-mémoire Hugo"
+++


### Sommaire     
1. [les commandes essentielles](#commandes)
2. [la typographie](#typographie)
3. [les citations](#citations)
4. [les listes](#listes)
5. [les textes longs](#longs)
6. [les liens](#liens)
7. [les tableaux](#tableaux)
8. [les images](#images)
9. [les vidéos](#videos)
10. [le code](#code)

<div id="commandes"></div>
### Commandes essentielles 

Créer un nouvel article :     

	$ hugo new post/nouveau.md

Générer le serveur :     

	$ hugo server --buildDrafts


Ajouter un thème : 

	$ cd themes
	$ git clone https://github.com/dim0627/hugo_theme_robust.git
	$ cd ..
	$ hugo server --theme=hugo_theme_robust --buildDrafts    

Rsync permet en une commande de mettre son site à jour.    

	$ hugo && rsync -r public/* govez@ftp.tuxfamily.org:/home/debiandoc/pingouindoc.tuxfamily.org-web/htdocs/hugo/

<div id="typographie"></div>
### La typographie Markdown

**Aller à la ligne** : 4 espaces    

Écrire en **gras** :  encadrer le mot par deux *    
Écrire en *italique* : encadrer le mot par une *    
Barrer un ~~texte~~ : encadrer le texte par deux ~   

**une ligne horizontale** : écrire - - - entre les paragraphes
texte    

---

texte  


<div id="citations"></div>
### Les citations
Pour afficher un bloc de citation, commencez le paragraphe par un chevron fermant.
     
>Les cons, ça ose tout !     C'est même à ça qu'on les reconnaît.    
>Lino Ventura, Les tontons flingueurs (1963)

	
	>Les cons, ça ose tout ! C'est même à ça qu'on les reconnaît.
	>Lino Ventura, Les tontons flingueurs (1963)

<div id="listes"></div>
### Les listes 

**liste non-ordonnée** : mettre *, + ou - au début de chaque élément

* premier
+ deuxième
- troisième   

**liste ordonnée** : mettre un nombre au début de chaque élément    

1. Premier
2. Deuxième
3. Troisième 


**liste avec sous-élément** : (décaler d'un espace le sous-élément)    

* Premier
* Deuxième
  + Sous élément
  * Sous élément
+ Troisième élément
- Quatrième élément
  * Sous élément
  - Sous élément
* Cinquième élément   

<div id="longs"></div>
### Publier des textes longs

Séparer les deux parties de texte par &lt; !- - more - -&gt; la première partie sera affichée
 mais il faudra cliquer sur *Lire la suite* pour avoir le texte entier.

<div id="liens"></div>
### Les liens

[Cliquez ici pour aller sur Google](http://www.google.fr "Le site Google")    
**Syntaxe :**  

	[Cliquez ici pour aller sur Google](http://www.google.fr "Le site Google")    


[Lien vers une autre page de mon site](/about/index.html)    

	[Lien vers une autre page de mon site](/about/index.html)

<div id="tableaux"></div>
### Les tableaux


Année | CA | TVA | TTC
| :---: | ---: | :---: | ---: |
2010 | 3 200 | 19,6 % | 3 827,20
2011 | 6 500 | 19,6 % | 7 774,00
2012 | 14 500 | 20,6 % | 17 487,00

#### Syntaxe

	Année | CA | TVA | TTC
	| :---: | ---: | :---: | ---: |
	2010 | 3 200 | 19,6 % | 3 827,20
	2011 | 6 500 | 19,6 % | 7 774,00
	2012 | 14 500 | 20,6 % | 17 487,00

C’est la seconde ligne du tableau Markdown qui va gérer les alignements des cellules.    
En n’oubliant pas les pipes | pour marquer et séparer les cellules ainsi que les infos d’alignement :     

- Centré :---:
- À droite ---:
- À gauche :---

<div id="images"></div>
### Les images
On peut les insérer très simplement en utilisant du code Markdown :  ![home](/images/home.png "image en local")

	![home](/images/home.png "image en local")   

Avec l'argument [img] l'image ne dépassera pas le cadre :    

![img](/images/cupsong.jpg)      

	![img](/images/cupsong.jpg)  

### Ou alors : 

{{% fluid_img "/images/plage.jpg" %}}    

**Syntaxe:** {&#123;% fluid_img "/images/plage.jpg" %}}


<div id="videos"></div>
### Les vidéos


Repérer l'ID de la vidéo (sur Youtube par exemple) pour afficher la vidéo.    
**Syntaxe**   : {&#123;< youtube w7Ft2ymGmfc >}}

{{< youtube w7Ft2ymGmfc >}}




<div id="code"></div>
### Insérer du code 




Il suffit d'encadrer le bloc de code par &grave;&grave;&grave; nom_du_langage et &grave;&grave;&grave;     

Du HTML :    
``` html
<section id="main">
  <div>
    <h1 id="title">{{ .Title }}</h1>
    {{ range .Data.Pages }}
      {{ .Render "summary"}}
    {{ end }}
  </div>
</section>
```    
Du CSS    

``` css
a:visited {
  	color: #265778;
}
```    


Du Ruby   

``` ruby
print "Hello, World!\n"
```    

