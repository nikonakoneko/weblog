# Herzlich wilkommen auf der Seite der Nikonako Katze!

## (Re)introducing me and… this thing you are reading right now

I am some random nerd Geekin'n'Hackin (sex, drugs and segmentation faults!)
around and I don't really like to speak English dialect, this is pourquoi je
continuerai dans n'importe quelle autre [dialecte
indoeuropéen](https://upload.wikimedia.org/wikipedia/commons/4/4f/IndoEuropeanTree.svg).

- Com n'[Oswald
  Spengler](https://en.wikipedia.org/w/index.php?title=Oswald_Spengler&oldid=1213605401)
  ho va ser, aspir a esdevenir un *polímata*. Mas, contràriament a el, **no me
  plai pas** el *Nationalsozialismus*.
- So wie der [Richard Stallman](https://de.wikipedia.org/wiki/Richard_Stallman),
  ich die [Proprietäre
  Software](https://de.wikipedia.org/wiki/Propriet%C3%A4re_Software) hasse.
  Mais, [contrairement à lui](Proprietäre Software), je ne confie pas en l'État.

## Foire aux questions

- **¿Por qué 「猫」?**
   - *Per çò que los cats negres agaitan lo patron dempuèi los maquis*

- **Però il giapponese non è indoeuropeo…**
   - Tant me fot! I això que tu dius tampoc és cap pregunta… çò ací és una
     **F·A·Q**, avec un gros **Q** de **Questions**.

---

- **Pourquoi ce… heu.. site ouèb… un peu… craignos?**
   - Pour essayer de trouver d'autres membres de la diaspora de licornes de la
     réseausphère.

- **Tu sais que t'es vraiment chelou, mec?**
   - I tant, i tant. Quaero mihi similes et adiungor pravis!

*wip wip wip*

## Journal pas tant journalier

### OpenZFS & Linux & virtiofs & DAX = false 

_Pissed off_ comme ils disent. Je ne sais même plus pourquoi j'ai voulu formater
mes disques durs avec ZFS… Tot i que tingui unes quantes funcionalitats molt
gaudibles, — que, de fet, n'estic gaudint llur (ab)ús — me'n falta una prou
cabdal per al meu _cāsus ūsūs_.

Je m'explique. Mon espace de stockage est principalement dedié à des machines
virtuelles et je préfère utiliser virtiofs pour qu'elles puissent y accéder
plutôt que d'avoir recours à l'interface de bloque de virtio. Puis, afin de
court-circuiter des couches d'abstractions redondantes entre l'hôte et l'invité,
— et gagner ainsi en performance — virtiofs peut faire usage de l'interface
d'accés directe à la mémoire (DAX) de Linux _à condition que le système de
fichier sous-jacent à virtiofs en soit capable_… bien évidement, fallait donc
que ce ne soit [pas le cas avec
OpenZFS](https://github.com/openzfs/zfs/issues/9986)… ¡Me cago en todo!
