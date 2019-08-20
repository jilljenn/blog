---
title: Carrés magiques
author: Jill-Jênn
layout: post
permalink: /2014/02/02/carres-magiques/
categories:
  - Mathématiques
  - Code
---
Le [musée de Grenoble](http://www.museedegrenoble.fr) a fêté ses 20 ans ce week-end, avec actuellement [Sigmar Polke](http://www.museedegrenoble.fr/1422-sigmar-polke.htm) à l'honneur. L'une de ses œuvres s'intitule « Carrés magiques I-VII (Saturne, Jupiter, Mars, Soleil, Vénus, Mercure, Lune) », et se compose de figures obtenues en reliant les nombres d'un carré magique d'ordre *N* dans l'ordre croissant, et ce pour *N* variant de 3 à 9 :

{% img /images/polke.jpg %}

On peut alors s'intéresser à la génération de carrés magiques d'ordre *N*. Apparemment, il existe une méthode simple pour le cas *N* impair, si simple qu'il en existe une implémentation en une ligne de Python :

{% highlight python %}
n=5
print [[(i+j-1+n/2)%n*n+(i+2*j-2)%n+1 for j in range(n)] for i in range(n)]
{% endhighlight %}

La [page Wikipédia](https://fr.wikipedia.org/wiki/Carré_magique_%28mathématiques%29) associée présente diverses méthodes plus ou moins compliquées pour le cas *N* pair, notamment une solution pour *N* multiple de 4 et une autre solution pour le cas général.

Mais heureusement, l'implémentation des carrés magiques dans le logiciel de calcul numérique Octave est succincte.

> Study the magic.m ([Figure 2](http://faculty.smu.edu/yzhou/Teach/2012F/practice1.pdf)) code and appreciate the wisdom inside this succinct script.

Il existe également une version Python de cette implémentation que l'on peut utiliser pour refaire les dessins de Polke en Ti*k*Z. Le code est sur [Bitbucket](https://bitbucket.org/jilljenn/polke).

{% img /images/polke-4.png %}
{% img /images/polke-5.png %}

{% img /images/polke-6.png %}
{% img /images/polke-7.png %}

{% img /images/polke-8.png %}
{% img /images/polke-9.png %}

À noter qu'il existe aussi [un package en R](http://cran.r-project.org/web/packages/magic/magic.pdf), qui permet de générer des hypercubes magiques de dimension quelconque.
