---
title: Rotten Tomatoes Catapult
author: Jill-Jênn
layout: post
permalink: /2012/08/06/rotten-tomatoes-catapult/
categories:
  - Cinéma
  - Code
---
Do you know [Rotten Tomatoes][1]? It's a review aggregator which measures the percentage of positive reviews of most films. I think it's really helpful if you want to watch a film without knowing anything about it (except a number), which can sometimes be vital (see ***12 Monkeys***). Thanks to it, I discovered ***Win Win*** (94%), ***El secreto de sus ojos*** (91%) or the documentary ***Exit Through the Gift Shop*** (96%), and I narrowly escaped *Hereafter* (46%) or *Nine* (37%). There are some subjective false positives though, like ***Norwegian Wood*** in my case (74% while I hated it).

 [1]: http://rottentomatoes.com

When I'm looking for film showtimes, I always use [Google Movies][2] rather than AlloCiné, because it gets to the point (no posters, no ads, no useless slideshows, just showtimes).

 [2]: http://google.com/movies

I made a [bookmarklet][3] which catapults Rotten Tomatoes ratings into a Google Movies page. It uses [the Rotten Tomatoes API][4], which is great (you need to register as a developer to get an API key) and jQuery.

 [3]: http://en.wikipedia.org/wiki/Bookmarklet
 [4]: http://developer.rottentomatoes.com

Here is a quick example, put your mouse over this image:

<div style="border:1px dashed #e2e2e2; margin: 0 auto 1.625em auto; background: url('/images/rt-catapult.png'); width: 365px; height: 505px; background-position: 0" onmouseover="this.style.backgroundPosition = '-365px';" onmouseout="this.style.backgroundPosition = 0;"></div>

As you can see, not all films are recognized by the API, and some ratings may not be available yet.

If you want to try it yourself, bookmark [this link][5], go to [this page][2], and click the bookmark.

 [5]: javascript:(function(){if(window.getGoogleFilms!==undefined){getGoogleFilms();}else{document.body.appendChild(document.createElement('script')).src='http://jill-jenn.net/js/rt.js?';}})();

*   [Browse the code][6]
*   [Learn more about bookmarklets: “Make Your Own Bookmarklets With jQuery”][7]

 [6]: http://jill-jenn.net/js/rt.js
 [7]: http://coding.smashingmagazine.com/2010/05/23/make-your-own-bookmarklets-with-jquery/