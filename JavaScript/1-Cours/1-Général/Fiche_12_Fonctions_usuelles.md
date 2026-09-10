# Apprendre le JavaScript : Les fonctions usuelles

Video : https://www.youtube.com/watch?v=Qvr6Nh7rtAI

## Transcription

alors bienvenue dans ce nouveau chapitre
0:01
ou ce que je propose c'est de faire un
0:02
petit tour d'horizon des différentes
0:03
méthodes qu'il existe sur les tableaux
0:05
les objets et les fonctions et je vais
0:07
vous en parler vous montrer lesquels
0:08
sont les plus utiles à mon sens et
0:10
celles dont vous aurez besoin même si
0:11
vous ne les retenez pas toutes ce sont
0:13
c'est impossible de toutes les retenir
0:14
l'importance c'est de savoir quelles
0:16
existent pour si jamais vous tombez sur
0:18
une problématique particulière savons
0:20
les retrouver donc on va commencer par
0:21
les tableaux donc je vais taper EUR et à
0:24
ce niveau là et on va regarder les
0:25
différentes méthodes donc la première
0:26
méthode qui est intéressante c'est la
0:28
méthode at donc elle permet de récupérer
0:30
un élément un index particulier la
0:32
particularité qu'elle a c'est qu'elle
0:33
accepte des index négatifs par exemple
0:36
si je vais dans ma console ici et que je
0:38
crée une constante note et que je lui
0:41
dis j'aimerais bien avoir 12 17 et 18 on
0:44
a vu qu'on a déjà la possibilité
0:45
d'accéder à une note en faisant une
0:48
console point log note et un allant à
0:51
l'index 0 1 2 ou 3
0:52
l'intérêt de la méthode Ath c'est qu'on
0:55
peut lui dire d'aller dans le sens
0:57
inverse par exemple je peux lui dire de
0:58
faire un at- et dans ce cas là ça va
1:01
directement me donner la dernière valeur
1:02
ce qui est un petit peu plus simple que
1:04
de devoir faire un crochet de lui dire
1:07
en fait il faut que tu comptes le nombre
1:08
de notes donc ça serait une note point
1:10
donc at peut être intéressant parce que
1:13
il accepte des valeurs négatives
1:16
ensuite on a concaton permet de tout
1:19
simplement concaténer des tableaux
1:20
ensemble pour pouvoir les fusionner donc
1:23
on le voit ici il en ils ont ABC et ça
1:26
devient un seul tableau avec les
1:27
différentes valeurs on le verra dans la
1:29
partie sucre syntaxique on a une manière
1:31
un petit peu plus simple d'écrire ça
1:33
mais cette fonction c'est intéressant de
1:35
savoir qu'elle existe copie wivin je
1:37
l'ai jamais utilisé un trise aussi c'est
1:39
très spécifique every c'est aussi très
1:42
spécifique ça permet de remplir un
1:44
tableau avec des valeurs précises donc
1:47
si vous mettez une seule valeur ça va
1:49
remplir le tableau de cette valeur là et
1:51
vous pouvez lui dire en fait je veux
1:52
remplir à certains éléments ça peut être
1:54
intéressant de savoir que c'est là je
1:55
vous avouerai que de manière générale on
1:57
en a pas forcément besoin très souvent
1:58
ensuite on a la méthode filter alors
2:00
cette méthode elle va être super
2:02
importante elle va nous permettre de
2:03
filtrer les résultats par exemple
2:05
imaginons que ici j'ai des notes qui
2:07
sont aussi en dessous de la moyenne et
2:09
mon objectif serait de récupérer
2:11
seulement les notes qui sont au dessus
2:13
de la moyenne comment je peux faire
2:15
la première solution serait de créer un
2:17
tableau et ensuite de faire une boucle
2:19
et de rajouter des éléments dans ce
2:21
tableau la méthode filter va nous
2:22
permettre de faire les choses en une
2:23
seule fois donc on va appeler ça good
2:26
not ce sont les bonnes notes on va
2:29
utiliser le tableau note on va utiliser
2:31
les filters et cette méthode prend un
2:34
premier paramètre une fonction qui
2:36
recevra en paramètre la
2:38
chaque élément du tableau donc nous on
2:40
va appeler ça notre au singulier et
2:42
cette fonction elle devra retourner trou
2:44
si on garde la valeur et folle ce sinon
2:46
moi je vais lui dire retourne trou si la
2:49
note est supérieure ou égale à 10 si je
2:52
regarde maintenant mon tableau de bonnes
2:54
notes dans ce cas là je vais voir que ça
2:56
va me donner simplement les notes
2:58
au-dessus de 10 si j'inverse cette
3:00
condition ça me donnera que les notes
3:02
qui sont en dessous de la moyenne donc
3:03
filter peut être très intéressant si
3:05
vous voulez créer un nouveau tableau qui
3:07
ne contient que les valeurs qui
3:08
correspondent à votre critère
3:10
cette fonction de comparaison peut être
3:12
plus ou moins complexe suivant les
3:13
situations
3:16
donc dès que vous avez besoin de
3:17
supprimer des éléments dans un tableau
3:18
c'est ce qu'il faudra utiliser ensuite
3:21
on a la méthode fight la méthode find va
3:23
permettre de récupérer le premier
3:25
élément qui correspondra à la condition
3:26
donc par exemple ici il demande une note
3:30
supérieure à 10 et ça va nous donner du
3:31
coup 12
3:33
on a la même fonction avec findendax qui
3:36
nous permet de nous renvoyer l'index de
3:38
l'élément qui a été trouvé c'est la même
3:40
chose sauf que ça ne va nous renvoyer
3:41
ici l'index 3
3:44
parce que il y a que cette note qui est
3:46
au dessus de 13 on a enfin une de Last
3:49
qui comme find mais qui va nous trouver
3:50
le dernier élément find the last index
3:52
qui comme findex sauf que ça va nous
3:54
trouver le dernier élément c'est 4
3:56
fonctions là peuvent être utiles si
3:58
jamais vous avez besoin d'explorer un
3:59
tableau et de trouver un élément en
4:00
particulier
5:00
une fonction hop cette fonction recevra
5:03
en paramètre la note l'index ou la clé
5:05
et ensuite si je fais un console point
5:08
log et que j'affiche la valeur de la
5:10
note et de l'index mais ça me donnera 12
5:12
à l'index 0 ça me donnera 17 à l'index 1
5:16
et ainsi de suite ainsi de suite donc si
5:18
vous voulez parcourir un tableau ça peut
5:19
être une manière différente par rapport
5:21
au boucle ce qui est intéressant c'est
5:23
qu'on peut créer une fonction de
5:24
parcours qu'on peut réutiliser dans
5:25
plusieurs tableaux là où les boucles ne
5:27
sont pas vraiment réutilisables on a la
5:30
méthode from qui est très utile aussi
5:31
elle elle va permettre en fait de créer
5:33
un tableau à partir de différentes
5:35
choses donc si par exemple on lui passe
5:37
une chaîne de caractère automatiquement
5:39
ça crée un tableau avec les différentes
5:40
lettres si on lui passe un tableau et un
5:43
second paramètre ça permet de créer un
5:45
nouveau tableau où chaque élément se
5:47
verra appliquer cette fonction-là je
5:49
vous avouerai que cette version avec
5:50
deux paramètres je ne l'ai jamais trop
5:52
utilisé parce qu'on va voir qu'il y a
5:53
une autre fonction qui est la fonction
5:54
map qui permet de faire quelque chose de
5:56
très similaire
5:58
le EUR et from va surtout être
6:00
intéressant lorsque vous avez quelque
6:01
chose qui est itérable si vous voulez le
6:03
convertir sous forme de table mais dans
6:06
le JavaScript de base on n'a pas
6:07
forcément trop de choses itérable mis à
6:10
part les chaînes de caractère
6:11
alors la méthode in clouds elle est
6:13
super intéressante elle permet de
6:15
vérifier si une valeur est inclue dans
6:17
un tableau par exemple ici il crée un
6:19
tableau avec toutes les valeurs
6:20
possibles donc charge chien et
6:22
chauve-souris et il demande est-ce que
6:24
dans le tableau des animaux de compagnie
6:26
on achat et là il me répond oui est-ce
6:28
que on a hâte et là il répond Falls donc
6:30
ça ça peut être intéressant plutôt que
6:32
d'écrire des conditions typiquement ce
6:35
qu'on faisait avant c'est est-ce que a
6:37
= A B ou est-ce que la valeur de a est
6:41
égale à C c'est un petit peu pénible et
6:43
surtout si on commence à rajouter des
6:44
conditions c'est un enfer l'avantage
6:47
avec les tableaux c'est qu'on peut
6:48
facilement écrire on va écrire B C et D
6:53
et on va lui dire est-ce que ce tableau
6:55
là inclut la valeur de 1 et c'est
6:57
beaucoup plus simple à écrire et c'est
6:59
beaucoup plus modulable donc voilà la
7:02
méthode inkloud elle est plutôt pratique
7:06
donc ensuite on a indexOf c'est un peu
7:08
comme le find sauf que vous pouvez
7:10
directement lui passer une valeur et ça
7:12
va trouver la valeur dans le tableau et
7:13
vous renvoyer l'index à laquelle la
7:15
valeur existe ça peut notamment être
7:17
utilisé pour savoir si une valeur existe
7:19
dans le tableau ça renvoie moins un si
7:22
la valeur que vous avez rentrée n'existe
7:23
pas on utilisait notamment beaucoup ça
7:25
avant que le include apparaissent donc
7:27
si vous voyez dans du code que l'on
7:29
teste est-ce que l'index est égal à -1
7:30
ça c'est totalement remplaçable par la
7:33
méthode inclut
7:35
donc la méthode de join on l'a vu ça
7:37
permet de joindre les différents
7:38
éléments avec une un caractère de
7:40
liaison ça c'est très pratique aussi
7:42
mais il faut en avoir besoin la méthode
7:44
clé va nous permettre de nous renvoyer
7:45
les clés on en aura pas forcément
7:47
beaucoup besoin le Last index off c'est
7:50
comme index off mais dans l'autre sens
7:51
la méthode map ça c'est une méthode qui
7:54
est très très importante et que vous
7:55
allez utiliser très souvent cette
7:57
méthode là elle prend un premier
7:59
paramètre une fonction qui va permettre
8:00
d'altérer les éléments si vous voulez
8:02
vous pouvez imaginer cette fonction
8:03
comme une fonction de transformation
8:05
d'un tableau elle prend un tableau de 10
8:07
éléments et elle va vous le transformer
8:08
en un tableau de 10 éléments où on
8:10
applique une fonction de transformation
8:11
à chaque fois typiquement ici ce qu'ils
8:14
disent c'est que ils disent X sera égal
8:16
à X multiplié par 2 dans ce cas là si on
8:19
passe ce tableau là on obtiendra en
8:22
résultat un tableau où toutes les
8:23
valeurs ont été multipliées par deux
8:24
donc c'est vraiment très utile lorsque
8:26
vous avez besoin de transformer des
8:28
tableaux si je vous montre un autre
8:30
exemple qui sera peut-être un petit peu
8:31
plus parlant on imagine qu'on a un
8:33
tableau de personnes et dans ce tableau
8:35
là on a des objets avec le first name
8:37
qui contient le prénom de la personne et
8:40
un last name qui contient le nom et on
8:43
s'imagine avoir plusieurs personnes dans
8:46
ce tableau là donc on va écrire Jane on
8:48
va écrire Marc et on va écrire Manon
8:52
maintenant j'aimerais bien avoir une
8:54
chaîne de caractère qui contient une
8:55
ligne avec marqué John do une autre
8:57
ligne avec Jane do une autre ligne avec
8:59
Margot et ainsi de suite ainsi de suite
9:01
donc ce que je peux faire c'est lui dire
9:03
je pars de mon tableau de personnes je
9:05
vais utiliser la méthode map dans cette
9:09
méthode map je vais du coup lui passer
9:11
un paramètre une fonction qui recevra la
9:13
personne et cette fonction elle
9:16
retournera
9:17
personne.frname où là limite je vais
9:20
l'appeler P si on peut gagner un petit
9:22
peu de temps donc P point first name +
9:25
un espace plus p.nase name j'aurais pu
9:28
utiliser des bactéries ici aussi
9:30
ça ça va me donner un nouveau tableau
9:32
avec les différentes personnes si je
9:34
fais un console point log de ce résultat
9:37
là donc on fait bien attention aux
9:39
parenthèses voilà
9:42
si je regarde dans la console j'obtiens
9:44
maintenant un tableau avec John Doe Jane
9:46
do McDo et ainsi de suite ainsi de suite
9:48
et ce que je peux faire c'est lui dire
9:49
de faire un Joy et de faire un join avec
9:52
un caractère de saut de ligne et là
9:54
j'obtiens la liste de mes utilisateurs
9:56
comme ça donc vous voyez la fonction map
9:59
elle est pas mal puissante pour
10:00
convertir des choses
10:02
mais il faut bien prendre en compte que
10:03
map elle vous renverra un tableau qui a
10:06
la même taille que le tableau original
10:07
chaque élément est en modifié et notre
10:09
fonction pour faire des trucs un petit
10:10
peu plus poussé mais on va l'avoir juste
10:12
après donc on continue vous avez ensuite
10:15
pop alors pop ça permet de retirer le
10:18
dernier élément d'un tableau attention
10:20
cette méthode là elle affecte le tableau
10:22
original donc si vous faites un pop et
10:25
que vous regardez le tableau après coup
10:26
la dernière valeur a été modifiée c'est
10:29
un petit peu pénible il y a beaucoup de
10:30
fonctions en JavaScript qui modifie les
10:32
objets originaux mais et cette fonction
10:35
en fait partie on verra qu'il y a
10:36
d'autres manières d'extraire le dernier
10:37
élément si on le souhaite ensuite on a
10:40
la méthode push qui permet elle de
10:41
d'envoyer un nouvel élément dans notre
10:43
tableau et elle modifie le tableau
10:45
original et ensuite on a la méthode
10:47
radius alors cette méthode radius c'est
10:50
une des méthodes qui à mon sens est plus
10:51
compliqué qu'en débute mais c'est aussi
10:53
celle qui offre le plus de puissance
10:55
donc on a eu le problème déjà
10:56
précédemment quand on avait besoin de
10:58
calculer la somme des notes on avait été
11:00
obligé de faire une boucle et il n'y a
11:03
rien de mal à faire une boucle mais il y
11:05
a une manière encore plus facile
11:06
d'écrire les choses avec le radius donc
11:09
comment il fonctionne on va mettre un
11:10
console point log on va utiliser nos
11:13
notes et on va utiliser la méthode
11:17
cette méthode elle prend en premier
11:18
paramètre un callback ce callback il
11:21
aura deux paramètres un premier que l'on
11:23
va appeler un accumulateur en général on
11:25
va l'appeler ACC comme accumulateur et
11:27
en second paramètre il va prendre la
11:29
valeur courante donc ici ça serait la
11:31
note sur laquelle on est donc un peu
11:33
comme la fonction map ce second argument
11:35
va permettre de parcourir chacune des
11:37
notes à l'intérieur de cette fonction on
11:40
va retourner une valeur mais pour
11:42
l'instant on va pas trop s'en occuper
11:43
ensuite en second paramètre on va lui
11:45
donner une valeur de départ cette valeur
11:47
sera ensuite placée dans l'accumulateur
11:49
donc si je veux faire une somme si vous
11:52
souvenez quand vous avez fait notre
11:53
boucle on avait commencé à créer une
11:54
variable somme qui est égale à 0 donc là
11:57
je lui dis que ça sera égal à zéro cette
11:59
fonction sera donc appelée la première
12:01
fois avec l'accumulateur qui sera égal à
12:03
zéro et la première note
12:05
ce qu'elle devra faire cette fonction
12:06
c'est qu'elle devra retourner la
12:08
nouvelle version de l'accumulateur donc
12:10
je peux lui dire ici retourne
12:11
l'accumulateur auquel on rajoute la note
12:14
courante
12:16
ensuite ça va prendre cette nouvelle
12:17
valeur et ça va réappeler la méthode
12:19
pour le second élément on aura
12:21
l'accumulateur qui aura la valeur
12:22
précédente et note qui aura la valeur 18
12:25
ça va faire le code et ensuite on va
12:27
l'utiliser une troisième fois vu qu'on a
12:29
trois éléments l'accumulateur sera la
12:31
valeur du retour précédent et note aura
12:33
la valeur 19 et à la fin ça va nous
12:36
renvoyer le résultat si j'écris ça de
12:38
cette manière là et que je regarde dans
12:40
ma console j'ai bien ici 49 j'ai comme
12:43
ça écrit une fonction qui permet de
12:45
faire la somme des éléments d'un tableau
12:46
on pourrait même la raccourcir en
12:49
retirant la colade à ce niveau là et en
12:51
l'écrivant sur une seule ligne c'est
12:53
beaucoup plus court que la boucle que
12:55
l'on avait écrit c'est peut-être un
12:57
petit peu moins lisible je vous
12:58
l'accorde mais voilà comment fonctionne
12:59
l'accumulateur
13:01
donc cette fonction sera très utile
13:03
lorsque vous avez un tableau qui
13:04
contient des éléments et à en sortie
13:06
vous voulez qu'une seule valeur là il
13:09
faudra utiliser radio il y a vraiment
13:10
trois fonctions qui sont vitales sur les
13:13
tableaux ce sont vraiment les fonctions
13:15
map filter et reviews pour tout ce qui
13:17
est manipulation du tableau avec ces
13:18
trois fonctions vous pouvez faire
13:19
globalement la plupart des opérations
13:21
donc maps c'est pourquoi convertir un
13:23
tableau dans un autre tableau avec des
13:26
valeurs différentes mais qui aura la
13:27
même taille filter c'est pour retirer
13:29
des éléments d'un tableau en fonction
13:30
d'une d'un filtre de condition et radius
13:34
ça permet de réduire les différentes
13:36
valeurs et d'obtenir qu'une valeur en
13:37
sortie très pratique notamment pour les
13:39
sommes ou des accumulations
13:41
voilà pour la partie radius donc si je
13:44
continue ensuite on a regius right ça
13:47
permet de faire la même chose mais
13:48
plutôt que de lire les éléments de
13:49
gauche à droite ça lie les éléments de
13:51
droite à gauche ensuite on arrive verse
13:53
qui permet d'inverser un tableau faites
13:55
attention sans modifie le tableau
13:56
original on a la méthode shift donc
14:00
cette méthode elle fonctionne un peu
14:01
comme la méthode pop sauf qu'elle va
14:03
retirer le premier élément d'un tableau
14:05
et modifier le tableau original pareil
14:07
on verra avec d'autres syntaxes
14:09
lorsqu'on parlera du sucre syntaxique
14:10
une manière un petit peu plus simple de
14:12
faire ça on a la méthode slice qui va
14:15
permettre de récupérer une partie du
14:17
tableau donc si je fais animal ce point
14:19
slice 2 ici il va commencer à l'élément
14:22
2 et va nous récupérer l'ensemble des
14:24
éléments restants donc là ça nous
14:26
donnera le chameau le canard et
14:29
l'éléphant vous pouvez lui donner un
14:31
second paramètre qui sera l'index auquel
14:34
vous souhaitez vous arrêter dans ce
14:36
cas-là ça voudra dire prends tous les
14:37
éléments du tableau à partir de l'index
14:39
2 jusqu'à l'index 4
14:41
donc l'index 2 c'est ici l'index 4 c'est
14:44
éléphant
14:46
et du coup il prendra tout ce qui est
14:47
entre l'index 2 et l'index 4 donc
14:49
compris donc ça donnera chameau et
14:52
canard si vous lui donnez une valeur
14:53
négative dans ce cas-là il va commencer
14:55
par la droite donc si vous donnez -1
14:57
mais il va s'arrêter là - 2 il
14:59
s'arrêtera au canard et ainsi de suite
15:00
ainsi de suite une propriété
15:02
intéressante de slice c'est que ça
15:03
permet de créer un nouveau tableau je
15:06
vous donne un exemple concret imaginons
15:08
que ici j'ai envie d'inverser les notes
15:10
si dans ma console je fais un autre
15:12
point riverse le problème on l'a vu
15:14
c'est que on a inversé le tableau
15:16
original et on se retrouve du coup avec
15:17
la variable note qui a été modifiée pas
15:20
très pratique ce qu'on peut faire c'est
15:22
lui dire j'aimerais bien créer une slice
15:25
et je reverse cette slice là j'obtiens
15:29
alors les notes qui ont été inversées si
15:32
je regarde note maintenant on voit que
15:34
les notes n'ont pas été modifiées parce
15:36
qu'en créant une slice on crée un
15:38
nouveau tableau et ce tableau là est
15:40
inversé donc c'est ce nouveau tableau
15:42
qui est inversé pas le tableau original
15:44
encore une fois quand on parlera du
15:46
chapitre sur le sucre syntaxique je sais
15:48
je vous le tisamment mais vous aurez une
15:50
autre manière un petit peu plus élégante
15:52
d'écrire ça mais c'est toujours
15:54
intéressant parce que vous allez
15:55
peut-être retrouver dans du vieux code
15:56
cette stratégie là pour créer un nouveau
15:58
tableau à partir d'un autre
16:00
donc ensuite on a la méthode somme que
16:02
je n'utilise pas forcément beaucoup
16:04
sorte qui va permettre d'organiser les
16:07
éléments dans un tableau ensuite vous
16:09
allez splice je vous avoue j'utilise pas
16:11
très souvent mais ça permet de modifier
16:12
un élément spécifiquement dans un
16:14
tableau concrètement on peut le faire
16:16
autrement donc c'est vrai qu'on a
16:17
tendance à pas trop l'utiliser et enfin
16:19
la dernière méthode c'est la méthode
16:21
unshift donc cette méthode là ce qu'elle
16:23
permet de faire c'est qu'elle permet
16:24
d'insérer des données un peu comme push
16:26
sauf que elle va les insérer au début du
16:28
tableau voilà c'est pas forcément très
16:31
utile mais si jamais je vous avais
16:32
besoin c'est important de savoir que
16:33
elle s'appelle comme ça plutôt que push
16:36
donc voilà pour les méthodes sur les
16:38
tableaux donc maintenant on va parler
16:39
des objets vous allez voir il y a
16:42
beaucoup moins de méthodes sur les
16:43
objets c'est beaucoup plus simple
16:45
donc si je descends un petit peu on va
16:47
commencer par le signe le sign va vous
16:50
permettre d'assigner des propriétés d'un
16:52
objet à un autre objet donc on a un
16:54
exemple ici on a un objet a qui a les
16:57
propriétés A et B un objet qui est les
16:59
propriétés B et C et lorsqu'on fait un
17:01
object points il a signé les valeurs de
17:03
l'un dans l'autre on verra dans la
17:05
partie sucre syntaxique qu'il existe
17:07
aujourd'hui une nouvelle syntaxe pour
17:08
faire ça et finalement ça rend le
17:10
objectif un petit peu obsolète un petit
17:14
détail intéressant qui est valable sur
17:16
l'objet mais aussi avec la syntaxe que
17:18
vous verrez plus tard c'est que ça
17:19
permet de créer un nouvel objet si je
17:21
vous refais un exemple dans la console
17:23
je vais extraire la première personne
17:25
dans une variable voilà hop donc on va
17:29
créer une nouvelle constante personnes
17:30
et on va lui dire de mettre ça voilà si
17:34
je regarde ma personne je vois que
17:36
j'obtiens bien mes informations mais si
17:38
je modifie le first name et que je mets
17:40
Jane mais là ce que j'ai fait c'est que
17:42
j'ai modifié l'objet original et je me
17:45
retrouve finalement avec une toute
17:46
nouvelle personne avec le object.side
17:49
vous allez pouvoir en fait créer un
17:51
nouvel objet mais qui réutilise les
17:53
mêmes propriétés que notre en écrivant
17:55
les choses de cette manière là en fait
17:57
je suis en train de créer un nouvel
17:58
objet et dans cette nouvelle objet
18:00
j'assigné les propriétés que l'on a dans
18:02
personne si je crée donc une nouvelle
18:04
variable à partir de ça si je modifie
18:07
quelque chose dans cette nouvelle
18:08
variable ça me permet de modifier une
18:11
propriété je me retrouve bien avec une
18:13
personne qui s'appelle le Jane do sans
18:15
avoir modifié pour autant la personne
18:17
originale donc c'était notamment utilisé
18:19
pour ça donc dans certains vieux codes
18:22
vous pourriez retrouver cet élément de
18:23
syntaxe maintenant on a une autre
18:26
syntaxe pour faire ça aujourd'hui on
18:27
peut écrire les choses de cette manière
18:28
là mais on en revienne on reviendra
18:30
dessus un petit peu plus tard lorsque
18:31
l'on parlera du sucre syntaxique ensuite
18:34
on a la méthode Create donc la méthode
18:36
de create elle permet de créer un nouvel
18:38
objet en utilisant le prototype d'un
18:40
autre objet
18:41
donc c'était aussi très utile au moment
18:43
où on n'avait pas trop l'utilisation des
18:45
classes avec les classes ces méthodes-là
18:47
sont devenues beaucoup moins pratiques
18:49
mais avant on pouvait utiliser cette
18:51
méthode là pour gérer le système de
18:53
prototype ensuite on a la méthode define
18:55
property qui permet de définir une
18:57
propriété sur un objet alors on peut se
19:00
demander quel est l'intérêt de ce truc
19:01
là concrètement vous n'allez pas trop
19:03
l'utiliser mais ça permet peut-être
19:04
d'expliquer une chose imaginons je crée
19:07
une classe A je crée un 7 heures pour un
19:10
champ qu'on va appeler field et dans ce
19:12
secteur je fais un console point log et
19:15
l'eau maintenant je vais créer dans le
19:17
constructeur
19:19
quelque chose en faisant vice.field et
19:22
je vais lui donner la valeur 3 donc là
19:25
il râle un petit peu parce que j'ai pas
19:26
précisé de valeur
19:28
si au niveau de ma console je fais une
19:30
nouvelle instance de cette classe là et
19:33
que je regarde ma console il l'affiche
19:35
bien le hello donc on voit que ce
19:37
secteur est appelé lorsque je fais
19:39
vis.field = 3 par contre si jamais je
19:42
modifie ça et que je venais définir
19:44
cette propriété directement au niveau de
19:47
l'objet comme ça field également 3
19:50
si je sauvegarde et que je refais ma
19:52
constante a également on va voir que ce
19:54
secteur là ne va pas être appelé il ne
19:57
va pas être appelé parce que cette
19:58
propriété là va être directement définie
20:00
sur l'objet un petit peu de cette
20:02
manière là avec le define properties et
20:04
ça pour effet de complètement over-hide
20:07
le seter d'ailleurs si je fais un
20:08
a.field = 4 on voit que le console point
20:11
log du secteur n'est pas appelé file ne
20:13
sera plus quelque chose accessible via
20:15
le seter ça sera une simple propriété et
20:18
c'est comme si vous n'aviez pas du tout
20:19
écrit ça si je reviens à ce niveau là on
20:22
va directement écrire le constat a = new
20:25
a ici si maintenant je fais un object
20:28
donc point define alors on peut faire
20:31
soit dit find properties soit define
20:33
property là moi je vais juste en définir
20:35
une seule donc je vais utiliser define
20:36
property je lui passe l'objet je lui
20:38
donne le nom à ma propriété field et je
20:41
vais lui donner ensuite un objet avec la
20:43
valeur donc je vais dire ici que je veux
20:45
la valeur 3 si je fais ça on voit que
20:47
mon objet a maintenant a bien une
20:49
propriété qui a été défini et j'ai entre
20:52
guillemets outre passé le 7 heures voilà
20:54
donc c'est pas forcément utile de savoir
20:56
utiliser ces méthodes là parce que vous
20:58
en aurez jamais trop besoin en vrai mais
21:00
c'est intéressant de savoir que c'est
21:02
Issa qui est utilisé en interne lorsque
21:03
vous définissez les propriétés et c'est
21:05
pour ça que vous sentez les 7 heures
21:07
dans ce cas là
21:09
ensuite on a object pointes on
21:11
remarquera d'ailleurs que sur les objets
21:12
la plupart des méthodes qui nous
21:14
intéressent elles ne sont pas
21:15
disponibles sur le prototype elles sont
21:16
en directement disponibles au niveau du
21:18
de l'objet directement je sais pas trop
21:20
pourquoi ils ont fait comme ça mais
21:22
c'est comme ça en Javascript donc intriz
21:24
en fait ça va vous permettre de renvoyer
21:26
un tableau avec les clés et les valeurs
21:27
alors c'est assez spécifique mais
21:29
revenons-en à notre personne si j'essaie
21:33
dans ma console de faire un objectif
21:36
et de lui passer personne on voit qu'on
21:39
obtient un tableau de taille 2 parce que
21:41
j'ai deux propriétés et si je regarde le
21:44
premier tableau c'est l'approprier et la
21:47
valeur associée le second c'est la
21:49
propriété la valeur associée ça ça va
21:51
être intéressant notamment lorsqu'on va
21:53
parler de la déstructuration donc on en
21:55
parlera dans le chapitre sur le sucre
21:56
syntaxique ça permet par exemple de
21:58
pouvoir faire une boucle for off sur les
22:00
objets chose qui ne nous était pas
22:01
autorisées donc dans ce cas là ça permet
22:03
de faire une boucle et de récupérer à la
22:05
fois la clé et la valeur dans les
22:07
propriétés de l'objet
22:10
ensuite on a object point frise donc ça
22:12
c'est un petit peu particulier ça a créé
22:14
notamment aussi à l'optimisation de la
22:15
mémoire mais ça permet de geler un objet
22:17
ça veut dire que cet objet ne peut plus
22:19
être modifié ça peut être intéressant
22:21
pour garantir une certaine sécurité mais
22:24
en dehors de ça c'est pas forcément
22:25
quelque chose qui va vous intéresser en
22:27
tout cas pour l'instant à votre niveau
22:28
ensuite on va descendre toutes ces
22:30
méthodes là sont pas forcément utiles je
22:31
vous laisse les explorer si ça vous
22:33
intéresse vous avez le object.e.s ça
22:36
c'est un opérateur de comparaison c'est
22:39
un peu comme un triple égal au final si
22:40
ce n'est que ça a des conditions un peu
22:42
spécifiques qui sont expliquées ici
22:44
c'est que ça permet de comparer un zéro
22:46
négatif un zéro positif et ça permet
22:48
aussi de comparer de notre number
22:50
ensemble encore une fois c'est très
22:53
spécifique c'est intéressant pour la
22:54
culture générale mais en dehors de ça ça
22:56
ne vous servira pas c'est à dire que si
22:58
vous comparez de notre number ensemble
23:00
il vous dit que ce ne sont pas des deux
23:02
objets égales alors que si vous faites
23:03
un object.e.s et que vous comparez de
23:06
notes number ensemble bah lui il vous
23:08
dira que c'est vrai
23:10
voilà encore une fois c'est tellement
23:12
spécifique que de toute façon vous en
23:13
aurez pas besoin tout de suite alors on
23:16
continue
23:17
qu'est-ce que j'ai noté ensuite j'ai
23:19
noté Keys qui était intéressant donc ils
23:21
en fait ça va vous permettre d'avoir un
23:23
tableau de toutes les clés donc ça c'est
23:25
intéressant pour pouvoir ensuite faire
23:26
une boucle justement si vous êtes
23:28
intéressé par toutes les clés qui sont
23:30
au niveau de votre objet personnel vous
23:31
faites ça et vous obtenez un tableau qui
23:34
contient first name et la sname si vous
23:36
êtes intéressé seulement par les valeurs
23:37
ben vous avez la même méthode mais qui
23:39
s'appelle vadios et dans ce cas là ça
23:40
vous donne un tableau des valeurs qui
23:43
correspondent aux différentes propriétés
23:44
ça peut être intéressant voilà dans ces
23:47
deux cas et après vous pouvez faire une
23:48
boucle sur les clés ou sur les valeurs
23:50
et faire le traitement qui qui vous
23:53
intéresse et globalement c'est tout ce
23:55
qu'il y a connaître sur les objets
23:56
concrètement si vous ne devez retenir
23:58
que quelques fonctions je dirais que
24:01
intriz est utile si vous avez besoin
24:03
ensuite de faire des boucles et
24:04
récupérer que les valeurs values et quiz
24:07
sont utiles les autres ne servent plus
24:08
aujourd'hui parce qu'avec les nouvelles
24:09
syntaxes vous n'en aurez pas besoin
24:12
enfin on va finir sur les fonctions
24:14
alors je sais pas sur les fonctions si
24:16
on a une référence donc on va peut-être
24:19
plutôt utiliser
24:20
Uplay pour essayer de trouver voilà le
24:23
prototype donc sur les fonctions vous
24:24
avez assez peu de méthode qui sont
24:26
disponibles au niveau du prototype on a
24:28
déjà rapidement parlé avec le système de
24:30
vis mais c'est trois méthodes là et
24:33
justement elles permettent de jouer avec
24:34
vice pour vous les expliquer on va se
24:37
créer ici une fonction
24:40
et cette fonction elle fera tout
24:42
simplement un console.log de vis
24:47
donc la première méthode qui est
24:48
intéressante c'est byte donc bind va
24:51
vous permettre de créer une nouvelle
24:52
fonction à partir d'une fonction en
24:54
changeant le contexte de vis donc vous
24:56
faites hello point bye 3 et maintenant
24:59
dès que vous allez appeler hello vice
25:01
aura la valeur 3
25:03
c'est intéressant parce que ça vous
25:04
permet d'ancrer la valeur et ensuite à
25:07
ne pourra plus être modifié c'est à dire
25:08
que si je fais un et deux je vois que ça
25:11
me donne bien le nombre 3 mais si je
25:13
décide de faire un hello 2
25:16
et de l'appeler en lui passant une autre
25:19
valeur de vis 4 par exemple ça me
25:22
donnera toujours le nombre 3 une méthode
25:24
qui a été bindée à une valeur de vis qui
25:27
est définie et cette valeur là ne pourra
25:29
pas être modifié par la suite c'est un
25:30
peu comme finalement une fonction
25:31
fléchés ça peut être intéressant donc si
25:34
jamais vous créez une fonction qui est
25:36
derrière ça vous donnera la même chose
25:39
c'est à dire si vous faites un hello 2
25:40
il va ignorer le bind 4 que vous avez
25:43
mis parce que là on a bindé la valeur de
25:45
vis
25:46
les autres méthodes va correspondre à la
25:48
même chose
25:49
Uplay permet d'appeler une méthode en
25:51
les passant la valeur de vis et un
25:52
tableau qui correspondra aux différents
25:54
arguments et la méthode call permet de
25:57
faire un peu la même chose que le uplice
25:58
si ce n'est que on mettra les arguments
26:00
les unes derrière les autres donc ça ça
26:02
va être intéressant vraiment dans des
26:03
cas spécifiques si jamais vous avez des
26:05
erreurs parce que vous utilisez vis dans
26:06
vos fonctions une de ces trois fonctions
26:08
là va vous aider en dehors de ça il y a
26:11
pas plus à dire et là on a terminé avec
26:13
ce petit tour d'horizon des différentes
26:15
fonctions que vous avez à connaître pour
26:17
la suite de cette formation donc
26:19
n'hésitez pas toujours à revenir sur la
26:21
documentation pour vous souvenir de tous
26:23
les objets qui sont standard dans le
26:24
Javascript voir un petit peu comment il
26:26
fonctionne et voir leur prototype est-ce
26:29
qu'il est possible de faire dessus donc
26:31
j'espère que ça pas été trop pénible
26:32
comme ça de me voir lister les fonctions
26:34
mais je suis désolé il y a vraiment pas
26:35
le choix à ce niveau là et je vous donne
26:36
rendez-vous dans le chapitre suivant
