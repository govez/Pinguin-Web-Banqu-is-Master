---
author: "Patrice Blondel"
date: 2012-02-12
linktitle: L'alphabet phonétique international 
title: L'alphabet phonétique international 
description: Afficher les caractères phonétiques
weight: 10
tags: 
- phonétique
topics:
- typographie
---

[L'alphabet phonétique international](http://fr.wikipedia.org/wiki/Alphabet_phon%C3%A9tique_international) (API) 
est un alphabet utilisé pour la transcription phonétique des sons du langage parlé.     
Contrairement aux nombreuses autres méthodes de transcription qui se limitent à des familles de langues, 
l'API est prévu pour couvrir l'ensemble des langues du monde.    

<!--more-->

### Utilisation dans un traitement de texte

Si on n’a pas les caractères de l’API dans les « caractères spéciaux » on peut installer une fonte spécialisé 
sur son ordinateur.        
Les fontes **Doulos SIL** de [SIL International] (http://www.sil.org/) sont Open Source.     

Téléchargez cette police puis copiez le fichier **DoulosSIL-R.ttf** dans votre répertoire *.fonts*.     
Dans votre traitement de texte, choisissez d'insérer des caractères spéciaux ; 
choisissez la police **Doulos** et l'alphabet phonétique international pour afficher vos caractères.   


![img](/images/api_lo.png "Choisir les polices API dans libre Office")   
Choisir les polices API dans libre Office    

### Intégration dans une page Html

L’insertion de caractères de l’API dans un document pour publication sur Internet ne peut pas se faire 
par simple insertion du caractère phonétique.    
Il faut insérer le code qui représente chaque caractère.    
Pour insérer son propre code, voici un tableau qui présente les caractères de l'alphabet phonétique, 
il suffit d'insérer les codes HTML (ceux de la dernière colonne).  

## Tableau des voyelles

Phonème | Graphies | Exemples | HTML
|:---: | :--- | :--- | :--- |
[ a ] | a, à, ha  | lac, à, habit | &amp;#97;
[ &#593; ] | â, a | pâte, cadre | &amp;#593;
[ ɑ̃ ] | an, am, en, em, han, aon | divan, jambe, gentil, remplir, hanté, paon | &amp;#771;
[ &#601; ] | e, ai, on | leçon, faisan, monsieur | &amp;#601;
[ e ] | é, er, ai, ez, hé; | égal, danser, j'aurai, chez, hélas | &amp;#101;
[ &epsilon; ] | é, e, ai, ei, &ecirc;, he, et, ey, enn, ess, ett | sève, espoir, j'aime, neige, crêpe, herbe, jouet, chienne | &amp;#949;
[ &oslash; ] | eu, oeu | jeu, vœu | &amp;#248;
[ &oelig; ] | eu, heu, œu | seul, heure, œuf | &amp;#339;
[ i ] | i, y, &iuml;, hi | fourmi, cygne, haïr, hiver | &amp;#105;
[ &#603;&#771; ] | in, im, en, ain, ein, aim | singe, impoli, chien, train, frein, faim | &amp;#603; &amp;#771;
[ o ] | o, au, eau, hau, &ocirc; | rose, autour, peau, hauteur, drôle | &amp;#111;
[ &#596; ] | o, au, ho | note, mauvais, homme | &amp;#596;
[ &#596;&#771; ] | on, om, hon | carton, pompier, honte | &amp;#596; &amp;#771;
[ u ] | ou, où, oû | soupe, où, goût | &amp;#117;
[ y ] | u, û, hu  | têtu, bûche, humide | &amp;#121;
[ &oelig;&#771; ] | un, um | lundi, parfum | &amp;#339; &amp;#771;


## Tableau des semi-voyelles

Phonème | Graphies | Exemples | HTML
|:---: | :--- | :--- | :--- |
[ j</span> ] | i, ll, il, ill, y | pied, billet, travail, rouille, yogourt | &amp;#106;
[ w</span> ] | oi, oin, ou, w | loi, soin, oui, Halloween | &amp;#119;
[ &#613;</span> ] | u, hu | lui, huit | &amp;#613;


## Tableau des consonnes

Phonème | Graphies | Exemples | HTML
|:---: | :--- | :--- | :--- |
[ b</span> ] | b | abri | &amp;#98;
[ k</span> ] | c, cc, qu, k, ch | café, occupé, quand, kilo, chorale | &amp;#107;
[ &#643;</span> ] | ch | achat | &amp;#643;
[ d</span> ] | d, dd | don, addition | &amp;#100;
[ f</span> ] | f, ff, ph | fort, siffler, phrase | &amp;#102;
[ g</span> ] | g, gu | globe, déguisé | &amp;#103;
[ &#626;</span> ] | gn | saigner | &amp;#626;
[ &#658;</span> ] | j, g, ge | jeu, agile, plongeon | &amp;#658;
[ l</span> ] | l, ll | lune, ballon | &amp;#108;
[ m</span> ] | m, mm | amour, commande | &amp;#109;
[ n</span> ] | n, nn | nature, personne | &amp;#110;
[ p</span> ] | p, pp | pouce, appeler | &amp;#112;
[ r</span> ] | r, rr, rh | rond, verre, rhume | &amp;#114;
[ s</span> ] | s, ss, c, ç, t, x | sel, tousser, cinéma, garçon, invention, six | &amp;#115;
[ z</span> ] | s, z | raison, zéro | &amp;#122;
[ t</span> ] | t, tt, th | très, attache, thé | &amp;#116;
[ v</span> ] | v | vite | &amp;#118;
[ ks</span> ] | x, cc, xc | taxi, accident, excité | &amp;#107; &amp;#115;
[ gz</span> ] | x | examen | &amp;#103; &amp;#122;



### Un exemple



gentil  &#x25B6; [ <strong>&#658;&#593;&#771;&#116;&#105;</strong> ] a pour code : 
	[ &amp;#658;&amp;#593;&amp;#771;&amp;#116;&amp;#105; ]

