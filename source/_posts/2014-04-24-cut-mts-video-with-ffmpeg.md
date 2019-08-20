---
title: Cut MTS video with ffmpeg
author: Jill-Jênn
layout: post
published: false
permalink: /2014/04/24/cut-mts-video-with-ffmpeg/
categories:
  - Cinéma
---
Pour les vidéos du concert retrogaming, j'ai utilisé ffmpeg.

    # Partie I
    ffmpeg -ss 00:04:07.5 -i 1.mp4 -t 00:00:05 -ss 56 -i god.m4a -t 00:00:05 -c copy -map 0:v:0 -map 1:a:0 p1.mp4
    ffmpeg -i 1.MTS -itsoffset 192 -i god.m4a -c copy -map 0:v:0 -map 1:a:0 p1.mp4

    # Partie II
    ffmpeg -i 2.MTS -ss 00:06:16 -i god.m4a -map 0:v:0 -map 1:a:0 -c copy p2.mp4

    # Partie III
    ffmpeg -i 3.MTS -ss 00:22:24.7 -i god.m4a -map 0:v:0 -map 1:a:0 -c copy p3.mp4

    # (Avec réencodage)
    ffmpeg -ss 00:04:07.5 -i 1.mp4 -t 00:00:10 -ss 56 -i god.m4a -t 00:00:10 -map 0:v:0 -map 1:a:0 out.mp4
    ffmpeg -ss 00:07:26 -i p1.mp4 -t 00:00:06 wind2.mp4
    ffmpeg -ss 00:03:23.2 -i p3.mp4 -t 00:00:06 gate2.mp4
    ffmpeg -ss 00:06:52 -i p3.mp4 -t 00:00:06 elm2.mp4
    ffmpeg -ss 00:10:56.5 -i p3.mp4 -t 00:00:06 fighting2.mp4
    ffmpeg -i p1.mp4 -ss 00:06:26 -t 00:02:56 -async 1 wind2.mp4

    # Cuts
    ffmpeg -ss 00:04:08 -i p1.mp4 -t 00:02:18 -c copy merry-go-round.mp4
    ffmpeg -ss 00:06:26 -i p1.mp4 -t 00:02:56 -c copy wind.mp4
    ffmpeg -ss 00:04:20 -i p2.mp4 -t 00:02:16 -c copy sis-puella-magica.mp4
    ffmpeg -ss 00:06:44 -i p2.mp4 -t 00:02:11 -c copy vamo-alla-flamenco.mp4
    ffmpeg -ss 00:09:12 -i p2.mp4 -t 00:04:22 -c copy yasashii-ryoute.mp4
    ffmpeg -ss 00:13:47 -i p2.mp4 -t 00:01:43 -c copy to-zanarkand.mp4
    ffmpeg -i 3.MTS -ss 00:22:24.7 -i god.m4a -t 00:03:12 -map 0:v:0 -map 1:a:0 -c copy mononoke-hime.m2ts
    ffmpeg -ss 00:03:23.3 -i p3.mp4 -t 00:03:15 -c copy gate-of-steiner.mp4
    ffmpeg -ss 00:06:52 -i p3.mp4 -t 00:03:46 -c copy ELM.mp4
    ffmpeg -ss 00:10:56 -i p3.mp4 -t 00:03:23 -c copy those-who-fight.mp4
    ffmpeg -ss 00:14:40 -i p3.mp4 -t 00:02:10 -c copy gravity.mp4
    ffmpeg -ss 00:17:00 -i p3.mp4 -t 00:01:40 -c copy gym-leader-battle-theme.mp4
    ffmpeg -ss 00:19:40 -i p3.mp4 -t 00:04:00 -c copy book-of-life.mp4
    ffmpeg -ss 00:24:27 -i p3.mp4 -t 00:02:15 -c copy shuffle-or-boogie.mp4
    ffmpeg -ss 00:26:49 -i p3.mp4 -t 00:01:43 -c copy lucky-channel-game-corner.mp4
    ffmpeg -ss 00:28:32 -i p3.mp4 -t 00:04:03 -c copy itsumo-nando-demo.mp4
    ffmpeg -ss 00:32:46 -i p3.mp4 -t 00:02:04 -c copy memory-of-waves-and-light.mp4
    ffmpeg -ss 00:34:58 -i p3.mp4 -t 00:05:14 -c copy laputa.mp4
    ffmpeg -ss 00:40:14 -i p3.mp4 -t 00:03:28 -c copy sore-feet-song.mp4
    ffmpeg -ss 00:43:46 -i p3.mp4 -t 00:02:14 -c copy zelda.mp4

    # (Tests)
    ffmpeg -i 1.MTS -itsoffset -253 -i god.m4a -t 00:10:20 -map 0:v:0 -map 1:a:0 -c copy out.m2ts
    ffmpeg -itsoffset -10 -i 1.MTS -i god.m4a -t 00:00:10 -map 0:0 -map 1:0 -c copy out.m2ts
    ffmpeg -i 1.MTS -itsoffset -10 -i 1.MTS -t 00:00:10 -map 0:1 -map 1:0 -c copy out.m2ts
    ffmpeg -i 1.MTS -itsoffset 10 -i god.m4a -t 00:00:10 -map 0:v:0 -map 1:a:0 -c copy out.m2ts
