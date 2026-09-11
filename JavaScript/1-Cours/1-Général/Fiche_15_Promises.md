# Apprendre le JavaScript : Les timers

Video : https://www.youtube.com/watch?v=05mKXSdkCJg

## Transcription

bienvenue dans ce nouveau chapitre nous
0:01
allons parler des promesses qui sont une
0:03
notion assez importante qui a créé à la
0:05
synchrone que l'on a vu dans le chapitre
0:06
précédent on l'a vu le principal
0:07
problème avec la synchrone c'est qu'on
0:09
se retrouve très souvent à avoir des
0:10
Call backs en école bagues en école back
0:12
et écrire du code comme ça ce n'est pas
0:14
pérenne pour pour le long terme donc
0:16
heureusement dans le JavaScript on a des
0:18
objets qui vont permettre justement de
0:20
représenter ce côté à synchrone et de
0:22
pouvoir travailler plus facilement avec
0:23
et ses objets ce sont les promesses
0:25
alors pour les utiliser il va falloir
0:27
créer une nouvelle instance de l'objet
0:29
promise donc on fait un constat on va
0:32
l'appeler ici P et on fera mieux promise
0:36
au niveau de son constructeur les
0:37
promesses attendent un paramètre qui
0:39
sera une fonction qui aura deux
0:42
paramètres un premier qui s'appellera
0:43
resolve et un second qui s'appelera
0:45
reggate en général on utilisera ces noms
0:48
pour ces deux paramètres là resolve sera
0:50
une fonction que l'on appellera pour
0:51
dire que notre promesse a été résolue
0:53
donc comme dans la vraie vie si on
0:55
respecte notre promesse on dira voilà là
0:57
à ce moment-là je viens de la respecter
0:59
et donc j'utiliserai resolve si jamais
1:01
on réalise que la promesse on ne peut
1:03
pas la tenir parce que c'est un truc qui
1:04
est imposable mais dans ce cas là on
1:06
utilisera la méthode reeject donc nous
1:08
ici on va s'imaginer une promesse qui se
1:10
résout tout de suite et on va utiliser
1:11
la méthode resolve et en lui passera une
1:13
valeur et on peut même lui en passer
1:15
plusieurs donc là on a une promesse qui
1:18
s'autorise si vous avez besoin de plus
1:20
d'informations sur les promesses comme
1:22
d'habitude il nous faudra pas hésiter à
1:24
faire un petit tour sur la documentation
1:25
et surtout sur la partie référence pour
1:27
voir les différentes méthodes et on voit
1:29
qu'il y a pas mal de méthodes qui sont
1:30
directement disponibles sur l'objet
1:32
promise mais nous ce qui va nous
1:33
intéresser c'est ce qui a trait au
1:34
prototype alors déjà on regarder
1:36
qu'est-ce qui qu'est-ce qui nous affiche
1:38
en console donc on va faire une console
1:40
point loc de P et on va regarder notre
1:42
console donc on voit qu'on nous dit
1:44
c'est un objet promise et le navigateur
1:46
il a une petite manière particulière de
1:48
nous expliquer un petit peu à quoi
1:50
ressemble cette promesse il nous met
1:51
qu'elle a été full field avec la valeur
1:53
4 si je sais de faire la même promesse
1:55
que je rejette mais dans ce cas là on me
1:58
dit que c'est une promesse qui était
1:59
rejetée donc c'est une promesse qui n'a
2:01
pas été respectée et elle a été rejetée
2:03
avec avec la valeur 4 alors maintenant
2:05
c'est bien mais moi dans la suite de mon
2:07
script j'aimerais bien justement savoir
2:09
est-ce que la promesse a été résolue ou
2:11
non donc pour cela on a deux méthodes
2:13
que l'on peut utiliser sur les promesses
2:14
on a une première méthode veine cette
2:17
méthode prend en paramètre un callback
2:19
que l'on appellera et ce callback
2:22
prendra en paramètre les valeurs
2:24
renvoyées lors de la résolution de la
2:25
promesse donc nous typiquement ici on
2:27
aurait un nombre et par exemple je
2:29
pourrais lui dire bah lorsque cette
2:31
promesse a été résolue j'aimerais bien
2:33
que tu m'affiche le nombre et ensuite de
2:36
la valeur de ce nombre là et là ça va me
2:38
donner la valeur 4
2:40
si jamais une promesse échoue on peut
2:42
capturer cet échec en utilisant la
2:45
méthode catch vous remarquez que ça
2:47
ressemble un petit peu au travail catch
2:48
c'est le même principe une promesse peut
2:50
ne pas être respectée et dans ce cas-là
2:52
on va pouvoir capturer cette échec là et
2:54
là on va faire une console point log et
2:56
on va faire échec et on va regarder à
2:59
quoi ça ressemble donc ici je vais
3:01
utiliser ridgeject et on va voir que
3:03
c'est bien catch qui est appelé avec
3:05
cette valeur là
3:07
alors si on regarde le retour de ce p.4
3:09
ou même du p.ven on va voir que le
3:12
retour lui-même de ces méthodes là c'est
3:14
une promesse donc ce qu'il est possible
3:16
de faire c'est de faire les choses de la
3:18
manière suivante on va lui dire
3:21
si la promesse a bien été résolue on
3:23
aura un nombre que l'on va afficher
3:27
mais par contre si jamais la promesse
3:29
échoue dans ce cas là on aura une erreur
3:33
par exemple et on pourra faire une
3:35
console point log
3:36
erreur
3:38
et utiliser ensuite l'erreur donc on
3:40
peut enchaîner les choses comme ça
3:42
moi ici il me dit qu'il ne connaît pas
3:44
eux effectivement il faut mettre un N
3:46
donc la promesse fonctionne c'est le vin
3:48
qui est appelé la promesse échoue c'est
3:51
le catch qui est appelé
3:53
alors là en l'état vous dites ouais mais
3:55
ça a pas l'air de résoudre le problème
3:56
des callbacks parce que finalement tu as
3:58
un call back le principal avantage c'est
4:00
que ce que l'on fait dans le vein et
4:01
aussi ce que l'on fait dans le catch
4:02
peut continuer à être utilisé imaginons
4:05
à ce niveau là je me décide de retourner
4:07
5 donc en fait je lui dis quand la
4:10
promesse est résolue je veux exécuter ce
4:12
code là qui retourne 5 donc ça ça nous
4:15
donne encore une fois une promesse et on
4:17
peut continuer à enchaîner les choses
4:19
par exemple on peut lui dire bon ben
4:20
quand cette nouvelle promesse est
4:21
résolue j'aimerais bien faire encore une
4:24
fois une console point log on va mettre
4:26
le nombre 2 pour pouvoir faire la
4:28
différence
4:29
et ensuite on mettra la valeur de ce
4:31
nombre là et tout ça on le cache donc si
4:34
je sauvegarde on voit que ça va me
4:36
donner ici une erreur parce que la
4:37
promesse a été échouée on fait qu'on a
4:40
un reggaject mais si je la résolve on va
4:43
voir les deux consoles point log donc
4:44
l'avantage c'est que c'est beaucoup plus
4:46
facile d'enchaîner les choses et en
4:48
général on va utiliser une syntaxe voilà
4:50
hop on ferme on va mettre en forme de
4:52
cette manière là les choses les unes à
4:55
la suite des autres c'est un petit peu
4:56
plus facile de comprendre la logique
4:58
donc là lorsqu'il y a une résolution ça
5:00
retourne quelque chose et vu que ça
5:02
retourne quelque chose ça renvoie une
5:03
nouvelle promesse qu'on peut aussi
5:04
écouter pour voir si elle est résolue si
5:07
je ne mets rien à ce niveau là le second
5:09
veine sera quand même appelé mais avec
5:11
la valeur indie find vu que la fonction
5:12
ne retourne rien elle retourne à defight
5:15
l'intérêt aussi c'est que ici je peux me
5:17
dire ah bah là il y a un petit problème
5:19
par exemple j'avais pas prévu ce coup là
5:22
et je vais mettre ici échec
5:24
si je fais ça on va voir qu'il y a deux
5:26
consoles points lo qui vont être
5:27
activées il y a celui-ci vu que notre
5:29
promesse a bien été résolue mais vu que
5:31
dans le callback de la première
5:32
résolution on a une erreur il va
5:34
considérer que cette nouvelle promesse
5:35
qui a un résulte est en erreur et du
5:37
coup on peut cacher cette erreur là donc
5:40
on aura la fois ce code là et ce code là
5:42
qui va être exécuté et de la même
5:45
manière si on continue à être encore
5:46
plus plus fou on peut ici lui dire en
5:49
fait il faut que tu retournes 2 et dans
5:51
ce cas là le résultat du catch c'est
5:52
encore une promesse que je peux aussi
5:54
capturer lui dire bon ben si ça ça a
5:56
bien marché je veux encore faire une
5:58
console point log et dans ce cas là ça
6:00
nous donne RA2 en console parce que le
6:02
retour du catch nous renvoie une
6:04
promesse qui est résolue de cette
6:06
manière là donc cette manière d'écrire
6:08
les choses me permet en fait d'avoir
6:09
toujours des callbacks ça c'est toujours
6:11
un problème mais on va voir qu'il y a
6:12
une syntaxe qui permet de remédier à ce
6:13
problème là mais nous permet surtout de
6:15
représenter du code séquentiel beaucoup
6:17
plus facilement
6:19
la de la même manière lorsque vous
6:21
faites un retour ça peut être
6:22
directement une valeur et dans ce cas là
6:24
cette valeur sera résolue directement et
6:26
on appellera le vin suivant soit ça peut
6:28
aussi être une nouvelle promesse mais on
6:31
va faire un exemple juste après avec les
6:32
timers une dernière chose on a une
6:34
troisième méthode que l'on peut utiliser
6:35
sur les promesses qui est finalement
6:38
quelque chose qui va être exécuté quoi
6:41
qu'il arrive c'est à dire que la
6:42
promesse échoue que la promesse
6:43
réussisse ça on l'affiche tout le temps
6:45
donc là on voit que ça va nous afficher
6:48
à AA si on n'avait pas le VN et qu'on
6:50
laissait le catch agir le AAA serait
6:52
toujours affiché donc le finali va être
6:54
exécuté quoi qu'il arrive que la
6:56
promesse soit résolue ou non
7:17
donc tout de suite on met le resolve et
7:19
le rejet
7:23
et hop on n'oublie pas la petite flèche
7:25
plutôt que de directement mettre un
7:27
resolve de 4 on va utiliser le 7e
7:31
on va lui dire d'exécuter une fonction
7:33
et dans cette fonction fera un résolve
7:37
et on va lui demander d'attendre pendant
7:38
une durée déterminée cette durée en la
7:41
passera en paramètre de notre fonction
7:43
wait l'histoire d'avoir un paramètre
7:45
dans le résolve je vais lui dire de
7:47
résolve avec la durée de notre timer et
7:50
on va faire la même chose pour une
7:52
promesse qui échoue donc à ce niveau là
7:55
on va créer une autre fonction qu'on va
7:57
appeler wait and fail et elle elle fera
8:00
la même chose sauf qu'au lieu de
8:01
resolveject
8:04
donc si maintenant je reteste ma
8:06
promesse je peux lui dire à ce niveau là
8:08
hop j'ai envie que tu fasses un wait je
8:11
veux attendre pendant deux secondes et
8:13
ensuite je veux que tu fasses un console
8:16
point lock donc on peut directement lui
8:18
passer console point log il sera appelé
8:20
avec les bons paramètres si on regarde
8:22
on va attendre ici 2 secondes et au bout
8:24
de 2 secondes on va bien avoir le 2000
8:26
qui s'affiche
8:27
l'avantage c'est que je peux lui dire en
8:30
fait je vais appeler une fonction comme
8:31
ceci
8:33
hop on va mettre ici j'ai attendu attend
8:35
de seconde
8:37
et après on peut lui retourner une
8:39
nouvelle promesse et on va lui dire
8:41
j'aimerais bien que tu attendes une
8:42
seconde et dans ce cas là le veine que
8:45
l'on met derrière il ne sera appelé
8:47
qu'au bout de une seconde après les deux
8:49
secondes précédentes et là on mettra la
8:52
tente de une seconde ici
8:55
si à ce niveau là on faisait un return
8:56
weight and fail après il faudra le
8:59
capturer et on pourra le capturer grâce
9:01
à un cache et vous pouvez enchaîner les
9:03
choses au fur et à mesure on va
9:05
s'arrêter juste à deux promesses
9:07
consécutives c'est juste pour vous
9:08
expliquer le principe mais vous voyez
9:10
qu'au bout de deux secondes on a le
9:11
attendre de 2 secondes et le attend de
9:13
une seconde qui s'affiche donc cette
9:15
syntaxe là permet de faire quelque chose
9:17
en séquence un peu plus simplement que
9:20
le système de callback l on a qu'un seul
9:23
niveau finalement de call back
9:25
et on voit que lorsqu'on en atteint la
9:27
résolution d'une promesse on peut
9:28
retourner une nouvelle promesse et le
9:30
résultat de tout ça mais ça redonne une
9:32
nouvelle promesse qui attendra la fin de
9:34
cette promesse là et pour être juste sur
9:37
qu'on soit hop tous sur la même longueur
9:40
d'onde si je fais ici un return wait and
9:42
fail vous allez voir que au bout de 2
9:44
secondes on va mettre un attente de 2
9:45
secondes et là on va me dire un coq in
9:48
promis alors ça c'est une erreur qui
9:50
veut dire que on a une promesse qui
9:52
échoue et cette promesse on n'a pas géré
9:54
de catch avec donc c'est exactement ce
9:57
qui se passe ici on a effectivement une
9:59
promesse que l'on attendait même si de
10:01
toute façon je retire ça on aurait la
10:02
même erreur donc quand une promesse
10:04
échoue le navigateur lui va considérer
10:07
que la l'erreur n'a pas été capturée et
10:10
que ce n'est pas une bonne chose c'est
10:11
une erreur qui peut être renvoyée ou non
10:13
suivant les environnements donc la
10:14
typiquement on pourrait faire un catch
10:16
et à l'intérieur on met une fonction qui
10:19
fait rien renverrait nul par exemple
10:21
dans ce cas là notre promesse va bien
10:23
capturer l'erreur et on voit qu'on a
10:25
plus mais ce catch est bien appelé soit
10:28
parce que directement cette promesse
10:31
serait rejetée soit parce que le
10:33
résultat du retour de cette fonction-là
10:35
serait rejeté aussi c'est à dire que si
10:37
ici je fais un white and fail
10:38
directement ce catch va être appelé
10:41
instantanément vu que c'est celle-ci qui
10:43
échoue donc il faut bien comprendre le
10:45
principe du chaînage pour ça que
10:46
j'insiste un petit peu sur ce point là
10:48
parce que c'est un élément assez
10:50
important dans l'utilisation des
10:51
promesses
10:52
alors maintenant on va parler d'un
10:54
élément de syntaxe qui va nous permettre
10:55
avec les promesses de travailler
10:56
beaucoup plus simplement le système de
10:58
veine et de catch et de callback c'est
11:00
pas forcément tout très pratique dans
11:02
certaines situations alors vous pouvez
11:04
déclarer une fonction comme asynchrone
11:06
en utilisant le mot clé usink ensuite
11:08
vous nommez votre fonction de manière
11:11
classique donc nous on va l'appeler main
11:13
comme la fonction principale donc ça
11:15
marche de cette manière là mais ça
11:16
marche aussi si vous créez la fonction
11:18
avec le système de constante vous pouvez
11:21
mettre think et ensuite mettre votre
11:23
fonction fléchées ou mettre votre
11:25
fonction avec le mot clé fonction ça
11:27
marche dans toutes les situations donc
11:29
toutes les fonctions que l'on a vu
11:30
peuvent être rendues à synchrone
11:32
lorsqu'une fonction est déclarée de
11:34
manière assez grande même si elle
11:35
retourne à un résultat directement là on
11:37
est d'accord que ce code techniquement
11:39
il est pas synchrone si j'appelle cette
11:42
fonction là et que je regarde son
11:43
résultat on va voir que ça va me dire
11:45
que c'est
11:46
une promesse
11:48
c'est une promesse qui est remplie vu
11:50
qu'on retourne une valeur et qui renvoie
11:52
4 si à l'intérieur de cette fonction on
11:55
fait un Frau et qu'on envoie une erreur
11:57
mais dans ce cas-là ça renverra une
11:59
promesse qui est rejetée avec l'erreur
12:01
en question donc ça change la manière de
12:04
travailler finalement avec les promesses
12:05
mais ce qui est super intéressant c'est
12:08
qu'on peut utiliser le mot clé ewate
12:09
lorsqu'on utilise une promesse dans une
12:11
fonction asynchrone imaginons j'ai envie
12:13
de faire un petit peu ce que j'avais
12:15
fait tout à l'heure atteindre de seconde
12:17
et afficher une console point lock parce
12:19
que je peux faire c'est utiliser le mot
12:20
clé awate et ensuite il faudra mettre
12:23
une promesse dont on atteint la
12:24
résolution donc nous on va générer cette
12:26
promesse en utilisant notre fonction
12:27
wait
12:29
et après je peux faire un console point
12:31
log et afficher par exemple bonjour
12:35
si j'essaie maintenant d'exécuter cette
12:37
fonction main qu'est-ce qui va se passer
12:39
mais il va attendre les deux secondes
12:42
parce que ça c'est une promesse et ce
12:44
code là ne sera exécuté qu'après
12:46
l'avantage c'est que cette syntaxe
12:47
permet d'être beaucoup plus rapide si je
12:49
veux lui dire ensuite à temps une
12:51
seconde et refait un console point log
12:53
derrière vous voyez c'est beaucoup plus
12:55
facile à écrire et ça se lit de manière
12:57
plus linéaire que le système de callback
12:59
dans ce cas là il va attendre 2 secondes
13:01
afficher bonjour puis une seconde plus
13:03
tard afficher hello si par contre une
13:06
promesse échoue si jamais on fait un
13:08
weight and fail mais il faudra la
13:10
capturer avec la syntaxe strikatch
13:12
habituel donc par exemple ici il faudra
13:14
faire un trail on pourra entourer tout
13:16
notre code ici hop et lui dire bon bah
13:20
il y a quelque chose qui s'est passé de
13:21
manière incorrecte et on peut réagir en
13:23
fonction par exemple ici on pourrait
13:25
faire un console.log
13:27
error
13:28
si je sauvegarde on va voir que dans ce
13:30
cas là la première va échouer et on
13:32
arrive dans ce cas-là donc la syntaxe
13:34
Wade est think permet encore une fois
13:37
d'avoir quelque chose de à plat beaucoup
13:38
plus simple à lire autre petit détail si
13:41
votre promesse renvoie un résultat vous
13:43
pouvez lui utiliser avec le White par
13:45
exemple je peux faire un console point
13:47
log lui dire attends de faire une
13:50
attente de 2 secondes ça on avait vu que
13:52
le weight ça nous renvoyait une promesse
13:55
qui se résolvait avec la valeur de la
13:56
durée ben dans ce cas là dans le console
13:58
point lock je vais avoir la valeur de la
14:00
durée ici 2000 mais je pourrais tout
14:03
aussi bien le sauvegarder dans une
14:04
variable par exemple on va l'appeler du
14:06
reichen voilà
14:08
j'attends la résolution de cette
14:10
promesse pour que cette valeur soit
14:11
définie et après je peux faire une
14:12
console point log et afficher la durée
14:16
donc on mettrait du Raichu
14:25
enfin un dernier petit point c'est que
14:27
si je décide plus tard de faire un
14:28
retard de 5 là il faut bien comprendre
14:30
que cette fonction-là elle renverra une
14:33
promesse donc je pourrais tout à fait
14:34
lui dire ici bon ben lorsque notre
14:36
fonction main a fini de s'exécuter donc
14:39
lorsque on a le 5 qui est renvoyé je
14:42
veux faire quelque chose par exemple
14:44
faire un console.log dans ce cas là il
14:47
attendra que toutes ces promesses soient
14:49
résolues et c'est comme la syntaxe de
14:50
veine que l'on a écrit précédemment mais
14:52
écrit finalement différemment donc le
14:54
Think awate ne va pas apporter de
14:55
nouvelles fonctionnalités il va surtout
14:57
nous permettre de travailler plus
14:59
simplement avec les promesses
15:01
enfin un dernier petit détail sur le
15:03
Think et le weight sur certains
15:06
environnements vous pouvez utiliser ce
15:07
que l'on appelle les tops level wait
15:09
c'est à dire que vous pouvez lui dire
15:11
par exemple là je veux attendre hop de
15:14
seconde et au bout de 2 secondes de
15:16
faire un console point de log de Hello
15:18
donc là sur le navigateur on voit que
15:21
tout de suite ça nous renvoie une erreur
15:22
nous dit non le awake il ne peut être
15:24
utilisé que dans les fonctions think ou
15:28
dans le haut des modules mais ça c'est
15:29
encore pour un autre chapitre mais donc
15:31
là on ne peut pas écrire un awate comme
15:32
ça ça sera réservé dans les fonctions
15:34
asynchrones
15:36
donc voilà pour ce petit détail alors
15:40
maintenant on va parler de la
15:41
possibilité de combiner les promesses
15:42
ensemble et on va revenir sur la
15:44
documentation donc on a déjà parlé du
15:46
cash on a parlé du finalier du veine sur
15:48
le prototype mais on voit qu'on a aussi
15:50
d'autres d'autres choses alors d'abord
15:52
les premiers points résolvent et
15:54
promise.jete c'est très simple ça permet
15:56
de renvoyer directement une promesse qui
15:58
est résolue ça peut servir dans
16:00
certaines situations ou des algorithmes
16:02
attendent une promesse plutôt qu'un
16:04
objet classique donc si je fais ici un
16:07
promise point resolve et que je mets la
16:11
valeur 2 automatiquement ça me donne une
16:13
promesse qui est déjà résolue avec cette
16:15
valeur là si je fais un promise point
16:18
reeject et que je donne la valeur 2 ça
16:21
nous donnera une promesse qui a échoué
16:22
avec la valeur 2 voilà ça peut être
16:25
utile mais concrètement ça correspondra
16:27
à des situations assez spécifiques
16:29
ensuite toutes les autres méthodes ont
16:31
entrées justement à la combinaison des
16:33
promesses alors on va commencer par le
16:34
premier point hall c'est à mon sens
16:36
peut-être le plus simple le premier
16:38
point hall on va lui passer un premier
16:40
paramètre unitérable donc considérez ça
16:42
comme un tableau où on va lui donner
16:43
différentes promesses et ensuite ce que
16:46
ça va faire c'est que ça va nous
16:47
renvoyer une nouvelle promesse qui aura
16:49
comme résultat la résolution de toutes
16:51
les promesses si une des promesses dans
16:53
la liste échoue dans ce cas-là ça nous
16:55
renverra le l'erreur de la promesse en
16:57
question alors prenons un exemple
16:59
concret ça nous parlera un petit peu
17:01
plus on va faire un promise
17:03
et on va lui passer de promesses une
17:06
promesse qui va durer une seconde et une
17:09
seconde promesse qui va durer deux
17:11
secondes voilà et cette promesse on va
17:14
regarder quand est-ce qu'elle est
17:15
résolue et on va faire un console point
17:16
log pour voir le résultat si je
17:19
sauvegarde on voit que au niveau de ma
17:21
console je n'ai rien et au bout de 2
17:23
secondes parce qu'il faut que les deux
17:24
soient résolus dans ce cas là il va
17:26
m'afficher un tableau alors on va
17:28
essayer aussi de faire un catch et on va
17:30
faire un console point log dans le cadre
17:32
d'une erreur aussi si une de mes
17:34
promesses échoue par exemple en imagine
17:36
que la première échoue au bout de une
17:39
seconde dans ce cas là la promesse va
17:41
échouer directement et c'est ce catch
17:43
qui va être appelé avec le résultat de
17:45
la première promesse qui a échoué si
17:47
c'était la seconde qui échoue et la
17:49
première qui réussit ça ferait la même
17:51
chose dans nos consoles ici on ne
17:54
rentrerait dans le catch et j'aurai 2000
17:56
alors ensuite on a la méthode all
17:58
settled donc c'est un petit peu le même
18:00
principe que le hall sauf que ça ignore
18:03
en fait les promesses qui vont échouer
18:04
donc on va faire un hall settle voilà on
18:08
va lui passer toujours de promesses qui
18:09
réussissent et ici je regarde le retour
18:12
je vais bien avoir mon tableau de taille
18:14
2 sauf que à l'intérieur je n'ai pas les
18:16
valeurs mais j'ai des objets j'ai un
18:18
objet qui contient le statut de la
18:20
promesse fullfield ça veut dire que la
18:22
promesse a bien réussi et la valeur si
18:24
une de mes promesses venait à échouer
18:26
donc on ferait un wait and fail ça
18:28
serait toujours ce console point log qui
18:30
serait appelé sauf que on aurait un
18:32
objet avec une seconde promesse qui sera
18:34
en mode rejective donc ça c'est
18:36
intéressant si vous voulez lancer
18:37
plusieurs opérations en même temps sans
18:39
que une opération Vienne annuler le
18:41
reste contrairement au hall où vous
18:43
considérez que si une échoue votre votre
18:45
système a échoué
18:47
après on a aussi la méthode ENI donc la
18:51
méthode ENI elle prend un paramètre
18:52
encore une fois plusieurs promesses donc
18:54
on va faire ici encore une fois uni on
18:56
va lui donner deux promesses qui va bien
18:59
fonctionner et pour différencier nos
19:01
consoles on va mettre une console point
19:03
error s'affiche les choses en rouge en
19:04
console plutôt que le console point lock
19:06
si je regarde dans ma console ça me
19:09
donne 1000 donc ni nous nous donne le
19:11
résultat de la première promesse qui est
19:12
résolue si cette promesse venait à
19:14
échouer par exemple on fait un wait and
19:16
fail dans ce cas là ça va nous donner
19:18
2000 c'est à dire que ça nous donne le
19:20
résultat de la première promesse qui
19:22
n'est pas rejetée dans ce tableau là si
19:25
les deux promesses venaient à échouer
19:26
dans ce cas là toutes les promesses
19:28
échouent et ils nous renverrai ici une
19:30
erreur en nous donnant une agrégate
19:32
erreur que l'on pourrait capturer grâce
19:34
au catch enfin la dernière chose c'est
19:37
le promise point rece c'est un petit peu
19:39
comme le premier x point ENI si ce n'est
19:42
que si la première promesse échoue il va
19:44
considérer que c'est un échec donc il va
19:46
regarder la première promesse qui arrive
19:48
à terme que ce soit un échec ou une
19:50
réussite et si c'est une réussite dans
19:52
ce cas là il renverra une nouvelle
19:53
promesse qui sera complétée dans le cas
19:57
contraire il renverra une promesse qui
19:58
est en échec si je fais ici un wait
20:02
on obtient le même résultat que le ni
20:04
c'est bien cette promesse là qui va être
20:05
résolue en premier et si je fais un wait
20:07
and fail là où le ENI attendait 2
20:10
secondes pour la résolution de celle-ci
20:11
le Race va dire ah mais c'est celle-ci
20:14
qui a été la plus rapide elle a été
20:15
rejetée donc je rejette et c'est le
20:17
catch donc voilà les différentes
20:19
manières que l'on a de combiner les
20:21
promesses je vous avouerai dans la vie
20:23
de tous les jours c'est quand même des
20:24
choses que vous avez besoin de faire
20:25
assez rarement mais c'est le jour où
20:27
vous avez besoin de le faire que c'est
20:29
important donc c'est pour ça que c'est
20:30
important de comprendre les différences
20:32
entre ces différentes méthodes mais
20:33
sachez qu'au jour le jour vous n'aurez
20:35
pas forcément besoin de les utiliser
20:36
toutes les deux secondes et vu que ces
20:37
différentes méthodes renvoient une
20:39
promesse si vous êtes dans un dans une
20:40
fonction asynchrone mais vous pouvez lui
20:42
dire au fait j'aimerais bien récupérer
20:44
par exemple le résultat de la première
20:47
promesse et faire un wait devant pour
20:49
attendre la résolution ça permet aussi
20:51
d'avoir une attaque qui est un peu plus
20:52
simple plutôt que de combiner les veines
20:54
mais ça il faut être dans une fonction
20:56
asynchrone
20:58
alors enfin un dernier petit point parce
20:59
que je sais que certaines personnes ont
21:01
eu des problèmes avec ça il faut bien
21:03
comprendre que lorsque vous créez une
21:04
promesse le code à l'intérieur de la
21:06
promesse est tout de suite exécuté ce
21:07
n'est pas lorsque vous faites un que il
21:09
est exécuté si je recrée ma fonction qui
21:12
permet d'atteindre de manière synchrone
21:13
on va l'appeler waiting on lui passe la
21:16
durée on crée une variable T qui est
21:19
égale à la date du jour en milliseconde
21:21
et en lui disant que la date du jour
21:23
moins ST est inférieur à la durée que
21:26
j'ai spécifié dans ce cas là je bloque
21:28
mon script voilà donc imaginons que
21:31
maintenant je me crée une promesse
21:36
et cette promesse on va lui passer juste
21:38
le resolve et on fera un console point
21:41
log et l'eau
21:43
et ensuite on lui dit de resolve avec la
21:46
valeur 2
21:48
cette promesse on va le sauvegarder dans
21:49
une variable on va faire constipé et
21:52
ensuite on va lui dire attends de
21:54
manière synchrone
21:56
et attends 2 secondes alors là qu'est-ce
21:59
qu'il me dit il me dit que P déjà
22:01
utilisé ouais hop on avait utilisé en
22:03
haut
22:04
et ensuite je lui demande de faire un
22:06
console.log les gens
22:09
on pourrait se dire ben en fait la
22:11
promesse là ce code là il va être
22:13
exécuté de manière assez chronique mais
22:14
pas du tout ce code que l'on a à
22:16
l'intérieur va être exécuté tout de
22:17
suite et si j'essaie de réactualiser ma
22:20
page on voit bien qu'on a le hello qui
22:22
s'affiche au tout de suite et les gens
22:23
qui s'affichent tout de suite parce que
22:24
j'ai oublié d'appeler la fonction date
22:26
donc là on voit bien que ça tente 2
22:28
secondes avant d'afficher les gens cette
22:30
fonction-là est directement appelée ce
22:33
qui est asynchrone et ce qui va être
22:34
appelé dans un second temps c'est ce que
22:36
vous mettez dans le veine ce n'est pas
22:38
ce que vous mettez dans cette fonction
22:39
là donc ça c'est très important de bien
22:42
comprendre ça si jamais vous avez du
22:44
code bloquant à ce niveau là ce code
22:46
bloquant va être tout de suite exécuté
22:47
c'est un petit détail mais c'est
22:49
important si ici je le dis p.ven et on
22:52
va mettre
22:53
à l'intérieur une fonction qui fera
22:56
console point log et on mettra veine
22:59
lorsque je sauvegarde on a hello ensuite
23:02
on a les gens et ensuite seulement on a
23:04
le veine parce que il exécute le fil
23:07
principal c'est à dire qu'il exécute
23:08
cette fonction là tout de suite qui fait
23:10
le hello ensuite là il voit que c'est du
23:13
code asynchrone donc le VN il se le met
23:15
en attente lorsque la promesse sera
23:16
résolue même si la promesse est résolue
23:18
tout de suite ensuite il arrive au
23:19
waiting il attend pendant deux secondes
23:22
en bloquant totalement le script rien ne
23:24
peut être fait il arrive aux
23:25
consoles.log les gens et il l'affiche
23:27
maintenant le fil principal est libéré
23:29
et il peut attaquer le code asynchrones
23:31
et du coup il se dit ah bah ce code là
23:33
vu que la promesse est résolue je peux
23:35
l'exécuter et du coup il affiche le
23:37
console point longue de 20 donc même si
23:39
ça paraît pas forcément super naturel au
23:41
premier abord il faut bien comprendre
23:42
comment fonctionne le système de fil
23:44
principale et fil secondaire le
23:46
Javascript va toujours exécuter en
23:48
premier le fil principal et ensuite il
23:51
va mettre en file d'attente les
23:52
différentes les différents callbacks qui
23:54
doivent être appelés et il les appelle
23:56
dès que il a un petit moment de libre
23:59
et c'est pour ça que ce vn là n'est pas
24:01
exécuté tout de suite enfin dernier
24:03
petit détail sur le Think n'utilisez le
24:06
sint que si vous avez un away à
24:08
l'intérieur ce n'est pas nécessaire
24:10
d'utiliser un think si jamais vous
24:12
renvoyez directement une promesse comme
24:14
par exemple on a pu le faire pour Wade
24:16
ou autre de la même manière si vous
24:19
voulez renvoyer une promesse que vous
24:20
transformez vous n'êtes pas obligé
24:22
d'utiliser une fonction à synchrone
24:24
typiquement
24:26
imagine non on veut faire une fonction
24:29
qui s'appelle wait andlock l'idée ça
24:32
serait de lui passer une durée et un
24:34
message à logué donc par défaut on
24:37
aurait peut-être l'idée de se dire mais
24:38
on va faire une fonction asynchrone
24:42
et ensuite on va faire un weight on va
24:44
attendre la durée qui a été indiquée et
24:47
ensuite faire une console point loc de
24:49
message donc ça c'est parfaitement
24:50
valide mais ce que l'on peut aussi faire
24:52
c'est ne pas du tout faire une fonction
24:54
à synchrone et lui dire je veux faire un
24:56
return de wait et lorsque ce cette
25:00
promesse est résolue faire un vein et
25:02
faire un console point log de mon
25:04
message ça ça va avoir le même effet que
25:08
ce que l'on a écrit avec le Think mais
25:09
tant qu'une fonction renvoie une
25:11
promesse elle pourra être utilisée après
25:12
dans les aways et la synchrone voilà en
25:15
fait ce qu'il faut vraiment éviter c'est
25:16
les fonctions de cette manière là c'est
25:18
écrire des a think en écrivant ensuite
25:21
un return wait de ça ça n'a pas de pas
25:25
d'intérêt là vous créez en fait un autre
25:27
niveau de promesse pour rien et c'est de
25:29
la perte de performance pour absolument
25:31
aucun intérêt donc de temps en temps ça
25:34
peut être plus pratique d'utiliser le
25:35
point veine plutôt que de déclarer une
25:37
fonction asynchrone pour rien parce que
25:39
lorsque vous créez une fonction
25:39
synchrone ça crée une nouvelle promesse
25:41
qui est entoure votre mais pour
25:43
l'instant ne vous prenez pas trop la
25:44
tête sur ça au pire quand vous montrerez
25:46
votre code à votre personne elle vous
25:49
diront si peut-être vous avez utilisé un
25:50
insigne pour rien voilà mais c'est pour
25:52
vous montrer au cas où vous tombiez sur
25:53
le sur l'exemple donc avec ce petit
25:56
détail là on vient de terminer ce
25:58
chapitre là donc vous le voyez les
26:00
promesses vont nous permettre de
26:01
représenter n'importe quel code qui peut
26:04
fonctionner de manière à synchrone
26:05
finalement on fait un new promise on
26:07
passe ensuite une fonction dans cette
26:09
fonction on fait ce que l'on veut donc
26:11
on peut exécuter du code qui est assez
26:13
synchrone comme le 7 times et lorsque
26:15
notre promesse est résolue on peut
26:17
utiliser resolve si notre promesse est
26:19
en échec on ne sera rejette une fois que
26:21
l'on a une promesse dans du code
26:23
asynchrone on peut attendre la
26:24
résolution de cette promesse beaucoup
26:26
plus simplement et ça permet de créer un
26:28
code qui est plus séquentiel et plus
26:29
facile à lire là où avec syntaxe cette
26:32
timante classique par exemple on avait
26:34
ce système de callback l qui rendait le
26:36
code difficile à lire là on le voit et
26:38
quand on fait ce genre de code c'est
26:40
beaucoup plus facile à comprendre parce
26:41
que on est plus habitué à lire les
26:43
choses de haut en bas plus que des
26:45
parenthèses imbriquées et enfin on
26:47
gardera dans un coin de notre tête les
26:49
différentes méthodes qui permettent de
26:50
combiner les promesses en fonction des
26:52
situations donc suivant ce que l'on vous
26:53
voudrez faire vous allez utiliser plutôt
26:55
l'une ou l'autre de ces éléments là
26:58
j'espère que j'ai été assez clair sur ce
27:00
chapitre là et je vous donne rendez-vous
27:02
dans un prochain chapitre ou justement
27:04
on va avoir une fonction qui utilise les
27:05
promesses c'est un des problèmes
27:07
effectivement dans le langage mis à part
27:09
une fonction la plupart des fonctions
27:11
qui existent actuellement en Javascript
27:13
vu qu'elles ont été créées avant
27:15
l'apparition des promesses utilise ce
27:16
système de Call pack comme par exemple
27:18
cette taille menthe ce que vous pouvez
27:20
faire et je vous inviterai de toute
27:22
façon à le faire dans vos scripts c'est
27:23
de transformer ces fonctions là avec des
27:25
versions avec promesses typiquement
27:27
cette fonction wait elle peut être très
27:29
utile et du coup on se voit dans le
27:31
prochain chapitre