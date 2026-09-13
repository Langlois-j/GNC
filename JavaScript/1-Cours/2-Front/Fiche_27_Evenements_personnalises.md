# JavaScript cote navigateur : Evenements personnalises

Video : https://www.youtube.com/watch?v=PmrHg7q5raw

## Transcription

bienvenue dans ce nouveau chapitre je
0:01
vous propose de parler de la manière
0:03
d'émettre nous-même des événements en
0:05
Javascript donc on aimerait bien par
0:06
exemple sur notre système de to do list
0:08
pouvoir détecter quand une tâche est
0:10
supprimée donc on pourrait aimer de la
0:13
logique compliquée dans notre code mais
0:14
vous allez le voir le dôme nous permet
0:16
déjà de faire des choses qui sont plutôt
0:17
intéressantes avec notamment la
0:19
possibilité d'émettre nous-même nos
0:21
propres événements en effet on l'a vu
0:22
sur les champs ou sur à peu près
0:25
n'importe quel type d'éléments on a des
0:27
événements qui sont natifs mais on aura
0:29
la possibilité aussi de créer nous-même
0:31
nos propres événements alors pour cela
0:33
on va se baser dans notre fichier to do
0:35
list.js et on va s'imaginer que lorsque
0:37
l'on supprime un élément on veut émettre
0:39
un événement donc dans ce cas là on va
0:42
devoir toujours partir d'un élément
0:43
particulier donc nous on va on va partir
0:45
de notre lit et on va dire sur le l i
0:47
j'aimerais bien envoyer un événement
0:49
donc à ce niveau là on va pouvoir faire
0:51
un vice point element pour récupérer
0:54
notre élément et on pourra utiliser la
0:56
méthode dispatch event cette méthode
0:58
elle va prendre un seul para qui sera un
1:00
événement vous pouvez utiliser les
1:02
événements natifs mais vous pouvez aussi
1:04
créer vous-même vos propres événements
1:06
pour cela on utilisera nouvel objet qui
1:09
sont les custom events ces objets sont
1:11
construits à partir d'une chaîne de
1:12
caractères qui sera le nom de
1:13
l'événement donc on peut faire ici un
1:15
new custom event on va lui passer un
1:18
premier paramètre le l'événement des
1:21
lettres
1:22
voilà maintenant si on souhaite
1:23
s'abonner à cet événement là il faudra
1:26
tout simplement mais faire un Advent les
1:28
sœurs et écouter l'événement des lettres
1:29
donc on s'imagine que ici par exemple on
1:32
fait un vice-point dièse et les mains et
1:35
j'aimerais bien rajouter un lisseur sur
1:37
des lettres qui n'est pas un événement
1:38
standard du dôme mais ce n'est pas
1:40
gênant et je récupérerai ensuite
1:42
l'événement et cet événement pour
1:43
l'instant je vais faire une console
1:44
point log et voir de quoi il en retourne
1:47
si maintenant je me rends sur ma page et
1:49
que j'ouvre ma console lorsque je
1:51
supprime l'élément on voit bien que j'ai
1:53
mon custom event ici ce costam event va
1:55
contenir différentes propriétés qui
1:57
correspondent à un événement classique
1:59
on aura notamment le courant target par
2:01
exemple ne faites pas attention si la
2:03
console vous dit nul pour avoir essayé
2:05
si vous essayez de déboguer courante
2:07
target ça vous donnera bien la cible le
2:10
problème c'est que au moment où notre
2:12
console affiche les choses l'élément est
2:14
supprimé du Dôme et du coup le courant
2:15
target il nous le donne comme nul autre
2:18
petit détail le dispatch Event est
2:20
synchrones c'est-à-dire que lorsqu'on
2:21
fait un dispatcheven tous les
2:23
glisseneurs vont être exécutés de
2:24
manière synchrone et c'est que une fois
2:26
tous les disseneurs exécutés on passera
2:28
la tâche suivante donc si on avait du
2:30
code bloquant à ce niveau là on ne
2:32
supprimerait pas l'élément tant que les
2:33
disseneurs n'ont pas été déclenchés
2:34
c'est complètement différent des
2:36
événements natifs qui sont eux à
2:37
exécutés de manière asynchrone donc
2:39
lorsque vous faites un dispatch event ça
2:41
va être synchrone c'est un petit détail
2:42
mais ça peut avoir son importance de
2:44
temps en temps
2:45
ensuite en plus du nom de l'événement on
2:47
a la possibilité de passer un second
2:49
paramètre qui sera un objet d'option une
2:51
première option super intéressante c'est
2:52
die tail qui nous permet d'afficher plus
2:54
d'informations sur cet événement là donc
2:56
si on a besoin de passer des données
2:58
c'est grâce à cette propriété day
3:00
imaginons nous par exemple on initialise
3:03
l'attache à faire donc on va le faire
3:05
dès le dès la construction
3:08
voilà et on se dit ça serait intéressant
3:10
à ce niveau là de passer dans le détail
3:12
le l'attache que l'on vient de supprimer
3:14
si je fais ça lorsque je vais supprimer
3:17
une tâche on va voir que dans notre
3:19
événement si je remets voilà l'événement
3:21
directement on aura dans la partie
3:24
detail les informations sur la tâche
3:26
donc on récupérerait l'objet original
3:28
tout doux ensuite on a une autre
3:30
propriété qui est intéressante qui est
3:32
bubble qui va permettre de préciser si
3:35
notre événement a un système de
3:36
propagation alors pour prendre un
3:38
exemple concret imaginons que j'écoute
3:40
ce même événement sur carrément notre
3:43
body donc je vais faire un document de
3:45
point body point A des vent listener et
3:47
je vais écouter le même événement des
3:49
lettres ça prendra une fonction et dans
3:51
ce cas là je ferai une console point log
3:53
j'afficherai body suivi de mon événement
3:56
si j'essaie de supprimer un élément on
3:58
voit que ce console point log n'est pas
4:00
utilisé donc l'événement ne se propage
4:02
pas et il ne se propage pas parce qu'il
4:04
n'a pas de propriété bubbles qui est un
4:06
trou c'est ici je rajoute une propriété
4:08
bubble's et que je mets mes trous dans
4:11
ce cas là automatiquement lorsque je
4:12
supprime on voit que on a à la fois
4:14
l'événement qui est appelé sur notre
4:16
élément mais il est aussi appelé au
4:18
niveau du body parce que ça remonte vers
4:20
l'élément par an il faut savoir que
4:22
cette propriété n'existent pas que sur
4:24
les custom events c'est une propriété
4:25
qui est directement disponible au niveau
4:27
de events donc vous avez ce système de
4:29
bubbling qui est présente pour en fait
4:31
tous les événements par défaut donc par
4:33
exemple lorsque vous faites un clic bah
4:35
c'est quelque chose qui bubble qui monte
4:37
mais certains événements vont ne pas
4:39
être propagés parce qu'ils ont le Bubble
4:40
s'affols donc si vous voulez vérifier si
4:42
un événement est capable de propager ou
4:44
non vous pouvez regarder cette propriété
4:45
là pour avoir plus d'informations je
4:47
sais pas si par contre c'est indiqué
4:48
dans la documentation à première vue
4:50
j'ai pas eu l'impression mais je sais
4:53
pas si vous pouvez voir en un clin
4:55
d'oeil quel événement
4:56
découpage et quels événements ne se
4:57
propagent pas
4:59
donc ensuite on a une autre propriété
5:01
qui est cancellable qui permet de
5:03
préciser est-ce que finalement cet
5:05
événement peut être annulé ou pas si
5:07
vous mettez un cancellable à trous vous
5:09
allez avoir des informations
5:10
supplémentaires et vous allez surtout
5:12
avoir la possibilité d'utiliser la
5:13
méthode prévente des folt donc par
5:15
exemple je vais lui dire dans mon
5:16
événement lorsque ici je récupère mon
5:19
événement j'ai envie d'utiliser la
5:21
méthode prévente des fautes voilà
5:24
l'avantage c'est qu'après on peut
5:26
vérifier est-ce que l'événement a été
5:28
annulé par exemple à ce niveau là je
5:30
pourrais me dire je vais sauvegarder
5:31
l'événement en amont je vais l'appeler
5:33
event je vais ensuite le passer à mon
5:36
dispatch event donc tous les liceneurs
5:37
vont se déclencher dessus et certains
5:39
lisseurs pourraient faire un prévente
5:41
des fold après je peux lui dire est-ce
5:43
que sur cet événement on a le defold
5:46
preventide si on a le défolt preventide
5:48
ça veut dire que quelqu'un a fait un
5:50
préventifold et du coup je ne souhaite
5:52
pas appliquer le comportement par défaut
5:54
qui serait la suppression de l'élément
5:56
donc là je pourrais faire un return pour
5:58
empêcher la suite de mon script de
5:59
s'exécuter si j'essaie de supprimer un
6:01
élément on voit qu'il n'y a plus aucune
6:03
suppression parce qu'ici j'ai mis un
6:05
pré-vent défolt si je retire ce présente
6:07
des volts la suppression refonctionne
6:08
donc quand c'est labre vous permet
6:10
d'indiquer que l'événement peut être
6:12
annulé grâce à un prévode donc voilà
6:14
pour les trois propriétés à connaître
6:15
sur les événements dit-elle pour envoyer
6:17
des informations bubble pour propager
6:19
l'événement aux éléments parents ou
6:22
propager dans notre sens si on a des
6:23
éléments en mode capture et quand c'est
6:25
lable qui va permettre l'utilisateur de
6:26
faire un prévoyance des volts si ça
6:28
permet d'annuler des comportements par
6:29
défaut nous dans notre cas par exemple
6:30
on pourrait annuler la suppression si on
6:33
détecte certains comportements
6:35
maintenant comment on peut les utiliser
6:36
dans des cas réels les événements vont
6:39
être super intéressant lorsqu'on a
6:40
besoin de faire des communications à
6:42
enfants par an donc typiquement nous ici
6:44
on a envie de penser que notre composant
6:46
qui représente un élément dans notre
6:48
liste c'est un composant qui est isolé
6:50
du coup pour qu'il communique avec le
6:52
reste de notre application on va lui
6:53
faire émettre des messages ensuite ça
6:55
sera à notre classe d'où listen de voir
6:57
si elle souhaite agir ou non sur ces
6:59
événements là donc ça nous permet de
7:01
vraiment concevoir quelque chose d'isolé
7:03
donc on va regarder le comportement que
7:05
l'on a fait on va dire que par exemple
7:06
lorsque l'on supprime une to-do list
7:08
effectivement on va émettre l'événement
7:09
des lettres de la même manière lorsque
7:12
l'on togole une checkbox on pourrait lui
7:15
dire ça serait intéressant d'émettre un
7:16
événement pour dire qu'il y a eu un
7:18
changement
7:19
donc là par exemple on pourrait envoyer
7:21
une méthode toggle
7:23
on lui passerait toujours la to do on
7:25
lui demanderait de Bubble et ensuite là
7:27
le cancella je vous avouerai qu'il
7:28
serait pas très utile voilà donc
7:30
maintenant hop notre composant est
7:33
capable d'émettre des événements en
7:34
fonction de différentes situations qui
7:36
lui arrivent donc on peut le replier
7:37
complètement et on peut se baser sur
7:39
notre élément parent pour pouvoir
7:41
capturer ses événements là donc au
7:43
niveau de notre à peine on ne va pas
7:44
être obligé d'écouter directement sur
7:46
l'élément vu qu'on admis que tout
7:47
pouvait meublé on va dire j'aimerais
7:50
bien sur mon liste élément
7:53
venir écouter quand est-ce qu'un élément
7:55
a été supprimé donc écoutez l'événement
7:57
des lettres dans ce cas là je recevrai
7:59
un événement et la seule chose qui
8:01
m'intéresse sur l'événement c'est le
8:03
Detail donc le die tail je vais appeler
8:05
ça tout doux et ensuite hop je mets ma
8:08
petite fonction fléchée donc là vous
8:09
voyez c'est un cas d'utilisation de la
8:10
destructuration et je vais faire une
8:12
console.log tout doux pour voir la tâche
8:14
en question
8:16
si maintenant j'essaie de supprimer un
8:18
élément j'obtiens bien cette to do là ce
8:20
qui pourrait être intéressant ça serait
8:21
du coup de mettre à jour à en interne la
8:24
liste des tâches donc je pourrais lui
8:26
dire j'aimerais bien que tu mettes à
8:27
jour en interne tout doux et que tu lui
8:31
dises de faire un vis point tout doux
8:34
et je veux que tu filtres en retirant
8:36
les tâches et en ne gardant que les
8:38
tâches qui sont différentes de la tâche
8:40
sur laquelle on est si ensuite je fais
8:42
un console point log de vis point dièse
8:46
tout doux mais dans ce cas là on va voir
8:49
que si je supprime une tâche hop on a
8:51
notre tableau qui diminue en taille de
8:54
la même manière je pourrais lui dire
8:55
lorsque on a une checkbox qui est coché
9:00
donc lorsqu'on a un toggle j'aimerais
9:02
bien que tu modifies la tout doux en
9:03
question donc là on pourrait modifier
9:05
l'objet vu qu'on modifie une propriété
9:07
de l'objet on fait une mutation et on
9:09
fera un tout doux point compliquid
9:11
= différent de tout doux points
9:13
completide donc on est en train de
9:14
changer si c'était vrai ça devient folle
9:16
c'est si c'est folle ça devient vrai
9:17
donc si je coche tout ça on changerait
9:20
les valeurs à l'intérieur de notre objet
9:21
je vais peut-être mettre dans les deux
9:23
cas une console point log
9:25
de vis pointe tout doux pour suivre un
9:27
petit peu les changements voilà mais si
9:29
maintenant je coche cette case là et
9:30
cette case là je vois pas de console.log
9:32
en console parce qu'effectivement en bas
9:34
j'ai créé l'événement mais j'ai
9:36
complètement oublié de le dispatcher
9:37
qu'on ne va pas aller loin si on ne
9:39
dispache rien hop je dispache mon
9:42
événement et voilà donc si je recoche
9:45
certaines cases on va voir que au fur et
9:47
à mesure mon tableau est mis à jour donc
9:49
il ne change pas de taille par contre si
9:51
je déplie mes éléments je vois que là je
9:53
vais avoir bien un complotides à trou
9:55
pour l'ensemble de mes propriétés ça me
9:57
permet comme ça directement au niveau du
9:59
parent de pouvoir suivre l'évolution de
10:01
mes tâches et de pouvoir mettre à jour
10:03
mon tableau pour pouvoir ensuite le
10:05
réutiliser plus tard donc voilà comment
10:07
vous pouvez utiliser les événements donc
10:09
dès que vous avez besoin de faire
10:10
communiquer un élément enfant avec son
10:12
parent les événements du navigateur sont
10:16
très utiles je ne voulais pas forcément
10:18
préciser mais vous pouvez aussi utiliser
10:19
dans les événements grâce au custom
10:22
event des noms qui sont déjà utilisés
10:25
moi personnellement j'aurais tendance à
10:26
vous déconseiller de faire ça parce que
10:28
le problème c'est que quand on écoute un
10:30
événement de change on s'attend à ce que
10:31
ça soit fait par exemple sur input on
10:33
s'attend à avoir différentes propriétés
10:35
par exemple si on écoute un quiddown on
10:37
s'attend à avoir une propriété clé si
10:39
vous utilisez un custom event vous vous
10:41
retrouvez avec un événement personnalisé
10:42
qui a le même nom que notre événement
10:43
mais qui n'a pas forcément les mêmes
10:45
propriétés ce qui peut être un petit peu
10:46
perturbant donc personnellement j'aurais
10:48
tendance à vous conseiller de mettre des
10:49
noms qui sont différents des non natifs
10:51
mais voilà pour cet exemple là donc
10:54
j'espère que ce petit exemple vous aura
10:55
permis de comprendre un petit peu
10:56
comment ça peut fonctionner et pourquoi
10:58
ça peut être utile des maîtres des
10:59
custom event sur votre code et je vous
11:02
donne rendez-vous dans le prochain
11:03
chapitre
