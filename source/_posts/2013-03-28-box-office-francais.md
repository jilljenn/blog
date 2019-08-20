---
title: Box-office français
author: Jill-Jênn
layout: post
permalink: /2013/03/28/box-office-francais/
categories:
  - Cinéma
  - Code
---
En cherchant le score au box-office du film ***[Les Enfants loups, Ame et Yuki][4]***, je suis tombé sur [une page avec des astérisques à la place des chiffres][1]. Pour voir les chiffres, il faut avoir un compte payant.

 [1]: http://www.cbo-boxoffice.com/v3/page000.php3?Xnumitem=110&inc=fichemov.php3&fid=20547&t1=2

Seulement, voilà : comme ils ont laissé les jauges, et qu'on dispose du nombre de chiffres de chaque nombre d'entrées, il est possible de déterminer une fourchette pas trop floue sur le score au box-office ! Passez votre souris sur l'image suivante :

<div style="margin: 0 auto 1.625em auto; background: url('/images/boxoffice.png'); width: 550px; height: 246px; background-position: 0" onmouseover="this.style.backgroundPosition = '-550px';" onmouseout="this.style.backgroundPosition = 0;"></div>

Pour l'essayer, enregistrez **[ce lien dans vos signets][2]**, allez en bas de **[cette page][1]** et cliquez sur le signet.

 [2]: javascript:(function(){if(window.getGoogleFilms!==undefined){getGoogleFilms();}else{document.body.appendChild(document.createElement('script')).src='http://jill-jenn.net/js/boxoffice.js?';}})();

Pour ceux que ça intéresse, j'avais aussi fait [un bookmarklet pour récupérer les scores de Rotten Tomatoes][3].

 [3]: /2012/08/06/rotten-tomatoes-catapult/
 [4]: /2013/02/01/les-enfants-loups-ame-et-yuki/