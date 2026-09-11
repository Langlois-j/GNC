# Apprendre le JavaScript : Le sucre syntaxique

Video : https://www.youtube.com/watch?v=kwcFfskBaag

## Transcription

ah bienvenue dans ce nouveau chapitre je
0:01
vous propose de parler des timer et
0:03
notre objectif ici c'est de faire en
0:04
sorte d'afficher quelque chose
0:05
d'attendre une seconde et d'afficher
0:07
autre chose et on va voir qu'il y a
0:09
plusieurs manières de faire les choses
0:10
et ça va nous permettre de mettre un
0:12
petit peu les pieds dans le côté
0:13
asynchrone du JavaScript
0:15
donc notre idée c'est de nous créer une
0:17
fonction que l'on va appeler wait on lui
0:19
passera en paramètre une durée et
0:21
ensuite cette fonction va permettre
0:24
d'attendre l'idée c'est qu'ensuite je
0:26
puisse faire console point log bonjour
0:28
lui dire j'aimerais bien que tu attendes
0:31
alors on va parler un millisecond dans
0:33
JavaScript donc on va lui dire une
0:34
seconde et que tu affiches les gens
0:36
voilà donc si j'ai exécute ce code tout
0:39
de suite passer ma fiche bonjour les
0:40
gens direct donc pour lui demander de
0:43
s'arrêter la seule manière que l'on a vu
0:45
jusqu'à maintenant c'est les boucles on
0:46
a vu que si on faisait une boucle
0:47
infinie ça s'est arrêté de manière
0:49
indéfinie c'est à dire que le script ne
0:51
se lançait jamais on peut utiliser cette
0:52
cette problématique là à notre avantage
0:55
pour cela on va utiliser une variable
0:57
spéciale en utilisant la méthode no sur
1:00
les dates je vous en ai jamais parlé
1:02
mais cette fonction-là permet d'obtenir
1:04
le nombre de millisecondes écoulés
1:06
depuis le 1er janvier 1970 c'est ce que
1:09
l'on appelle un timestamp donc souvent
1:11
quand on représente les temps en genre
1:13
en Javascript mais aussi dans d'autres
1:14
langages de programmation on utilise
1:16
cette donnée là le nombre de secondes ou
1:18
de mini secondes et couler depuis le 1er
1:20
janvier 1970 a aujourd'hui
1:23
donc ensuite on peut lui dire tant que
1:25
date point nos donc recalcule la date
1:28
moins ST est inférieur à la durée je ne
1:32
fais rien concrètement ça veut dire que
1:34
si j'exécute ce code je vais être bloqué
1:36
dans cette boucle jusqu'à qu'une
1:38
certaine durée se soit exécutée si je
1:41
sauvegarde maintenant on voit qu'il
1:42
affiche bonjour ça met un petit temps à
1:44
charger et ensuite il met les gens donc
1:47
ça c'est une manière d'attendre qui est
1:49
une manière synchrone mais on va avoir
1:51
la possibilité avec le JavaScript de
1:53
faire les choses de manière asynchrone
1:55
ce qui permettra d'avoir un code
1:56
beaucoup plus efficace alors histoire de
1:58
vous illustrer la différence entre
1:59
langage asynchrone et un langage
2:01
synchrone je vous propose un petit
2:02
exemple vous êtes un restaurateur et
2:04
vous tenez un petit restaurant de
2:06
poisson on imagine que chaque opération
2:07
que l'on fait dans ce restaurant et une
2:09
fonction mange JavaScript donc d'abord
2:12
on prend la commande des gens donc ça
2:14
serait une fonction prendre commande
2:15
donc là il nous demande de faire un
2:17
poisson donc je vais avoir une fonction
2:19
prendre poisson puis une fonction cuire
2:21
le poisson le problème c'est que pendant
2:23
la cuisson je suis obligé d'attendre la
2:25
fin de l'exécution de cette fonction une
2:27
fois qu'elle a fini de s'exécuter je
2:28
vais pouvoir prendre le poisson le
2:30
mettre dans une assiette et peut-être le
2:32
mettre de côté j'ai besoin de cuisiner
2:34
un autre poisson donc je fais la même
2:36
chose je prends le poisson je les dépose
2:38
et j'attends devant le feu qu'il se
2:41
fasse et une fois qu'il est fait je peux
2:43
le mettre dans l'assiette et servir mes
2:44
différents clients donc on le voit le
2:46
problème de cette manière de travailler
2:48
c'est que finalement on a beaucoup
2:50
d'opérations qui mettent du temps à se
2:52
faire et pendant que on attend on ne
2:54
fait rien un langage asynchrone va être
2:56
beaucoup plus efficace parce qu'on va
2:57
pouvoir faire plusieurs opérations en
2:59
même temps donc on va commencer par la
3:01
même chose on va prendre la commande des
3:03
personnes on va prendre le poisson et on
3:06
va le faire cuire mais pendant qu'il est
3:07
en train de cuire plutôt que d'attendre
3:09
devant le feu mais on va pouvoir faire
3:11
d'autres choses donc on va pouvoir
3:12
prendre notre poisson et le faire cuire
3:14
aussi ensuite une fois que le premier
3:16
poisson a fini de se cuire mais je peux
3:18
revenir dessus et continuer les
3:19
opérations
3:20
et une fois que le second a fini je le
3:23
reprends et on voit que c'est beaucoup
3:25
plus efficace parce que plutôt que de
3:26
passer du temps à ne rien faire et à
3:29
rester devant le feu pendant que les
3:30
choses se font on peut attaquer d'autres
3:32
choses donc le Javascript va avoir cette
3:34
capacité de pouvoir passer d'un fil à un
3:38
autre et de pouvoir effectuer avec un
3:40
seul processus plusieurs opérations en
3:42
même temps alors nous évidemment ici on
3:44
ne va pas cuisiner mais on veut attendre
3:46
un petit moment donc on a vu cette
3:48
fonction là mais on a des fonctions
3:49
internes au JavaScript qui nous
3:51
permettent de faire les choses de
3:52
manière beaucoup plus efficace on a une
3:54
méthode qui s'appelle cette taille
3:56
menthe si vous cherchez sur MDN hop
3:59
cette timante elle prendra en général
4:01
deux paramètres le premier ça sera une
4:04
fonction qui sera exécutée lorsque le
4:05
délai sera il est coulé et le second
4:08
paramètre c'est le délai attention ce
4:10
délai est un milliseconde
4:12
donc dans notre cas plutôt que des
4:14
utiliser notre fonction wait on va la
4:15
commenter on va pouvoir utiliser cette
4:18
taille menthe en lui passera en premier
4:20
paramètre une fonction qui fera du coup
4:22
notre console point log les gens
4:25
et ensuite on va mettre une virgule et
4:28
mettre une seconde
4:31
si j'exécute ce code-là on voit que ça
4:34
m'affiche bonjour les gens la
4:36
particularité c'est que si j'avais ici
4:38
le reste de mon code et que je faisais
4:40
un au revoir
4:42
qu'est-ce qui se passerait avec cette
4:44
fonction à synchrone on voit qu'il fait
4:46
bonjour au revoir et ensuite seulement
4:48
il affiche les gens donc c'est ce que je
4:50
vous disais avec l'exemple du cuistot le
4:52
Javascript ne va pas rester bloqué
4:54
devant le feu c'est à dire que lorsqu'on
4:55
va lui dire attend une seconde ça va
4:58
être mémorisé par le moteur en interne
5:00
mais votre JavaScript va continuer à
5:02
exécuter le reste des lignes au bout
5:04
d'une seconde le délai est écoulé et du
5:07
coup bah si j'ai du temps de libre je
5:08
vais exécuter cette ligne là et
5:10
s'affichera les gens donc l'avantage de
5:12
la synchrone c'est que ce n'est pas
5:14
bloquant si on reprend l'exemple avec le
5:17
weight juste pour vous le remontrer on
5:19
aurait affiche ici le console.log les
5:22
gens on va commenter notre sept timante
5:24
le comportement est complètement
5:25
différent là on est bloqué c'est comme
5:28
tout à l'heure on est bloqué devant le
5:30
feu c'est exactement ce qui se passe ici
5:31
on est obligé d'atteindre une seconde
5:33
avant de pouvoir exécuter les lits donc
5:35
ce set tiement va nous permettre de
5:38
faire d'autres choses pendant la phase
5:39
où on est en train d'attendre une
5:41
seconde et ça c'est super intéressant
5:42
pour pouvoir faire plus de choses avec
5:44
autant de ressources donc on a cette
5:47
fonction cette taille mouth mais on a
5:48
aussi une autre fonction qui s'appelle
5:50
cette intervalle qui va permettre de
5:52
faire une opération à un intervalle de
5:55
temps régulier donc dans mon cas ici ça
5:57
affichera en bout d'une seconde les gens
5:59
et ça continuera à le faire toutes les
6:01
secondes
6:02
cette fonction cette intervalle et la
6:05
fonction cette taille m'a aussi elle
6:07
retourne quelque chose si je regarde un
6:09
petit peu à quoi ressemble la valeur de
6:11
retour ça va me donner un entier cet
6:14
entier est un identifiant permettant de
6:16
retrouver ce timer alors pourquoi on
6:18
aurait besoin de nous retrouver pour par
6:19
exemple le stopper on a des méthodes qui
6:22
sont associées on a clear intervalle
6:24
pour les intervalles et claire timorde
6:26
pour les times on fait cuire intervalle
6:29
on met entre parenthèses l'idée de
6:31
l'intervalle que l'on souhaite nettoyer
6:32
et automatiquement lorsqu'on l'exécute
6:34
l'intervalle est supprimé et du coup on
6:37
voit que cette boucle là s'est arrêtée
6:39
on peut faire la même chose avec le 7
6:41
times
6:43
autre petit détail vous n'avez pas de
6:45
garantie sur l'affichage ici imaginons
6:48
que vous écrivez ce code là on revient
6:50
sur le sept timelante on se dit bon ben
6:53
au bout d'une seconde il va afficher les
6:54
gens le problème c'est que si vous êtes
6:57
bloqué sur autre chose par exemple on
6:58
peut s'imaginer que après on demande à
7:01
l'utilisateur quelque chose on lui
7:02
demande de rentrer un nom
7:04
si on fait ça et quand actualise la page
7:06
on voit que dans la console il n'affiche
7:08
pas les gens parce que notre code est
7:10
actuellement bloqué comment il était
7:13
bloqué finalement quand on fait le wait
7:14
dans cette partie prompte donc tant que
7:17
le Javascript n'a pas repris la main il
7:19
n'est pas capable d'exécuter ce que l'on
7:20
a dans les 7 times donc effectivement
7:22
ici on a dit il faudrait que tu
7:23
l'affiche au bout d'une seconde mais
7:25
dans la réalité ça va être affiché
7:26
beaucoup plus tard vu que en état obligé
7:29
d'atteindre la fin du prompt par contre
7:31
cette exécuté directement dès que j'ai
7:32
tapé le prompte parce que c'était un fil
7:34
d'attente donc ça c'est aussi quelque
7:36
chose à prendre en compte si vous avez
7:38
des opérations lourdes vous n'avez pas
7:39
forcément une garantie absolue que ça ça
7:42
va être exécuté au bout d'une seconde
7:43
exactement voilà c'est un petit détail
7:45
si vous utilisez ces données là il faut
7:47
faire attention à ça le principal
7:49
problème que l'on va rencontrer avec
7:50
cette notion d'un synchrone c'est vrai
7:52
pour cette fonction de timer mais ça va
7:54
être vrai pour beaucoup de fonctions
7:55
javascript c'est que ça nous oblige à
7:57
imbriquer les callback en effet si on se
8:00
dit que on a notre bonjour on fait notre
8:02
sept timante et la suite de notre script
8:04
elle dans le Times donc on écrirait du
8:06
code ici avec plein plein de lignes le
8:09
problème c'est que plus tard on se dit à
8:10
l'intérieur j'ai envie d'attendre par
8:13
exemple deux secondes je suis obligé de
8:15
refaire ça et de mettre la suite de mon
8:17
script ici et si je continue plus tard
8:21
peut-être j'ai envie de attendre mais
8:23
j'écrirai quelque chose comme ça
8:26
ça c'est ce que l'on appelle le callback
8:28
l en anglais c'est l'enfer des callbacks
8:31
c'est le fait que vu que à chaque fois
8:33
qu'on a quelque chose à synchrone on
8:35
était obligé d'avoir une fonction à
8:36
laquelle on passe un callback on se
8:38
retrouve à avoir des callbacks dans des
8:39
call back dans des call back et ça va
8:41
nous amener au chapitre suivant il y a
8:43
justement une manière un petit peu plus
8:44
simple aujourd'hui d'écrire ça en
8:47
utilisant le système de promesse c'est
8:49
quelque chose d'un petit peu plus
8:49
compliqué donc j'ai décidé de consacrer
8:51
un chapitre entier à la notion de
8:53
promesse et je voulais pas vous le
8:54
mélanger avec ça ce que vous devez
8:56
retenir c'est que si jamais vous devez
8:58
attendre un certain une certaine durée
9:00
ne faites jamais ça ça c'est bloquant
9:03
c'est synchrones et ça ne correspond pas
9:05
à la manière de travailler du Javascript
9:07
si vous avez besoin d'atteindre une
9:08
durée déterminée vous allez utiliser
9:10
cette taille menthe et cette intervalle
9:13
si vous voulez faire quelque chose avec
9:14
un intervalle de temps régulier et vous
9:16
pouvez utiliser clear intervalle pour
9:17
nettoyer les choses
9:19
peut-être un petit détail je vais vous
9:21
donner un mini TP pour voir si vous avez
9:22
compris cette notion de timer je vous
9:24
demande de faire quelque chose qui
9:25
s'affiche 5 fois et une fois que vous
9:28
avez fait ça je vais vous demander de
9:29
créer une fonction qui s'appelle
9:30
décompte et l'objectif de cette fonction
9:33
c'est qu'ensuite on puisse lui dire
9:34
j'aimerais bien faire un décompte et
9:37
dans ce cas-là ça affiche 3 ça attend
9:39
une seconde s'affiche 2 ça tend une
9:40
seconde s'affiche 1 et ensuite s'affiche
9:42
0 et ça s'arrête à zéro voilà donc
9:45
essayez de faire ça d'abord essayez
9:47
d'afficher un message un certain nombre
9:49
de fois
9:52
alors pour cette fonction il nous faut
9:54
savoir le nombre de fois qu'on a fait un
9:55
affichage donc on va créer une variable
9:57
i qui aura la valeur 0 ensuite on fait
10:00
notre intervalle avec un set intervalle
10:03
vu qu'on veut faire quelque chose
10:03
plusieurs fois
10:05
je vais lui dire que l'intervalle c'est
10:07
une seconde et ensuite à l'intérieur de
10:09
ma fonction je vais lui dire de faire un
10:11
console point log bonjour
10:14
et à chaque fois que j'appelle bonjour
10:16
j'incrémente i ce qui fait que à
10:19
l'intérieur de cette fonction-là il va
10:21
valoir 0 puis 1 puis 2 puis 3 et ainsi
10:24
de suite ainsi de suite si je veux
10:26
l'arrêter il va me falloir sauvegarder
10:28
l'intervalle dans une variable
10:32
et ensuite lorsque i par exemple est
10:35
égal à 5 ou supérieur ou égal à 5 à sa
10:39
peu d'importance je peux lui dire
10:40
nettoie l'intervalle c'est-à-dire arrête
10:43
de continuer l'exécution de cette boucle
10:46
là si on regarde ça on va voir que ça va
10:49
nous afficher bonjour 5 fois et ça va
10:51
s'arrêter donc voilà comment vous
10:53
pourriez utiliser le système
10:54
d'intervalle avec une limitation au
10:56
niveau du nombre d'exécution maintenant
10:57
on va passer au deuxième exercice le la
11:00
fonction décompte donc des comptes en
11:02
lui passant paramètre un nombre et
11:04
ensuite on appelle avec un décompte de 3
11:07
par exemple
11:08
alors il y a ce niveau là je vais encore
11:11
avoir besoin du timer donc là on va
11:13
faire un set intervalle c'est un
11:16
intervalle qui va durer
11:18
une seconde et on va lui dire de faire
11:21
une console point log de N mais on a
11:25
besoin de savoir quand est-ce que N a
11:26
atteint 0 donc au fur et à mesure je
11:28
vais faire n - Pour décrémenter N et je
11:32
vais dire si n est égal à 0 dans ce
11:35
cas-là c'est que je suis arrivé au bout
11:36
et il faut que je nettoie cette
11:37
intervalle là donc je peux créer une
11:40
variable qui contiendra l'identifiant et
11:42
je fais un Clear intervalle et je lui
11:45
dis de supprimer t si j'essaie de faire
11:47
le décompte de 3 on voit que ça fait 2 1
11:49
0 le petit inconvénient c'est que ça
11:52
n'affiche pas le 3 donc on va lui dire
11:54
dès le début j'aimerais bien que tu
11:55
fasses un console point log de N comme
11:58
ça maintenant ça fait 3 2 1 0 petit
12:02
détail vu que c'est asynchrones on peut
12:04
demander de faire deux décomptes à la
12:05
fois dans ce cas là il va décompter 3 et
12:08
5 en même temps ça fait trois deviens 2
12:10
et 5 de 24 et ainsi de suite ainsi de
12:12
suite donc c'est l'avantage aussi de la
12:14
synchrone vous pouvez avoir plein de
12:16
choses qui se font en même temps donc on
12:17
va revenir juste sur un seul décompte
12:19
sinon ça va être un peu compliqué à
12:20
suivre donc ça c'est une manière
12:22
d'écrire les choses mais il y a aussi
12:23
une autre manière plutôt que de faire un
12:25
intervalle qui se client après le risque
12:27
c'est que parfois on oublie de faire
12:29
l'écrire intervalles et on a des trucs
12:30
qui tournent en tâche de fond on peut
12:32
remplacer ici par un 7e
12:36
si je fais ça
12:38
mais qu'est-ce qui va se passer il va se
12:40
passer que je vais exécuter notre
12:42
compteur qu'une fois ce que je peux
12:44
faire c'est lui dire en fait lorsqu'on
12:46
arrive au bout de la de la durée
12:48
déterminée j'aimerais bien que tu
12:50
réappelles cette fonction là donc en lui
12:52
disant ré appelle des comptes mais tu
12:55
vas l'appeler en lui passant une valeur
12:57
de n qui est décrémentée de 1
13:00
donc si j'appelle des comptes avec 4 par
13:02
exemple il va faire un console point
13:04
lock de 4 il va attendre une seconde et
13:07
appeler la fonction des comptes avec 3
13:09
décompte avec 3 va afficher 3 puis
13:11
appeler des comptes avec deux et ainsi
13:13
de suite ainsi de suite la fonction va
13:14
finalement s'auto appeler l'avantage
13:17
c'est qu'on peut utiliser ici une petite
13:19
condition en lui disant
13:20
if n est égal à 0 je veux que tu
13:23
returnes comme ça tu t'arrêtes tu
13:25
n'aurais exécutes rien je n'ai du coup
13:27
pas ici besoin d'utiliser des clients
13:29
intervalles ça se fait un petit peu de
13:31
manière automatique moi personnellement
13:33
je trouve ce code un petit peu plus
13:35
clair mais après ça peut dépendre de des
13:37
personnes si j'exécute ça ça va afficher
13:39
3 2 1 0 et ça s'arrête à zéro donc on a
13:44
deux manières de faire ça c'est pour ça
13:46
que je voulais vous montrer ce petit
13:47
exemple là
13:49
donc voilà pour la notion de timer et le
13:51
côté asynchrone du javascript j'espère
13:53
que tout a été clair et je vous donne
13:55
rendez-vous dans le prochain chapitre où
13:57
on va parler des promesses et c'est un
13:58
petit morceau