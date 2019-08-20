---
title: Relaxations pendant les vacances
author: Jill-Jênn
layout: post
published: true
permalink: /2015/08/29/relaxations-pendant-les-vacances/
categories:
  - Algorithmique
  - Start-up
  - Code
---

(Ne vous méprenez pas, par « relaxation » j'entends [la définition au sens de la théorie des graphes](https://en.wikipedia.org/wiki/Bellman–Ford_algorithm).)

Je me pose le problème suivant : si j'essaie d'aller d'une ville **A** à une ville **B**, existe-t-il une ville **X** par laquelle il serait intéressant de passer pour casser le prix ? (Car, au risque de vous surprendre, les tarifs des vols ne respectent pas l'inégalité triangulaire.)

**Update 29/08.** [Ryan Lahfa](https://github.com/RaitoBezarius) m'a fait découvrir le site allemand [Tripdelta](https://tripdelta.com) qui accomplit cette tâche merveilleusement ! Mais ce n'est pas une raison pour ne pas coder quelque chose nous-mêmes !

**Update 30/08.** Tripdelta c'est une équipe basée à Cologne, 2 développeurs + 1 business dev. Ça fait 4 mois qu'ils existent, ils ont le calendrier des prix et la carte des prix sur la to-do list. Actuellement ils utilisent l'API [Skyscanner](http://www.skyscanner.fr) (comme [Kenweego](http://kenweego.com/fr) et sûrement la majorité des sites du genre). Je vais leur proposer des missions :-)

Par exemple, le 9 septembre 2015 :

{% img /images/gf-triangle.png %}

46 + 32 = <font style="color: #347009">78 €</font> au lieu de <font style="color: #e12727">138 €</font>, ça les vaut ! Certes, c'est plus long. Mais même un vol de Paris à Édimbourg s'arrêtant 3 h 45 à Manchester coûte 115 € (Air France puis FlyBE).

## Google Flights

Ça faisait un bail que je voulais coder un script qui pour un budget donné indique les destinations possibles : on ne dit pas où on veut aller, seulement combien on est prêt à mettre.

En fait, Google Flights fait déjà ça.

### Carte des prix

Visiblement, ça ne coûtait pas cher de voyager en Europe le 19 août 2015.

{% img /images/gf-map.png %}

### Calendrier des prix

Il indique aussi selon le jour où on part quel est le meilleur prix. C'est plus puissant que le « ± 3 jours » que l'on voit habituellement sur les sites de comparateurs de vol.

Tiens, ça ne coûte que 32 $ d'aller de Marseille à Édimbourg le 12 octobre !

{% img /images/gf-calendar.png %}

## API

Il n'en existe pas (encore) d'API, mais on peut interroger le serveur RPC avec des requêtes POST. Par exemple :

    $ gnutls-cli google.com

    POST /flights/rpc HTTP/1.1
    Host: www.google.com
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
    Content-Type: application/json; charset=utf-8
    X-GWT-Permutation: XXX
    Content-Length: 304
    Connection: keep-alive
    Pragma: no-cache
    Cache-Control: no-cache

    [,[[,"fs","[,[,[[,[\"CDG\",\"ORY\",\"BVA\",\"XPG\"],,\"2015-09-14\"]],,,,,,,1,,,,,,,,,1,[[,3,1]]],[]]","1518231496671724",9]],[,[[,"b_al","no:64"],[,"b_ahr","no:s"],[,"b_ca","52:67383"],[,"f_ut","search;f=CDG,ORY,BVA,XPG;d=2015-09-14;r=2015-09-18;tt=o;mc=e"],[,"b_am","fs"],[,"b_qu","0"],[,"b_qc","1"]]]]

Réponse :

    [,[[,"fs","[,[[,\"CDG\",\"Paris-Charles De Gaulle\",\"Paris\",\"PAR\",\"France\",49.0097222,2.54777778,,\"FR\"],[,\"ORY\",\"Paris Orly\",\"Paris\",\"PAR\",\"France\",48.7233333,2.37944444,,\"FR\"],[,\"BVA\",\"Paris Beauvais-Tille\",\"Paris\",\"PAR\",\"France\",49.4544444,2.11277778,,\"FR\"],[,\"XPG\",\"Paris Gare du Nord Railway Station\",\"Paris\",\"PAR\",\"France\",48.8808333,2.35527778,,\"FR\"]],,[[,\"PAR\",\"Paris\",48.856614,2.3522219000000004,[\"CDG\",\"ORY\",\"BVA\",\"XCR\",\"XPG\",\"LBG\",\"POX\",\"VIY\"],[\"CDG\",\"ORY\",\"BVA\",\"XPG\"],\"France\",,\"FR\"]],,\"\",,,,,[[,6,,0]],,,,,,,,,,0]",,1]],[,[[,"b_sshk","wl_467279cc"],[,"b_ssfgip","hIymy7tx8nKn7sfxANtGtg"]]]]

Trop aimable. En gros, je lui ai envoyé quelque chose contenant « CDG », il m'a envoyé quelque chose contenant « Paris-Charles De Gaulle ». On va dire que c'est un début.

Un type a rédigé [un post de blog](http://www.nohup.in/blog/using-json-google-flights) où il essaie de comprendre comment fonctionne l'API.

Si ça vous dit de m'aider à construire ce petit script, votre aide est la bienvenue. Je suis tellement persuadé qu'on serait capables de trouver des vols Paris → X → Marseille moins chers que les tarifs de la SNCF !

### Sites similaires

- [Liligo](http://www.liligo.co.uk/mapping-out-the-deals/) a une carte des prix, très discrète (merci Alexis Descamps).
- [Kenweego](http://kenweego.com/) aussi, c'est fait par un Français.
- [Momondo](http://momondo.com/) c'est danois, ils ont [une API](http://www.momondo.com/Momondo.asmx?op=WhereToGo) (merci Luc Rocher).

Et sinon un peu de méta, vous voulez voir [quelle gueule a le code de ce post de blog](https://bitbucket.org/jilljenn/blog/raw/9c1457e4d5716d538976ca06fbe5fe25b94a1dfc/_posts/2015-08-29-relaxations-pendant-les-vacances.md) ? Merci [Octopress](http://octopress.org).
