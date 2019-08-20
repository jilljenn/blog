---
title: Eigaki, phystx, Joe Hisaishi
author: Jill-Jênn
layout: post
permalink: /2011/12/25/eigaki-phystx-joe-hisaishi/
categories:
  - Misc
---
Avant tout, j'espère que vous avez passé un Joyeux Noël (en fait, je m'en tape, mais il est d'usage de commencer un billet de manière chaleureuse). Voici 3 projets récents (le 2e date d'aujourd'hui).

## Joe Hisaishi

Aux amateurs : combien de mélodies de Joe Hisaishi reconnaissez-vous ici ?  
Le record actuel est de 8 !
{% youtube KusYNlX9h2M %}

## phystx

[phystx][1] est un webcomic créé en TeX par phystx et moi. On a conçu un package nommé **phx.sty** (évidemment), qui contient des macros pour Ti*k*Z, un langage pour faire des figures sous LaTeX. Des métamacros, en fait.

 [1]: http://phystx.com

## Eigaki

Reconnaissez que noter un film sur 10, c'est hyper dur. On note quelques films, puis au bout d'une dizaine, on se rend compte qu'on doit noter un film qui vaut plus qu'un film qui a 9 mais moins qu'un film qui a 8. En plus, un 6/10 n'a pas la même valeur d'une personne à une autre.

Pour un projet de master, j'ai fait [un site de recommandation de films][2]. Le principe : lister les films que vous avez aimés, et ceux que vous n'avez pas aimés. Le reste des informations sont facultatives (*Avez-vous aimé la réalisation ? le scénario ? la musique ? Qu'est-ce qui vous a plu ? Qu'est-ce qui vous a déplu ?*). Deux avantages :  
— le côté binaire fait qu'une fiche est rapide à remplir (le site attribue une note implicite au film en fonction de ce que vous avez coché) ;  
— les deux dernières questions appellent des tags personnels.

 [2]: http://eigaki.com

### L'algorithme classique (*k-nearest-neighbors user-based recommendation*)

Dans un premier temps, cet algorithme cherche à coups de produits scalaires les personnes qui vous ressemblent le plus en matière de goûts (vos *amis*[^1]). Pour ce faire, il considère pour chaque utilisateur la liste de ses notes pour chacun des films. Deux utilisateurs sont d'autant plus proches que le produit scalaire de leurs vecteurs de notes (appelé *score*) est grand (si les deux ont une note de −5 pour un film, ça comptera autant que si les deux avaient une note de 5 pour ce film, par exemple).

Ensuite, il calcule la moyenne des notes de vos « amis » pour chacun des films, pondérées par leur score (quelqu'un de plus proche de vous aura donc plus de poids dans la note finale). Ensuite, il classe les films dans l'ordre décroissant de leurs notes, et zou ! il vous file les 5 premiers.

Il existe une variante appelée *item-based recommendation* qui établit une similarité entre films plutôt qu'entre utilisateurs. Ça donne de meilleurs résultats, paraît-il (il doit être plus simple de trouver que deux films sont proches plutôt que deux utilisateurs).

Le souci avec une telle méthode, c'est que deux utilisateurs ne seront considérés comme similaires que s'il existe des films qu'ils auront vus tous les deux (sinon, ils seront « orthogonaux »).

### Un algorithme probabiliste (chaînes de Markov)

Il est possible de considérer une marche aléatoire dans un graphe non orienté dont les nœuds représentent soit un film, soit un utilisateur, soit une catégorie de films. Les arêtes relient des utilisateurs et des films, ou des films et des catégories, et sont pondérées : plus un utilisateur aime un film, plus le poids de l'arête les liant est grand (idem pour la relation film-catégorie). Ensuite, on calcule le nombre de pas moyen pour aller d'un certain utilisateur à chacun des films, les plus proches étant susceptibles de plaire à l'utilisateur.

Cette technique fournit des résultats qui ne sont pas bien meilleurs que l'algorithme classique ; certains chercheurs critiquent son niveau d'abstraction. Le problème également, c'est que les arêtes ne peuvent pas avoir un poids négatif.

### L'algorithme maison (basé sur SimRank++)

Un article datant de 2010 parle d'un algorithme où la similarité entre utilisateurs est définie en fonction de la similarité entre films (pour tous les couples de films qu'ils ont vus), et inversement. Cela aboutit à une équation matricielle, résoluble. Il existe même un algorithme très simple d'approximation de la solution (pour éviter de calculer des inverses, BRRR !).

Seul bémol : il faut manipuler 2 matrices comportant (nombre d'opinions)² éléments non nuls chacune (c'est ce petit ² (qui n'est hélas pas une note) qui fait toute la différence). J'ai donc eu la joie de constater avec 4 536 opinions qu'un calcul approximatif de la matrice solution durait 7 heures, 47 minutes et 19 secondes.

Pour vous aider à remplir votre liste, le site vous propose de noter des films controversés (c'est-à-dire, qui ont presque autant de votes positifs que de votes négatifs). Apparemment, le film le plus controversé de toute l'histoire est *L'Île du docteur Moreau* (1996) : 194 votes positifs, 194 votes négatifs ! Et dans les films plus récents, on trouve *L'Imaginarium du docteur Parnassus* et le dernier *Harry Potter*.

 [^1]: Si tu cherches des amis, inscris-toi sur Eigaki.