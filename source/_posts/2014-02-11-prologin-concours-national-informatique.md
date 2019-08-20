---
title: Prologin, le concours national d'informatique
author: Jill-Jênn
layout: post
permalink: /2014/02/11/prologin-concours-national-informatique/
categories:
  - Prologin
  - Code
---
À l'occasion des [Google RISE Awards](https://www.google.com/edu/programs/google-rise-awards/) qui ont tout récemment récompensé l'association Prologin pour son engagement dans la promotion de l'algorithmique chez les jeunes, j'aimerais rappeler en quoi consiste ce concours.

L'association Prologin organise le concours national d'informatique, ouvert aux jeunes de 20 ans et moins. Celui-ci se déroule en trois parties :

* En octobre, un questionnaire de culture informatique et d'algorithmique.
* En février et mars, des épreuves régionales dans diverses villes de France et de Belgique.
* En mai, une finale de **36 heures non stop** à l'EPITA à Paris, sur un projet d'IA.

Le concours est entièrement gratuit et les dix meilleurs reçoivent un prix (un ordinateur portable, une console, mais aussi parfois des lots plus exotiques comme une caméra [GoPro](http://gopro.com) ou un [kit Arduino](http://arduino.cc/en/Main/ArduinoStarterKit)).

### Le questionnaire de sélection

Pour exemple, [le sujet de 2011](http://www.prologin.org/files/prologin2011/Prologin_QCM2011.pdf) s'intéressait à un logiciel minimaliste (ProloGIMP) de traitement d'images représentées par des matrices de 0 et de 1.

{% img /images/prologimp.png Un exemple d'image de ProloGIMP. %}

Les questions allaient de la simple écriture d'une fonction pour inverser les bits d'une image jusqu'à des questions plus difficiles telles que : à partir d'une image initialisée à 0 et d'un pinceau de curseur en forme de + qui inverse les bits sur lesquels on l'applique, est-il possible de dessiner une certaine image ? Notez que ce problème est identique au jeu [Lights Off](http://demo.marcofolio.net/lights_off_canvas/) (merci Alexis Comte !) où il faut éteindre toutes les lampes sachant que les interrupteurs sont interdépendants.

Si vous voulez essayer ces exercices, [en vous inscrivant](http://prologin.org/user/register) vous pourrez tester vos algorithmes sur [le serveur d'entraînement](http://prologin.org/training/challenge/qcm2011).

### Les épreuves régionales

L'épreuve régionale se déroule un samedi dans un centre d'examen. Le matin une épreuve écrite, l'après-midi une épreuve machine. Le déjeuner est offert par l'association.

#### Un sujet écrit d'algorithmique

Le samedi 17 mars 2012 vers neuf heures, la vidéo suivante a été diffusée dans un amphithéâtre à l'École polytechnique juste avant la distribution des sujets de l'épreuve écrite.

(Activez les sous-titres, cela nécessitera peut-être de passer par la version Flash, hélas.)

{% youtube VczJBIjPXds %}

Et voici [le sujet correspondant](http://www.prologin.org/files/archives/2012/demi-finales/sujet/the-final-problem.pdf), qui contenait une grille semblable à celle dont il est question dans la vidéo avec l'ensemble des candidats à l'épreuve écrite en haut et « finaliste » ou « non finaliste » en bas. La première question du sujet était d'ailleurs :

> Question 1. Alors ? Êtes-vous sélectionné en finale ?

Ces grilles, nommées [*amidakuji*](http://en.wikipedia.org/wiki/Ghost_Leg), sont très répandues au Japon : c'est effectivement un moyen très simple de créer une permutation aléatoire.

Aussi, savez-vous comment on dit « [une machine à deux anneaux](http://prologin.org/files/archives/2013/demi-finales/sujet/two-ring-machine.pdf) » en anglais ?

#### Un sujet machine de programmation

Voici un exemple d'exercice que j'aime beaucoup : [**Épiphanie**](http://prologin.org/training/challenge/demi2011/epiphanie).

> C'est l'épiphanie, Joseph Marchand doit se couper une part de gâteau des rois. En fait, la brioche ne l'a jamais intéressé ; non, ce qu'il aime, ce sont les fruits confits. Tradition familiale oblige, il va se servir une part de gâteau. Déterminer les endroits où couper de sorte à ce que Joseph obtienne la plus petite part contenant au moins une fois chaque fruit confit.

{% img http://prologin.org/files/prologin2011/problems/epiphanie.png Un gâteau des rois. %}

On pourrait certes tester toutes les parts, mais cette approche pour 1 000 fruits confits réaliserait 1 000 000 opérations, ce qui dépasserait la limite de temps. Il existe en réalité une approche qui n'explore que 2 000 parts.

### La finale

La dernière épreuve rassemble les 100 meilleurs candidats à l'EPITA pendant trente-six heures au cours desquelles la restauration et l'hébergement sont entièrement pris en charge par l'association. En 2006, les candidats pouvaient découvrir les premières lignes du [sujet](http://prologin.org/files/archives/2006/finale/sujet/sujet2006.pdf) (de 24 pages !) :

> Bonjour à toi, vainqueur de l'édition 2006 de Prologin ! Ce fut une belle finale, et ce marathon de programmation aura été serré. Mais fort heureusement, tu t'en es bien sorti. Reste à savoir qui tu es, puisque autour de toi les autres candidats lisent précisément le même texte. Car c'est toi — ou plutôt moi — qui as écrit ce sujet, à la différence que moi, j'ai participé à la finale, et toi pas encore.

Ce métasujet, inspiré de *Retour vers le futur* décrivait les règles du jeu et les différentes fonctions utilisables par les programmes des candidats. Le but : contrôler des joueurs sur une carte pour récupérer le fameux almanach et la DeLorean afin de parier dans des casinos dans le passé pour gagner le plus d'argent possible. Comme chaque année, chaque candidat devait programmer une intelligence artificielle nommée *champion* qui jouait au jeu et des tournois étaient organisés entre les différents champions pour déterminer un classement.

Après la présentation du sujet, en sortant dans la cour pour accéder à la salle machine, on pouvait découvrir **une véritable DeLorean**.

{% img /images/delorean.jpg Une DeLorean. %}

Car en plus de concevoir les règles du sujet et d'établir l'infrastructure de la finale, les orgas travaillent la déco. Et à l'issue des trente-six heures, d'une courte nuit et des oraux pour les dix premiers du classement devant un jury, à l'ouverture de la remise des prix, une vidéo est projetée retraçant l'événement. L'équipe EPTV avait donc travaillé d'arrache-pied la dernière nuit pour nous offrir le spectacle suivant :

{% youtube -c4fxrVIN-8 %}

Et pour la vidéo de la finale 2013, c'est [ici](http://vimeo.com/prologin/2013). Bon code à tous !
