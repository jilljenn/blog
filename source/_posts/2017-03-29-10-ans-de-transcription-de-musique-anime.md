---
title: Transcription de partitions de musique d'anime
authors:
  - Jill-Jênn Vie
layout: post
published: true
permalink: /2017/03/29/transcription-de-partitions-musique-anime/
categories:
  - Anime
  - Musique
  - Code
---

Il y a 3 ans jour pour jour, le [Trio ELM](http://trioelm.com) faisait son premier concert, à l'ENS Cachan, à l'occasion des rencontres culturelles interENS :

{% img /images/music/concert.jpg %}

En voici la playlist complète ainsi que le [programme](http://trioelm.com/concerts/interq.html) :

<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLPtDOWi65kraB9AgUkcN9NkwIsiT6NRnb" frameborder="0" allowfullscreen></iframe>

À l'époque, on avait une certaine culture du teasing, donc on avait décidé de révéler les musiques du concert petit à petit, et on avait même proposé aux gens de suggérer des musiques via un input.  
<small>(Forcément, on s'est retrouvé avec les trolls classiques : l'opening de *Naruto* en allemand, les Chœurs de l'Armée rouge, *4’33”* de John Cage, etc.)</small>

{% img /images/music/FONDCONCERTDESU.min.jpg %}

Et en fait, on transcrivait nos partitions nous-mêmes ! On les a interprétées à Japan Expo en 2015, Japan Expo Sud en 2016, et plusieurs années à [Epitanime](http://www.epitanime.com) et [d'autres conventions](http://trioelm.com).

{% img /images/music/bokendeshodesho.jpg %}

C'est l'occasion pour moi de revenir sur **12 ans de transcription de partitions de musique d'anime**.

# Quel langage choisir pour mettre en page de la musique ?

Prenons une musique de piano.

{% youtube 6l15AFUuaoQ %}

Ces notes au piano constituaient la musique de fond de la page Web de *.hack//G.U.*, un jeu qui était très attendu en 2005. Il **fallait** transcrire cette musique.

## MusiXTeX, un langage pour écrire des partitions en TeX

Je [l'ai transcrite](http://jill-jenn.net/anime-sheet-music/pdf/desktop.html) en [MusiXTeX](https://en.wikipedia.org/wiki/MusiXTeX) en 2005, mais le code donnait ça. (Ma première partition par ordinateur.)

    ...
    \maketitle
    \startpiece
    \Notes\ibu0c0\qb0{Mcf}\ds\qp|\qp\sk\ds\qb0{gh}\tbl0\qb0j\en
    \bar
    \Notes\ibl0M0\qb0K\tbl0\qb0a\ql e\sk\ql d|\ibu0l0\qb0{ljhfe}\tbu0\qb0d\en
    \bar
    \Notes\ibl0H0\qb0{FJ}\tbl0\qb0M\ds\qp|\qu c\sk\ds\ibu0c0\qb0{Na}\tbu0\qb0c\en
    \bar
    \Notes\ibl0F0\qb0D\tbl0\qb0H\ql M\sk\qp|\ibu0j0\qb0{ecghi}\tbu0\qb0j\en
    \bar
    \Notes\ibl0E0\qb0{CG=KLb}\tbl0\qb0c|\ibu0m0\qb0m\tbu0\qb0l\zq {=k}\qu p\sk\qu n\en
    ...

Assez indigeste. C'est parce qu'on peut régler tout, jusqu'à l'angle d'inclinaison des ligatures.

## PMX, un langage plus simple qui produit du MusiXTeX

Plus tard, j'ai découvert qu'il existait des méthodes plus simples !! (Sans déconner.)  
Don Simons a codé un préprocesseur pour le MusiXTeX. Le langage s'appelle **PMX** et est plus lisible :

    1 1 3 4 3 4 0 -4
    0 5 16 0.085
    Piano
    t
    ./
    It60ipi
    Tt
    .hack//G.U. - Desktop
    Tc
    Chikayo Fukuda\\Transcribed by Jill-J\^enn Vie
    f83 c+ f g af c | ef c a f e d | c2 r4 /

Les premières lignes constituent le préambule, pour indiquer l'armure, la mesure, les instruments, et le tempo du fichier MIDI. Le cœur de la partition est la dernière ligne :

    f83 c+ f g af c | ef c a f e d | c2 r4 /

Ce qui donne :  
*fa do fa sol la<sup>♭</sup> do | mi<sup>♭</sup> do la fa mi ré | do*

{% img /images/music/desktop.png %}

(Bon j'ai mis des bémols alors qu'ils sont déjà à l'armure mais comme ça vous voyez comment ça marche.)

- Par défaut la note suivante est la plus proche, si on souhaite changer d'octave on a `+` ou `-`.
- `8` (*8<sup>th</sup>*) indique qu'il s'agit de croches (`4` : noires, `2` : blanches, etc.).
- `f` (*flat*) indique un bémol, `s` (*sharp*) un dièse.
- `r` (*rest*) est un soupir.

Ce qui est appréciable, c'est que PMX peut créer un fichier MIDI en plus de la partition (`.tex`), ce qui aide au debug. Sur [mon site](http://jill-jenn.net/anime-sheet-music/) vous avez une centaine de partitions créées à partir de ce langage.  
Je mettrai les sources en ligne, mais il y en a qui ont sombré avec mes anciens ordinateurs 😢.

Il existe aussi LilyPond, mais je trouve ce langage [plus compliqué](http://lilypond.org/text-input.fr.html), même s'il faut reconnaître que la communauté est très vivante, et que cela permet un rendu plus net.

## VexFlow

Depuis lors, un framework open source a été développé par un fou furieux en JavaScript, qui génère des commandes canvas ou du code SVG, avec lecture audio dans le navigateur, s'il vous plaît ! Ça s'appelle **VexFlow** et c'est [sur GitHub](https://github.com/0xfe/vexflow).

<div id="wmd-preview" class="wmd-panel wmd-preview">
    vextab
    options player=true tempo=140
    tabstave notation=true tablature=false time=3/4
    notes :8 F/3 C-F-G-A@/4 C/5 | E@-C/5 A@-F-E@-D@/4 |
    notes :2 C/4
    options space=15
</div>

Produit par le code [VexTab](https://github.com/0xfe/vextab) suivant :

    options player=true tempo=140
    tabstave notation=true tablature=false time=3/4
    notes :8 F/3 C-F-G-A@/4 C/5 | E@-C/5 A@-F-E@-D@/4 |
    notes :2 C/4
    options space=15

Les `@` indiquent les bémols, les `/4` `/5` sont les octaves.

<script src="http://static.vexflow.com/js/support/jquery.min.js"></script>
<script src="http://static.vexflow.com/js/support/underscore-min.js"></script>
<script src="http://static.vexflow.com/js/support/vexflow-min.81.js"></script>
<script src="http://static.vexflow.com/js/support/tabdiv-min.81.js"></script>
<script src="http://static.vexflow.com/js/support/paper.min.js"></script>
<script src='http://my.vexflow.com/js/app.9da856e68cab5dda7469337bb6f6f2eb.js'></script>

<script type="text/javascript">
  $(function() {
    notespace_embedded_setup();
  });
</script>

Quand je dis que ce sont des fous furieux, c'est qu'ils ont même des [tests visuels de rendu](http://www.vexflow.com/tests/index.html) et [plein d'autres trucs décrits sur leur blog](http://0xfe.blogspot.fr). Plus récemment, l'auteur a conçu un nouveau langage appelé [EasyScore](https://github.com/0xfe/vexflow/wiki/Using-EasyScore), plus lisible.
 
## Trinket

D'autres personnes appréciant le côté feedback immédiat ont codé [une surcouche propriétaire](https://trinket.io) du framework open source VexFlow. Leur langage est extrêmement simple (mais du coup, limité) :

<iframe src="https://trinket.io/embed/music/549fa52a01" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Ici des *fa* d'octaves croissants seront représentés par :

    FFF FF F f f' f'' f'''

Tandis que `-` et `+` permettent de mettre des bémols et dièses.

## Le mouvement OpenScore

Vous devez connaître [**IMSLP**](http://imslp.org) (*International Music Score Library Project*), c'est la plus grande base de données de partitions dans le domaine public. Ils se sont associés en janvier 2017 avec le logiciel open source [MuseScore](https://musescore.com) lors du dernier FOSDEM (*Free and Open Source Software Developers' European Meeting*) pour former **OpenScore**, une initiative visant à **ouvrir le code source des musiques** pour faciliter les reprises, arrangements, mais aussi l'indexation et l'extraction de données pour la recherche. [En savoir plus sur le site du FOSDEM](https://fosdem.org/2017/schedule/event/openscore/) ou [de MuseScore](https://musescore.org/en/user/57401/blog/2017/01/11/introducing-openscore).

La question est de savoir quel standard va gagner (MusicXML ? ou le format MSCZ de MuseScore ?).

Connaissez-vous d'autres initiatives prometteuses ? Vous pouvez en faire part dans les commentaires ci-dessous.

# Quelques anecdotes à propos des partitions transcrites

## Final Fantasy - Swing de Chocobo

Pour moi, le meilleur arrangement philharmonique du thème de Chocobo dans *Final Fantasy*, c'est **Swing de Chocobo** issu de *Final Fantasy X*.

{% youtube itwj_vStJAU %}

Pour le concert des prépas du lycée Thiers en 2008, on souhaitait à tout prix en faire une interprétation à six instruments + piano. MAIS impossible de mettre la main sur un trompettiste.

Je ne sais plus comment j'ai su que le documentaliste du CDI savait faire de la trompette. Du coup on est allés le voir :

> — BONJOUR, paraît que vous savez faire de la TROMPETTE ?  
> — Hein ? Oui mais je…  
> — S'IL VOUS PLAÎT c'est important.

Du coup c'était parfait de faire du PMX, parce que j'ai pu pondre toutes les versions pour tout le monde à coups de copier-coller :

{% img /images/music/chocobo.jpg %}

Vous pouvez écouter notre interprétation ci-dessous (ça commence à 1:33) et voir [toutes les partitions là](http://mickay.jill.free.fr/chocobo/). C'était une super expérience.

{% youtube 9MGior9dw3I %}

## Cosmo Warrior Zero - The Book of Life

Connaissez-vous le merveilleux ending **The Book of Life** de la série *Cosmo Warrior Zero* ? Non. Très bien.

{% youtube _LpDXnQVg_g %}

Un jour, pour une raison que j'ignore, je suis tombé sur une interprétation *live* de ce morceau par un quatuor de 3 chanteuses mexicaines et 1 piano : *el **Cuarteto Nausicaä***. Ça se déroulait à l'équivalent mexicain de Japan Expo.

{% youtube oy_fShMt7l0 %}

Comme je me souvenais que le refrain était difficile à transcrire au piano dans la musique originale, je me suis demandé : « *Tiens, comment elles ont fait, elles ?* » puis, au moment du refrain : « *Attends… elles ont fait comme moi… SE POURRAIT-CE QUE ?* » J'ai écrit à la pianiste, et elle m'a dit : « *Yes, you're right, it's yours!* » Wow.

## Ghost in the Shell - I Do

Cette petite pépite nous vient de la compositrice de génie [Yoko Kanno](https://en.wikipedia.org/wiki/Yoko_Kanno), qui compose 50 % du programme du Trio ELM (dont [**ELM**](https://www.youtube.com/watch?v=YR4TDBXebWc&spfreload=10) de la série géniale *Cowboy Bebop*), dont le trio tire son nom).

{% youtube qqmofWAAh1U %}

À l'été 2016, avec Ryan Lahfa, on a remporté un voyage au Japon pour notre projet de système de recommandation [Mangaki](https://mangaki.fr). À l'aéroport, comme il y a des pianos, on en a profité pour interpréter de la musique d'anime. Alors que Ryan était en train de jouer **Sadness and Sorrow** de *Naruto*, un Russe nous a interpellé : « *Hey guys, could you please play this?* » et il nous montre ceci :

{% img /images/music/ido.jpg %}

> Mec. C'est moi qui l'ai transcrite ta partition.

<blockquote class="twitter-tweet" data-lang="fr"><p lang="fr" dir="ltr">Piano de l&#39;aéroport, un mec me demande de jouer une partition, y a mon nom écrit dessus xD <a href="https://t.co/Kk8OeZZIFW">https://t.co/Kk8OeZZIFW</a> <a href="https://t.co/2rZpx3BSok">pic.twitter.com/2rZpx3BSok</a></p>&mdash; Jill-Jênn Vie (@jjvie) <a href="https://twitter.com/jjvie/status/756912248627535876">23 juillet 2016</a></blockquote> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

## TIPE de composition musicale

Avoir tout ce corpus de partitions PMX, c'était pratique quand j'ai voulu faire mon [TIPE de génération procédurale de musique par chaînes de Markov](http://jill-jenn.net/_static/works/un-algorithme-de-composition-musicale.pdf). Le programme prenait en entrée des partitions au format PMX et générait une partition PMX inédite, mesure par mesure.

{% img /images/music/markov.png %}

Quand j'ai voulu faire écouter ce que l'algorithme faisait au jury des ENS, ils m'ont dit :

> — On aimerait bien écouter mais pour ça il faudrait que votre portable reste dans la salle après l'oral.  
> — Ah ben non alors.

Notez que la musique de fond de *La Faute à l'algo* est également composée par une chaîne de Markov sur du code PMX, c'était d'ailleurs [le sujet de l'épisode 1 : génération procédurale](http://fautealgo.fr/ep1/) ! [Le code de `markov.py` est sur GitHub.](https://github.com/jilljenn/markov.py)

Voilà, et pour revenir à l'anniversaire de Trio ELM, sa vidéo la plus vue est : **Sis Puella Magica**, de *Puella Magi Madoka Magica*. Et si vous voulez écouter d'autres vidéos, c'est sur le site de [trioelm.com](http://trioelm.com) ! Joyeux anniversaire, [Sedeto](http://sedeto.fr) et [Lily](http://leslueursdelily.wixsite.com/leslueursdelily) !

{% youtube LFxfZqJD5I4 %}
