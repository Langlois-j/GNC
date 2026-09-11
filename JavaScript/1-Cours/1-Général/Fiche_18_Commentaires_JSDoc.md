# Apprendre le JavaScript : Les modules

Video : https://www.youtube.com/watch?v=9U-RgCzN9mI

## Transcription

ah bienvenue dans ce nouveau chapitre je
0:01
vous propose de parler des commentaires
0:02
donc on a déjà vu dans un chapitre
0:04
précédent comment écrire des
0:05
commentaires en termes de syntaxe mais
0:07
on n'a pas forcément parlé de leur rôle
0:08
au niveau du code donc tous les bons
0:10
développeurs vous donneront comme
0:11
conseil de bien commenter votre code
0:13
pour pouvoir le comprendre par la suite
0:15
et un mauvais réflexe malheureusement
0:16
c'est d'interpréter ce conseil là comme
0:18
écrire du code partout donc typiquement
0:21
moi je vais forcer un petit peu le trait
0:22
mais on pourrait avoir des commentaires
0:23
qui ressemblent à ça donc dans ce cas là
0:26
on est en train de tout simplement
0:27
expliquer ce que fait la ligne suivante
0:29
il faut comprendre qu'au-delà des
0:31
commentaires votre manière d'écrire le
0:32
code votre manière de nommer les
0:34
variables les fonctions ou les classes
0:36
apportent déjà de la compréhension sur
0:38
ce que fait votre code et vous n'avez
0:40
pas forcément besoin de réexpliquer les
0:42
choses au travers d'un commentaire
0:43
l'objectif des commentaires doit être
0:45
avant tout de rajouter du contexte et
0:47
d'expliquer pourquoi une telle ligne a
0:49
été rajoutée plus que ce qu'elle fait
0:50
parce que pour comprendre ce qu'elle
0:52
fait il suffit tout simplement de lire
0:53
le code si on reprend des exemples de
0:55
chapitre précédent ici j'ai une fonction
0:57
can drive vu que cette fonction commence
1:00
par canne moi je sais en général que
1:02
elle va retourner un boulet donc j'ai
1:04
pas forcément besoin de rajouter des
1:05
informations dessus par contre on voit à
1:07
l'intérieur que ce qui est peut-être
1:09
perturbant c'est cette condition là
1:11
peut-être que c'est lié à un texte de
1:13
loi c'est lié à des conditions
1:14
particulières donc dans ce cas-là c'est
1:16
intéressant de rajouter des informations
1:17
sur pourquoi on a mis cette condition là
1:20
donc typiquement ici on pourrait
1:21
rajouter avant un petit commentaire en
1:23
disant la loi aux États-Unis est
1:27
différente bon là on va mettre des
1:29
points de suspension et vous pouvez même
1:30
mettre des liens vers le texte de loi en
1:32
question pour que la personne qui
1:34
retombe sur ce code là plutôt que d'être
1:36
surprise et de se dire mais pourquoi il
1:37
a rajouté cette condition là et puisse
1:39
comprendre directement pourquoi vous
1:40
avez fait ça au-delà de ça vous avez
1:42
aussi une manière un petit peu plus
1:44
formatée de commenter les choses afin
1:46
d'avoir une meilleure auto-complétion au
1:48
niveau de votre éditeur donc on le voit
1:50
lorsque l'on écrit notre code l'éditeur
1:53
va automatiquement offrir de
1:54
l'autocomplétion c'est à dire que
1:55
lorsque je fais can drive et que je mets
1:57
une parenthèse il me rappelle les
1:59
paramètres qui sont attendus et ils me
2:01
dis âge de points ENI country 2.ni et
2:04
ensuite il me dit deux points bullean
2:05
donc c'est une syntaxe un petit peu
2:06
particulière mais après le deux points
2:08
en fait on va avoir le type et quand il
2:10
ne connaît pas le type il va vous mettre
2:11
ENI le 2 points qui se situe après la
2:14
parenthèse c'est le type de retour de
2:15
cette fonction-là donc là il est
2:17
automatiquement capable d'analyser le
2:18
code et de voir que vu qu'on ne retourne
2:20
que des boulets dans ce cas-là le retour
2:22
de cette fonction est un boulet pour des
2:24
fonctions un petit peu plus complexes si
2:26
on reprend l'exemple de la somme par
2:27
exemple il n'est pas capable de s'en
2:29
sortir si je survole cette variable là
2:31
il me dit aussi que c'est ENI donc il
2:33
est pas capable de connaître le type des
2:35
arguments ni le type de retour donc ça
2:37
ne nous aide pas à utiliser ce code là
2:39
donc pour nous aider pour ça et pour
2:41
aider l'éditeur on a la possibilité
2:42
d'utiliser la JS doc donc JS doc c'est
2:46
un format particulier de commentaires
2:47
que vous allez pouvoir écrire pour
2:49
guider les autres développeurs et qui va
2:51
aussi être compris par l'éditeur et qui
2:53
va permettre d'avoir une meilleure
2:54
auto-complétion
2:56
alors pour utiliser cette JS doc il y a
2:58
pas d'outils ou quoi que ce soit à
3:00
installer il suffit justement de décrire
3:02
les commentaires en respectant leurs
3:03
syntaxe donc pour écrire un commentaire
3:05
au dessus d'une fonction à faire Slash
3:07
et toile donc ça ça permet de commenter
3:09
un commentaire et on va rajouter un
3:10
deuxième étoile automatiquement vous
3:12
voyez que mon éditeur ici propose de
3:15
l'autocomplétion si j'appuie sur Entrée
3:18
il va déjà nous mettre une structure de
3:20
code donc la première ligne ça permet en
3:23
fait d'expliquer ce que fait cette
3:24
fonction-là comme je vous l'ai dit le
3:26
nom de la fonction est suffisamment
3:27
évocateur mais vous pouvez rajouter des
3:29
descriptions à ce niveau là donc on
3:31
mettra permet de savoir si l'utilisateur
3:36
peut conduire
3:38
et après si vous le voulez il faut pas
3:40
hésiter à rajouter des informations par
3:41
exemple on mettra en concordance avec
3:44
les textes de droite s'il y a besoin de
3:46
préciser des trucs supplémentaires en
3:49
dessous on va avoir un arobase Parme
3:51
donc ce arobase param permet de dire je
3:54
vais te donner des informations sur un
3:55
des paramètres et c'est le paramètre h
3:57
et on a ensuite des petites accolades
4:00
avec une astérisque dans ces petites
4:02
accolades on va pouvoir préciser le type
4:03
que l'on attend pour se paramètre là
4:05
donc l'ensemble des types est disponible
4:07
normalement quelque part je crois que
4:10
c'est dans le arobase type il faut
4:12
descendre un petit peu voilà vous avez
4:14
quelques exemples des types que vous
4:15
pouvez utiliser mais globalement ça
4:17
correspond au type que l'on avait évoqué
4:18
dans les premiers chapitres lorsqu'on
4:20
avait découvert les variables donc si
4:22
vous voulez un number vous mettez number
4:24
en minuscule pour le pays par contre
4:27
j'ai besoin de préciser un petit peu
4:28
plus de choses donc là on va mettre code
4:30
pays
4:31
sur deux caractères
4:34
je vais replier la partie de gauche
4:36
parce que sinon on va pas avoir assez
4:37
d'espace après au niveau du return on
4:40
peut spécifier ce que l'on renvoie bon
4:42
il était capable ici de le comprendre
4:43
mais on peut être précis donc je lui dis
4:45
ça va renvoyer un boule et âne voilà
4:48
maintenant réessayant d'utiliser notre
4:50
fonction je crée une constante a et je
4:53
vais utiliser kan drive lorsque je mets
4:56
en parenthèse on voit qu'il me demande
4:58
l'âge il m'affiche la description de la
5:00
méthode donc maintenant je vais rentrer
5:02
18 je mets virgule le pays et on voit
5:05
que on dans l'auto compression on a plus
5:06
d'explications sur ce paramètre là donc
5:08
si quelqu'un par exemple commence à
5:10
rentrer dans votre code et utilise cette
5:12
fonction là il aura plus d'informations
5:14
sur comment utiliser votre fonction et
5:15
ça c'est super pratique donc là on va
5:18
rentrer le code pays sur deux chiffres
5:19
sur deux lettres plutôt et voilà au
5:22
niveau de cette variable a on obtient
5:24
bien un boulet de toute façon ça il
5:27
était capable de le prévoir l'avantage
5:29
c'est que certains éditeurs seront
5:30
carrément capables de vous indiquer que
5:32
vous avez des alertes si par exemple
5:33
vous mettez ici une chaîne de caractères
5:35
certains éditeurs pourront vous dire
5:36
qu'il y a une erreur bon là dans cette
5:39
version là de VS code j'ai pas
5:40
l'impression qu'il râle beaucoup mais ça
5:42
peut être intéressant aussi à ce niveau
5:43
là parce que ça offre une sécurité
5:44
supplémentaire alors maintenant dans les
5:47
types que vous pouvez mettre on a number
5:49
string bullean pour les objets en mettra
5:51
object mais ce que l'on pourra aussi
5:53
faire c'est préciser la forme de l'objet
5:55
alors on va plutôt créer une nouvelle
5:57
fonction
5:59
qu'on va appeler fetch poste qui
6:02
récupérerait des articles peu importe
6:04
donc si on veut typer le retour à ce
6:07
niveau là on mettra @ returns vous
6:09
pouvez aussi simplement mettre return
6:11
c'est un alias les deux fonctionnent et
6:13
on mettra une accolade et à l'intérieur
6:15
on mettra le type qui est un objet on
6:17
précisera qu'on aura un ID deux points
6:19
le type associé number ensuite on aurait
6:22
un teele qui serait une chaîne de
6:24
caractère et on pourrait même avoir des
6:26
objets imbriqués et un body qui serait
6:28
une chaîne de caractère
6:29
si j'utilise maintenant cette méthode
6:31
fech post et que je regarde la variable
6:35
a on voit qu'il comprend que c'est un
6:37
objet qui contient ces différentes
6:38
propriétés ce qui est super intéressant
6:40
c'est qu'après lorsque vous faites un a
6:42
point quelque chose il vous propose de
6:44
l'autocomption à ce niveau là donc ça
6:46
c'est plutôt cool pour les tableaux vous
6:49
avez la possibilité de préciser que
6:51
c'est un tableau en mettant un
6:54
avec un A majuscule ce que vous pouvez
6:56
faire c'est lui préciser le type des
6:58
informations qu'il y a à l'intérieur
6:59
pour cela on utilisera un signe
7:02
inférieur puis un signe supérieur et à
7:05
l'intérieur on pourra mettre le type
7:06
associé donc là on est en train de
7:08
préciser que dans ce tableau on aura que
7:10
des chaînes de caractères si je regarde
7:12
un petit peu a on a aussi cette notation
7:15
là qui consiste à mettre le type suivi
7:17
de crochet donc on peut faire un tableau
7:20
de chaînes de caractères ou faire string
7:22
crochet c'est la même chose si on avait
7:26
une méthode qui est renvoyé des articles
7:27
hop on pourrait tout simplement
7:29
reprendre notre syntaxe ici et lui dire
7:32
ça c'est un tableau d'objets qui
7:35
ressemble à ça donc je peux maintenant
7:38
utiliser ma méthode fetch post lorsque
7:40
je fais un a mon éditeur va comprendre
7:43
que c'est un tableau on voit qu'on a
7:44
toutes les méthodes sur les tableaux je
7:46
peux lui demander de récupérer l'élément
7:47
l'index zéro et il va comprendre que
7:50
c'est un article et va me proposer
7:51
toujours c'est ses propriétés là et ça
7:54
c'est super pratique
7:55
pour les promesses si jamais vous avez
7:58
quelque chose qui est à synchrone on
8:00
peut s'imaginer que cette fonction elle
8:01
fait quelque chose et au bout d'un
8:03
moment elle renvoie ce type de données
8:04
là vous pouvez utiliser comme on l'a
8:06
fait pour les tableaux promise vous
8:09
utilisez le les petits les petits signes
8:11
supérieur et inférieur et entre vous
8:13
allez mettre le type de retour donc si
8:15
c'est une promesse qui est résolue avec
8:16
une chaîne de caractère on fera ça nous
8:19
dans notre cas on lui dira c'est une
8:21
promesse qui est résolue par une liste
8:22
d'articles ça peut devenir assez
8:24
complexe à ce niveau-là si maintenant
8:26
j'utilise mon fech pour poste je peux
8:29
faire un veine lui dire je vais
8:31
récupérer les articles hop et là lui
8:34
dire j'aimerais bien récupérer le
8:36
premier article
8:38
si je passe sur mon poste on voit bien
8:40
qu'il comprend que c'est un objet parce
8:42
qu'il a été capable de comprendre ce que
8:44
vous avez précisé ici donc la JSK va
8:46
être très très puissante pour nous
8:48
offrir un petit peu plus
8:49
d'auto-complétion et nous permettre de
8:51
mieux comprendre les retours mais aussi
8:52
les paramètres de notre fonction
8:55
si jamais vous avez besoin de répéter
8:56
quelque chose par exemple on peut
8:58
s'imaginer que l'objet qui représente un
8:59
article on en a besoin dans plusieurs
9:01
méthodes c'est vrai que ça peut être
9:02
pénible de toujours répéter ça on a la
9:04
possibilité de définir un type donc dans
9:07
ce cas là on va écrire un commentaire en
9:08
amont comme ceci on va mettre
9:11
@ type def
9:13
on va préciser que ça va être un objet
9:15
et on va lui dire c'est un objet qui
9:17
s'appelle post maintenant lorsque
9:20
j'utilise ma promesse et je lui dis j'ai
9:22
un tableau d'article je peux utiliser
9:23
post alors le problème c'est que lorsque
9:26
je vais regarder ma variable poste il va
9:28
me dire ouais mais je sais pas vraiment
9:29
qu'est-ce que qu'est-ce que l'on a à
9:31
l'intérieur donc dans mon type def je
9:33
peux en profiter pour préciser les
9:34
propriétés de mon objet on a une autre
9:37
tag que l'on peut utiliser c'est le tag
9:40
arobase property donc on va préciser
9:42
qu'on aura une propriété qui sera un
9:44
nombre qui s'appellera ID on aurait une
9:47
autre propriété qui sera une chaîne de
9:48
caractère qui sera le teele et une autre
9:52
chaîne de caractères qui sera le body on
9:54
peut aussi en profiter pour ajouter des
9:56
informations par exemple ici on mettra
9:58
titre de l'article
10:01
si je sauvegarde et que je regarde à ce
10:03
niveau là avec quoi ressemble le poste
10:04
on voit bien que c'est quelque chose de
10:06
type post et si je regarde post.itle
10:10
j'ai l'autocomplétion à ce niveau là
10:12
donc il me dit bien que ça existe et que
10:15
c'est une propriété de type chaîne de
10:16
caractère et dans le cadre de VS scotch
10:19
je peux même cliquer ici et ça me donne
10:20
la description qui était mise à ce
10:22
niveau là donc c'est plutôt puissant
10:24
vous le voyez pour pouvoir réutiliser
10:26
des choses
10:28
donc en plus des objets vous avez aussi
10:29
la possibilité de tiper les fonctions on
10:33
peut s'imaginer que cette fonction là
10:34
elle a renvoie une fonction qui
10:36
attendrait une chaîne de caractères et
10:38
un nombre donc dans ce cas là au type au
10:40
niveau du type de retour vous allez
10:42
mettre entre parenthèses vous allez
10:44
mettre une première parenthèse pour les
10:45
paramètres une flèche et le type de
10:48
retour donc par exemple on peut le dire
10:50
ça va être une fonction qui une fois
10:52
qu'elle sera appelée sera un nombre si
10:54
je fais fetch poste j'appelle cette
10:57
fonction là qui renvoie donc une
10:59
fonction lorsque je mets une parenthèse
11:01
on voit qu'il m'indique que c'est une
11:02
fonction qui va renvoyer un nombre si on
11:05
avait des paramètres on pourrait les
11:06
mettre en mettant le nom du paramètre
11:07
par exemple STR et le type associé âge
11:11
de point number par exemple et on
11:14
pourrait même dire ça renvoie des
11:15
articles bon je vais volontairement sur
11:17
des choses un peu compliquées mais là
11:19
lorsque je fais une petite parenthèse on
11:21
voit qu'il m'indique les paramètres donc
11:22
je peux dire bah tiens je vais mettre FR
11:25
et 18 et là ça va me renvoyer un article
11:28
donc lorsque je fais un point il
11:30
comprend que j'ai body title et Heidi
11:32
donc ce système de type est plutôt
11:34
puissant pour définir des choses assez
11:36
poussées et vous pouvez aussi utiliser
11:38
un type def pour lui dire bon ben ça
11:40
c'est quelque chose que je vais avoir
11:41
besoin de réutiliser hop et voilà là
11:43
j'ai défini un petit personnalisé qui
11:45
sera un petit peu plus pratique à
11:46
utiliser donc c'est possible de pas mal
11:48
aller loin à ce niveau-là
11:50
donc ensuite on a la possibilité de
11:52
faire la même chose au niveau des
11:53
classes alors si un jeu crée une classe
11:55
A je vais pouvoir ici dans les
11:57
commentaires préciser le type des
11:59
différentes propriétés qu'il y a à
12:00
l'intérieur en faisant arobase property
12:02
je peux mettre entre Cola de le type et
12:05
donner un nom à notre propriété donc
12:06
typiquement on aurait une propriété par
12:08
exemple first name et dans ce cas là
12:10
lorsqu'on initialise les choses il
12:11
devine qu'il y a cette propriété là
12:13
l'inconvénient c'est que pour avoir
12:15
testé ça sur Visual Studio code en tout
12:18
cas le taux compression a pas l'air très
12:20
présente si je fais un B point vous
12:22
voyez qui ne me propose pas first name
12:23
par contre l'éditeur est quand même
12:25
assez poussé et capable de faire ces
12:27
autocompessions un petit peu par
12:28
lui-même c'est-à-dire que si dans le
12:30
constructeur hop je fais un vis point
12:34
first name et que je mets ici un tableau
12:37
vide lorsque je vais faire B point
12:39
quelque chose on voit qu'il comprend que
12:41
ça c'est une propriété et que c'est un
12:43
tableau si vous avez besoin d'être plus
12:45
précis sur le type de d'une variable
12:47
alors ça marche pour une propriété ou
12:49
pour n'importe quoi vous pouvez décrire
12:51
un petit commentaire au-dessus donc vous
12:52
allez écrire slash étoile donc on va à
12:54
la ligne on peut préciser le but de ce
12:57
truc là donc on va mettre ici prénom de
12:59
l'utilisateur
13:01
vous pouvez rajouter un arobase type et
13:04
vous allez mettre le type associé donc
13:05
par exemple ça serait ici un tableau de
13:07
chaîne de caractère c'est très bizarre
13:09
pour un first name mais c'est pour
13:10
l'exemple maintenant lorsque je fais B
13:13
point quelque chose on voit qui comprend
13:15
bien que c'est un tableau de caractère
13:16
plutôt que d'être un tableau de
13:17
n'importe quoi donc ça peut servir dans
13:19
certaines situations de pouvoir typer
13:21
une variable comme ça sortie un petit
13:24
peu de n'importe où si par exemple je
13:25
crée une variable B et Judici c'est un
13:28
tableau vide si je regarde B il me dit
13:30
que c'est un tableau n'importe quoi mais
13:31
si au dessus je mets un petit peu de
13:33
commentaire et je précise que c'est un
13:35
type et on va lui dire que c'est une
13:37
Paray un tableau de chaîne de caractère
13:39
automatiquement il comprend mieux à ce
13:42
niveau là donc faudra pas hésiter des
13:44
fois si vous voulez un traître un petit
13:45
peu plus précis et avoir une meilleure
13:47
compréhension du Code A comme ça typé
13:49
certaines propriétés ou certaines
13:51
valeurs donc il y a beaucoup beaucoup de
13:52
choses que l'on peut faire avec la JS
13:54
doc après le problème c'est que la
13:55
compréhension varie pas mal suivant les
13:57
éditeurs il y a pas mal de choses que
13:59
les éditeurs sont aussi capables de
14:00
comprendre d'eux et que vous n'avez pas
14:01
forcément besoin de préciser mais c'est
14:04
intéressant de savoir qu'on peut faire
14:05
un petit peu tout ça donc n'hésitez pas
14:07
à faire un petit tour sur sur cette
14:10
documentation là vous avez tous les mots
14:12
clés qui sont listés ici pour vous
14:15
donner quelques mots clés intéressants
14:16
vous avez par exemple Frau aussi qui
14:18
vous permet de dire par exemple que tel
14:20
ou telle fonction peut renvoyer une
14:21
erreur vous avez private aussi qui vous
14:23
permet de dire que un symbole n'a pas
14:25
vocation à être utilisé en dehors et
14:26
dans ce cas là vous pourrez pas le voir
14:28
dans l'autocomplétion il y a pas mal de
14:30
choses qui peuvent être intéressantes
14:31
après vous avez aussi même des outils
14:33
qui sont capables de scanner votre code
14:35
à partir de la JS doc pour détecter les
14:37
erreurs mais là c'est un petit peu plus
14:38
poussé moi ce que je vous conseille
14:40
vivement de faire à votre niveau c'est
14:42
de commencer à commenter avec de la JS
14:44
doc toutes vos fonctions et vos méthodes
14:46
dans vos classes c'est important de
14:48
savoir ce que l'on peut envoyer une
14:49
fonction pour éviter les erreurs même si
14:52
parfois c'est évident on peut deviner
14:53
que quand on envoie un nage bah on
14:55
attend forcément entier c'est quand même
14:56
important de le préciser pour après
14:58
avoir un petit peu plus de structure
15:00
donc voilà pour ce principe là ce qu'il
15:02
faut retenir c'est que les commentaires
15:03
doivent expliquer le rôle de vos
15:05
fonctions ou de vos classes ou de vos
15:07
propriétés il ne faut pas avoir des
15:09
commentaires qui réexpliquent le code le
15:11
code en lui-même ce documente par nature
15:13
en fonction de les noms que vous avez
15:15
donné à vos variables et à vos fonctions
15:16
et ensuite on pourra utiliser la JSD
15:19
pour avoir un petit peu plus de
15:20
précision sur les types qui sont
15:21
attendus au niveau de nos paramètres de
15:24
fonction ou nos types de retour donc ça
15:26
ça permettra d'avoir un code qui sera un
15:28
petit peu plus facilement vérifiable par
15:29
la suite donc j'espère que ça vous aura
15:31
aidé et je vous donne rendez-vous dans
15:33
le prochain chapitre
