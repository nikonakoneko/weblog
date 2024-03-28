---
layout: post
author: Felis linuxensis
title:  OpenZFS & Linux & virtiofs & DAX = 0
categories:
- Computer
- Linux
tags:
- ZFS
- storage
- virtio
- virtualisation
---

_Pissed off_, comme ils disent. Je ne sais même plus pourquoi j'ai voulu
formater mes disques durs avec ZFS… Tot i que tingui unes quantes funcionalitats
molt gaudibles, — que, de fet, n'estic gaudint llur (ab)ús — me'n falta una prou
cabdal per a mon _cāsus ūsūs_.

Je m'explique. Mon espace de stockage est principalement dédié à des machines
virtuelles et je préfère utiliser
[virtiofs](https://docs.kernel.org/filesystems/virtiofs.html) pour qu'elles
puissent y accéder plutôt que d'avoir recours à l'interface de bloque de virtio.
Puis, afin de court-circuiter des couches d'abstractions redondantes entre
l'hôte et l'invité — et gagner ainsi en performance, — virtiofs peut faire usage
de l'interface d'accés directe à la mémoire
([DAX](https://docs.kernel.org/filesystems/dax.html)) de Linux _à condition que
le système de fichier qui lui est sous-jacent en soit capable_… bien évidement,
fallait donc que ce ne soit [pas le cas avec
OpenZFS](https://github.com/openzfs/zfs/issues/9986)… ¡Me cago en todo!
