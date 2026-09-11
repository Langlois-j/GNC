# Apprendre le JavaScript : Commentaires et JSDoc

Video : https://www.youtube.com/watch?v=AD28PddTwEE

## Transcription

salut et bienvenue dans cette nouvelle
0:01
vidéo aujourd'hui je vous propose de
0:02
parler des dates en Javascript alors
0:04
malheureusement le javascript n'est pas
0:06
forcément un très bon langage pour
0:07
parler des dates parce qu'il n'a qu'un
0:08
seul objet qui permet de les représenter
0:10
et c'est un objet qui vous allez le voir
0:12
est plutôt pauvre en termes de
0:13
fonctionnalités pour l'avantage il faut
0:15
voir le bon côté des choses c'est que
0:17
vous allez avoir peu de méthode à
0:18
apprendre et ça ça peut être plutôt cool
0:19
il faut savoir aussi que actuellement il
0:22
y a une autre API qui représente en
0:23
train de se développer qui s'appelle
0:24
temporal mais à l'heure actuelle elle
0:26
est trop expérimentale pour que je vous
0:27
la présente elle n'est pas supportée par
0:28
la plupart des navigateurs donc on va
0:30
l'oublier et date ça ça fonctionne
0:32
partout donc il y a aucun problème donc
0:35
l'objet Date va nous permettre de
0:36
représenter une date et en interne ces
0:38
représenté sous forme d'un nombre qui
0:40
s'appelle un Times stamp c'est le nombre
0:42
de secondes ou dans le cadre de
0:44
JavaScript le nombre de mini secondes
0:45
écoulée depuis le 1er janvier 1970 c'est
0:49
une donnée un petit peu arbitraire mais
0:50
qui est utilisée dans le langage pour
0:52
représenter des dates
0:54
alors pour construire cet objet Date
0:55
vous avez un constructeur qui est plutôt
0:57
simple donc ce constructeur il peut
0:59
prendre plusieurs types de paramètres si
1:01
vous ne lui passez rien par défaut il va
1:03
automatiquement construire une date à
1:05
l'heure actuelle donc au moment où le
1:07
votre code est exécuté vous pouvez lui
1:09
passer une valeur qui sera un nombre qui
1:11
représentera un time stamp unique en
1:13
millisecondes donc vous allez lui donner
1:15
le nombre de mini secondes écoulé depuis
1:17
le 1er janvier 1970 il vous créera la
1:19
date vous pouvez aussi lui passer une
1:21
chaîne de caractères qu'il va
1:22
automatiquement convertir sous forme de
1:24
date donc cette chaîne de caractères
1:26
devra correspondre à un standard qui
1:28
s'appelle le standard ISO 8601 c'est un
1:31
format qui ressemble un petit peu à ça
1:33
mais on en reparlera un petit peu plus
1:35
tard et enfin une dernière option qui
1:37
est un petit peu plus facile pour nous
1:38
les humains c'est en lui passant l'année
1:40
le mois le jour le nombre d'heures
1:42
minutes et secondes et voire même
1:44
millisecondes pour vous montrer un petit
1:46
peu à quoi ressemble cet objet on va ici
1:47
va créer une nouvelle date et si
1:50
j'appuie sur entrée elle nous est
1:52
représenté sous forme de chaînes de
1:53
caractères dans le navigateur mais on a
1:55
vraiment un objet et on voit que par
1:57
défaut cet objet là a pris leur à
1:58
laquelle je suis donc ensuite on a la
2:01
possibilité de le construire avec un
2:02
timestre donc si je mets 10 secondes
2:04
enfin 10 millisecondes ça va me donner
2:06
10 mines secondes à partir du 1er
2:07
janvier 1970 et ensuite on peut le
2:10
construire plus simplement en lui
2:12
passant ben des années des minutes et
2:14
tout ça le petit problème c'est que
2:17
étrangement le nombre de mois mais ça
2:19
n'est pas un nombre qui commencerait à 1
2:21
c'est pas un pour janvier 2 pour février
2:23
non c'est un index donc janvier
2:25
commencera à zéro donc si vous voulez le
2:27
premier janvier
2:29
2022 mais il faudra mettre 2022 0 et 1
2:33
et dans ce cas là on voit que ça nous
2:34
crée cette date là c'est un peu bizarre
2:36
mais bon je sais pas pourquoi ils ont
2:38
fait ça autre petit détail vous pouvez
2:39
avoir des mois qui ne sont pas dans la
2:41
valeur connue normalement d'une date par
2:43
exemple si je veux je veux dire je veux
2:45
le 14ème mois automatiquement il va
2:47
mettre mars de la même manière si je dis
2:50
je suis en janvier et que je lui dis je
2:52
veux être le 32 janvier ça ne lui pose
2:55
aucun problème dans le sens il va se
2:56
dire ben en fait je vais prendre 32
2:58
jours à partir du 1er janvier et ça nous
3:00
donnera le premier février donc vous
3:01
pouvez avoir des nombres un petit peu
3:02
bizarres et il l'acceptera très bien
3:04
JavaScript on va voir que ça c'est
3:06
quelque chose qui est d'ailleurs plutôt
3:07
pratique
3:08
autre point on voit que après nos dates
3:10
il nous parle de GMT donc ça c'est le
3:13
fuseau horaire par défaut il va utiliser
3:14
le fuseau horaire de notre système et vu
3:17
que moi je suis sur le fuseau horaire
3:18
français qui en plus le décalage horaire
3:20
suivant à quelle date on prend on est
3:21
décalé de deux heures ou de 1h petit
3:24
détail le fuseau horaire de base c'est
3:26
le temps que l'on appelle UTC
3:28
UTC c'est pour Universal time coordinate
3:31
et actuellement par exemple on est
3:33
décalé de deux heures par rapport à ce
3:34
tendre donc lorsque les dates nous sont
3:36
affichées elles nous sont affichées dans
3:38
notre fuseau horaire actuel et on nous
3:40
montre avec cette information là le
3:41
décalage mais en interne lorsque l'on
3:44
parle de timestamp le nombre secondes
3:45
écoulé c'est le nombre de milliers
3:47
secondaires par rapport au temps
3:49
UTC donc par rapport au 1er janvier 1970
3:51
en temps UTC si vous voulez connaître le
3:54
décalage que vous avez avec votre date
3:56
et le temps UTC vous pouvez prendre
3:59
votre date et utiliser une méthode qui
4:01
s'appelle get time zone offset et ça
4:03
vous donne love set en minute donc là on
4:06
nous dit que on a un décalage de 60
4:08
minutes entre notre date que l'on a
4:10
rentré et le temps UTC donc dans le
4:12
cadre du navigateur ça utilise l'horloge
4:14
de l'ordinateur mais si vous êtes sur un
4:16
serveur ça sera l'horloge du serveur qui
4:18
sera utilisé
4:19
donc ensuite pour parler des méthodes
4:21
plus généralement vous allez avoir tout
4:22
un tas de méthodes qui vont avoir un
4:24
trait à la récupération des informations
4:25
donc get hours pour récupérer les heures
4:28
get dates pour récupérer une date et
4:29
ainsi de suite ainsi de suite on
4:31
mentionnera juste que get day vous
4:33
renvoie le numéro du jour de la semaine
4:35
mais il faut faire attention c'est basé
4:37
sur le système anglais donc ça commence
4:38
en dimanche donc zéro représentera
4:40
dimanche 1 pour lundi et ainsi de suite
4:42
vous avez les mêmes méthodes mais pour
4:45
le temps UTC donc ça vous donne ici le
4:47
jour en UTC l'heure en UTC ainsi de
4:49
suite ainsi de suite vous avez ensuite
4:52
les mêmes méthodes sous forme de setter
4:53
pour pouvoir 7
4:55
un nombre de secondes au nombre de mois
4:58
et enfin vous avez des méthodes qui ont
5:00
entrées au formatage d'une date donc ces
5:03
méthodes là elles vont être plutôt
5:04
pratique pour communiquer avec des
5:05
systèmes donc si vous avez besoin
5:07
d'envoyer par exemple une date à un
5:09
serveur typiquement très souvent ça va
5:11
être le formatage ISO qui est un
5:13
standard particulier qui va être utilisé
5:15
donc si je demande la date du jour sous
5:17
forme de ISO string et ça va me donner
5:20
quelque chose qui ressemble à ça donc
5:22
c'est quelque chose on a l'année le mois
5:24
le jour et ensuite T pour indiquer qu'on
5:27
va avoir une notion de temps et ensuite
5:29
on aura les heures minutes et secondes
5:30
et puis le fuseau horaire donc là c'est
5:32
16 heures en temps UTC
5:35
de la même manière on va avoir une autre
5:37
méthode qui est tout utc-string qui nous
5:40
renvoie un format qui ressemble un petit
5:41
peu plus à ça je crois que c'est un
5:43
format qui est plutôt utilisé dans les
5:44
cookies par exemple ou dans d'autres
5:46
systèmes qui ont besoin de ce format là
5:48
je crois aussi dans les flux RSS pour
5:50
mais c'est très spécifique pour le coup
5:52
voilà donc ça ça peut être pratique et
5:54
après vous avez aussi
5:56
un format qui est super intéressant
5:58
c'est le tout local date string dans ce
6:02
cas là ça va vous formater une seule
6:04
main la partie date avec la locale de
6:06
l'utilisateur donc dans ce cas là ça me
6:08
le format en français mais vous avez la
6:10
possibilité de lui passer un premier
6:11
paramètre une locale différente et dans
6:13
ce cas là ça va formater avec la locale
6:15
que vous avez demandé donc typiquement
6:16
ici ça me formate ça pour un Américain
6:19
donc qui lui met d'abord les mois puis
6:21
ensuite les jours
6:22
vous avez aussi notre méthode il me
6:24
semble que c'est tout local string
6:28
directement et dans ce cas là ça vous
6:30
donne la le formatage avec à la fois la
6:33
date et à la fois le temps et enfin vous
6:35
avez aussi tout local times string et là
6:38
ça vous formate que la partie temps donc
6:40
à savoir les heures minutes et secondes
6:41
au niveau de votre de votre information
6:44
et il faut savoir que ces trois méthodes
6:46
en fait sont des raccourcis vers un
6:48
autre objet qui est beaucoup plus poussé
6:49
et vous y avez accès dans la
6:51
documentation voilà c'est l'objet int
6:54
qui est un objet qui permet de gérer
6:55
tout ce qui est localisation de
6:57
certaines informations ça peut être
6:59
utilisé pour les nombres mais ça peut
7:00
aussi être utilisé pour les dates comme
7:03
on vient de le voir donc si on clique
7:04
dessus voilà on nous explique comment ça
7:06
fonctionne normalement le construit avec
7:09
la locale et ensuite on peut lui passer
7:11
un second paramètre qui serait des
7:12
options et ces options je crois qu'elles
7:15
sont expliquées dans le constructeur
7:17
voilà on a toutes ces options là donc
7:19
par exemple je peux lui dire j'aimerais
7:21
bien que tu me formates ça sous forme de
7:23
string mais je voudrais avoir un dates
7:26
style donc le style des dates long et
7:29
dans ce cas là ça va me mettre quelque
7:31
chose tout en chaîne de caractère et on
7:33
va lui préciser qu'on met indie find
7:35
comme premier paramètre pour qu'il
7:37
prenne automatiquement la locale de
7:38
l'ordinateur donc là il me donne juste
7:40
le 7 octobre 2022 et si je lui dis pour
7:43
le Time style je veux que tu me donnes
7:46
longue aussi ça va me donner les
7:48
informations comme ça si je veux que il
7:51
raccourcisse le mois et qui ne mette que
7:53
sur quelques lettres mais je peux faire
7:55
ça donc cette méthode là peut vous
7:57
permettre de formater les dates pour les
7:59
renvoyer à l'utilisateur dans un format
8:00
qui est plus facile à comprendre donc
8:03
c'est relativement simple à utiliser il
8:04
y a juste un gros objet d'option avec
8:06
plein d'informations
8:07
et si vous êtes intéressé pour localiser
8:10
certaines informations je ne ferai pas
8:12
forcément de vidéos en plus dessus mais
8:14
vous avez grâce à cet objet Intel
8:16
d'autres formateurs par exemple vous
8:18
avez la un système qui permet de
8:20
formater les nombres pour pouvoir mettre
8:22
par exemple dans un certain nombre de
8:23
d'éléments après la virgule pour pouvoir
8:25
mettre une unité de monnaie vous pouvez
8:27
lui dire que dans certaines langues on
8:29
sait qu'on a inspirateur pour les
8:30
décimales qui sera des points mais dans
8:31
d'autres cdvirgule donc tout ce toutes
8:33
ces fonctions là elles sont super
8:34
intéressantes mais c'est relativement
8:36
poussé vu que c'est du formatage et de
8:37
l'internationalisation donc pour
8:39
l'instant sachez que c'est là si jamais
8:41
vous avez besoin mais on va revenir sur
8:43
notre système de date et globalement
8:46
c'est tout ce qui à savoir sur les dates
8:48
ce qui vous reste juste à explorer c'est
8:50
quelques fonctions vous avez des
8:51
fonctions qui permettent de créer des
8:52
dates directement donc on a vu date
8:54
point d'eau qui permet de générer un
8:56
timistan ça vous génère un nombre de
8:58
millisecondes et vous avez date point
9:00
par ce qui permet aussi de passer une
9:02
date sous un certain format et de vous
9:04
renvoyer le timing sans punix et après
9:06
vous avez date point UTC qui un petit
9:08
peu comme le constructeur de date c'est
9:09
à dire qu'il attend différents
9:10
paramètres sauf qu'il vous renvoie un
9:12
timistamp UTC et ensuite vous pouvez
9:14
l'utiliser dans le constructeur de date
9:15
si vous voulez construire des dates tu
9:17
sais directement voilà en dehors de ça
9:19
c'est tout ce qu'il y a à connaître sur
9:21
les dates ce que je vous propose
9:22
maintenant c'est quelque petits
9:23
exercices pour pratiquer de voir comment
9:25
vous pouvez utiliser cet objet là pour
9:27
avancer dans le temps ou reculer donc
9:30
d'abord je vous demande de créer un
9:32
objet Date donc nous on va l'appeler
9:33
today et on va lui dire que c'est la
9:36
date du jour
9:38
ensuite on va s'imaginer qu'on se crée
9:40
une méthode on va créer une fonction que
9:42
l'on va appeler ad days et l'objectif de
9:45
cette fonction c'est de prendre un
9:46
paramètre une date et ensuite de prendre
9:49
en seconde paramètre le nombre de jours
9:50
que l'on souhaite rajouter votre
9:52
objectif c'est de pouvoir ensuite créer
9:54
une constante que l'on appellerait tout
9:56
moraux et on lui dirait j'aimerais bien
9:58
que tu rajoutes à notre date du jour
10:01
today un jour et après en fin de console
10:04
point log et en log today et en loge
10:07
aussi tomorro donc notre objectif c'est
10:09
d'avoir quelque chose qui s'affiche en
10:11
console qui est correct si pour
10:13
l'instant je regarde ma console ça nous
10:15
donnera bien la date du jour mais
10:16
tomorro est un défunt donc je vous
10:17
laisse essayer de le pratiquer et encore
10:19
ici ensemble juste après
10:22
alors il y a plusieurs solutions mais la
10:24
première solution qui semble la plus
10:26
simple c'est de partir de la date que
10:27
l'on reçoit en paramètre et d'utiliser
10:29
la méthode 7 date pour lui rajouter la
10:31
date du jour plus donc là on pourrait
10:33
faire un date point 7 date et on doit
10:37
lui donner le numéro de la date dans le
10:39
mois on peut la récupérer en faisant un
10:41
date point get date et on rajoutera le
10:44
nombre de jours qui a été demandé
10:45
ensuite à la fin de cette fonction je
10:47
retourne à la nouvelle date si je
10:50
sauvegarde maintenant je vois que
10:51
j'obtiens le 8 octobre donc j'ai bien
10:53
une fonction qui est capable de rajouter
10:55
un jour
10:56
le problème de cette fonction là c'est
10:58
qu'elle fait ce que l'on appelle une
10:59
mutation c'est à dire que un des
11:01
paramètres qu'elle reçoit en paramètre
11:03
justement et modifier donc ça ce sont
11:06
des fonctions qui ont un inconvénient
11:07
c'est qu'en général elles peuvent être
11:08
imprévisibles et créer des effets de
11:10
bord c'est exactement le cas que l'on
11:11
voit ici on pourrait s'attendre
11:13
lorsqu'on fait un console point loc de
11:14
today que la date originale n'est pas
11:16
bougé pourtant on voit dans le console
11:18
que même tout d a été modifié parce
11:20
qu'on a utilisé cette date qui effectue
11:22
une mutation sur notre objet Date et on
11:25
se retrouve avec un effet qui est un
11:26
petit peu bizarre on s'attendrait en
11:28
console à ce que tout des restes le 7
11:29
octobre et que la date de lendemain soit
11:33
bien le 8 octobre donc moi ce que je
11:35
vous conseille de faire quand vous créez
11:36
des fonctions qui vont entrer aux dates
11:37
c'est de créer des fonctions qui sont
11:38
pures c'est à dire ce sont des fonctions
11:40
qui n'ont pas d'effet de bord qui ne
11:42
modifient pas ce qu'elles reçoivent en
11:43
paramètre donc ce qu'on pourrait faire
11:45
c'est créer une nouvelle date à partir
11:47
de la date que l'on reçoit en paramètre
11:49
pour cela on va créer une constante
11:51
quand on va appeler new date et on va
11:53
lui demander de construire un nouvel
11:54
objet et on va récupérer le Times stamp
11:57
de notre date originale donc ça ça va
12:00
permettre de créer une nouvelle date
12:01
ensuite si cette nouvelle date sur
12:04
laquelle je modifie le nombre de jours
12:07
et c'est enfin cette nouvelle date que
12:08
je vais renvoyer si je sauvegarde
12:10
maintenant l'avantage c'est que tout day
12:12
n'a pas été modifié par ma fonction on a
12:15
bien le 7 octobre et par contre on a
12:17
bien tout moraux qui est la date du
12:19
lendemain donc on voit que c'est
12:20
exactement à la même heure d'ailleurs et
12:22
ça fonctionne correctement donc cette
12:24
approche là est bien meilleure
12:26
on essaiera lorsqu'on créera des
12:28
fonctions avec les dates de ne pas
12:30
modifier l'objet original ça peut ça
12:33
peut créer des problèmes alors
12:34
maintenant je vous propose un exemple un
12:36
petit peu plus compliqué on va
12:38
s'imaginer que je vous demande de créer
12:39
une fonction qu'on en appelle add
12:41
intervalle on va lui passer un premier
12:43
paramètre une date un second paramètre
12:45
un nombre qu'on va appeler N et en
12:47
troisième paramètre une unité
12:49
et l'idée c'est de faire un petit peu la
12:51
même chose sauf que là plutôt que
12:53
d'utiliser add days je pourrais lui dire
12:55
j'aimerais bien ajouter à la date du
12:57
jour
12:58
3 et on lui précisera des mois alors
13:03
histoire d'éviter d'avoir comme ça des
13:04
chaînes de caractères qui se traînent un
13:06
petit peu partout on pourra se créer des
13:08
constantes on pourrait se créer une
13:09
constante qu'on va appeler Moon qui
13:12
permettrait de représenter des moins on
13:14
peut mettre n'importe quoi en terme de
13:15
valeur tant que c'est unique ensuite on
13:17
aurait days pour représenter des jours
13:19
et on aurait la même chose pour yos on
13:22
pourrait continuer pour pouvoir
13:23
permettre de rajouter des heures des
13:25
minutes et des secondes si on le
13:26
souhaite donc là plutôt que d'utiliser
13:28
notre chaîne de caractères on peut
13:30
utiliser une constante
13:31
voilà donc j'aimerais bien rajouter
13:33
trois mois un autre date et on
13:35
l'appellerait futur plutôt que de
13:37
l'appeler today donc votre objectif
13:39
c'est maintenant de faire en sorte que
13:40
cette fonction fonctionne
13:44
alors on a plusieurs solutions la
13:46
première solution c'est de repartir un
13:48
petit peu de notre exemple de base ici
13:50
et ensuite d'utiliser un petit switch
13:52
case en lui disant switch on va se baser
13:55
sur l'unité qui a été demandée et lui
13:58
dire si on est sur une unité qui est de
14:00
type days parce que l'on fera c'est
14:02
qu'on lui demandera de faire
14:04
un new date point 7 date et on rajoute
14:09
un nœud date point get date
14:14
auquel on rajoute le nombre de
14:16
d'éléments que l'on a choisi et après
14:19
ben on fera un break pour lui dire de
14:20
s'arrêter donc on fera la même chose si
14:22
jamais on est sur le nombre de mois ça
14:25
serait une Mons on lui demanderait de
14:28
faire un set date on récupère ré le
14:30
moins actuel et en rajouterait n si on
14:33
est sur un nombre d'années donc ça
14:35
serait ailleurs on lui demanderait de
14:37
récupérer le nombre de fullures
14:41
et on ferait un set foulure et là
14:44
attention on ferait la même chose aussi
14:45
cette mode
14:47
et après on n'aurait pas de cas par
14:49
défaut ou peut-être on pourrait dire
14:50
qu'on ne fait rien et à la fin je peux
14:52
retourner ma nouvelle date qui aurait
14:54
été modifiée si je regarde je vois bien
14:57
que ça me donne le 7 janvier si je me
14:59
dis je veux rajouter deux années donc je
15:02
rajouterai la constanteyers ça me donne
15:04
à 2024 donc on voit que ça fonctionne
15:06
bien donc une autre solution qui
15:09
permettrait d'éviter ce switch case et
15:10
qui serait peut-être un petit peu plus
15:11
dynamique serait de se dire en fait je
15:13
vais créer un tableau qui va représenter
15:14
les différentes parties de ma date donc
15:16
ici je vais créer un tableau que je vais
15:19
appeler parts parce que ça a des parties
15:20
d'une date et je vais lui donner les
15:22
valeurs dans l'ordre dans lesquelles on
15:24
doit les utiliser pour la construction
15:25
donc je vais dire par exemple là je
15:27
récupère fullieur ensuite je récupère le
15:32
nombre de mois ensuite je récupère
15:35
le la date donc elle date ensuite on
15:39
aura les heures
15:40
et vous avez compris le principe on fait
15:43
ça avec les différentes les différentes
15:44
choses donc ensuite on a besoin alors
15:47
ces get or get minute
15:51
get second
15:54
et je crois qu'ensuite on a besoin du
15:56
nombre de millisecondes donc on va
15:57
regarder si c'est disponible et on
15:59
remarque que minutes effectivement yes
16:01
get Horse aussi et on a get
16:03
millisecondes
16:07
je veux pas faire de fautes
16:08
d'orthographe donc je préfère l'avoir
16:10
comme ça donc là j'ai un tableau qui
16:13
permet de représenter ma date avec les
16:14
différents éléments l'avantage c'est
16:16
qu'ensuite je peux modifier mes
16:18
constantes ici et lui dire qu'en fait
16:19
dans years on aura 0 parce que c'est
16:22
l'élément l'index zéro dans Mons ça sera
16:25
l'élément à l'index 1 days ça sera
16:28
l'élément l'index 2 et de cette manière
16:30
là l'unité que je vais recevoir ça sera
16:32
un nombre plutôt que d'être une chaîne
16:33
de caractères donc je pourrais lui dire
16:35
une fois que tu as morcelé ce tableau là
16:37
je veux que tu prennes l'appart qui
16:39
correspond à l'unité et je veux que tu
16:42
l'incrémentes de N et une fois que j'ai
16:45
fini tu peux créer une nouvelle date et
16:47
je te passerai tous les éléments de ce
16:49
tableau
16:50
si je sauvegarde maintenant et que je
16:52
réactualise ma page on voit que ça me
16:54
donne le 7 octobre 2024 et si je lui
16:56
demande de rajouter un mois ça va
16:59
rajouter un mois donc on sera en
17:00
novembre donc c'est une autre manière de
17:03
faire les choses qui est un petit peu
17:04
plus dynamique et qui demande un peu
17:05
moins de code
17:07
en fin on va continuer notre
17:09
amélioration j'aimerais bien plutôt que
17:11
de faire ça lui dire en fait je vais te
17:13
passer un objet et je vais te dire je
17:16
vais rajouter un mois ou même aller on
17:18
va rajouter deux mois on va être un
17:19
petit peu fou donc on va lui dire c'est
17:20
un objet qui prend en clé la valeur de
17:23
la constante Mols et on va lui dire je
17:25
veux rajouter deux mois mais je veux
17:27
rajouter aussi un jour donc on mettra
17:28
days et en rajoutera un jour et
17:31
l'avantage de cet objet là c'est que ça
17:33
nous permet de rajouter un intervalle
17:34
qui contient à la fois des mois des
17:36
jours ou des années et ça c'est plutôt
17:38
intéressant
17:40
donc je vous laisse peut-être essayer de
17:41
le faire si vous êtes motivé mais sinon
17:42
je vous donne la correction tout de
17:44
suite
17:46
donc il va falloir changer le format de
17:47
notre fonction ici on va lui dire tu
17:49
recevras un paramètre en intervalle qui
17:51
sera en réalité un objet qui contiendra
17:53
en clé quelque chose qui sera un deux ou
17:56
zéro donc l'index du tableau que je dois
17:58
modifier et en valeur la valeur de
18:00
décalage que je dois appliquer donc il
18:03
nous suffit simplement de modifier cette
18:04
partie là en lui disant maintenant je
18:06
veux faire un fort const je vais
18:09
récupérer le l'unité et je vais
18:12
récupérer la valeur qui est la valeur de
18:14
décalage et je lui dis que je dois faire
18:15
un fort objectif entrees et j'utilise
18:19
les entrées que j'ai dans intervalle
18:21
voilà donc ça c'est toujours pour
18:23
récupérer les clés et les valeurs dans
18:24
un objet maintenant que j'ai ça je peux
18:27
lui demander à ce niveau là de prendre
18:28
notre clé qui correspond à l'unité donc
18:30
0 1 ou 2 et de modifier un incrémentant
18:33
de la valeur
18:34
et à la fin je reconstruis ma date à
18:37
partir de ça si je sauvegarde j'ai ici
18:39
quelque chose qui a été incrémenté d'un
18:41
jour et incrémenté de deux mois et vous
18:44
avez comme ça une petite fonction qui
18:45
vous permet facilement de créer une
18:47
nouvelle date en rajoutant un intervalle
18:49
particulier
18:50
donc je sais c'est peut-être pas
18:52
forcément évident en terme de logique
18:53
mais je voulais essayer de vous montrer
18:55
progressivement comment on peut arriver
18:57
à des fonctions qui peuvent être
18:58
intéressantes pour faire des problèmes
18:59
du quotidien que l'on a en Javascript
19:01
donc on pourrait lui dire on peut
19:03
rajouter les pareils la même chose pour
19:05
modifier les heures dans ce cas là on
19:07
aura une constante House qui permettrait
19:09
de dire ça serait le troisième index
19:11
ensuite on aurait une minute
19:13
minutes ce serait aussi une constante et
19:16
on va aller on va l'appeler minute comme
19:18
ça et ensuite seconde pour les secondes
19:21
en général les millisecondes je vous
19:23
avouerai qu'on a pas trop à y toucher et
19:25
vous pouvez comme ça modifier votre code
19:27
et les dire hop allez on va modifier de
19:29
3 minutes notre date et automatiquement
19:32
pouf elle est décalée de 3 minutes je
19:35
vous conseille de garder cette fonction
19:36
dans un coin de votre code ou peut-être
19:38
de le mettre dans un fichier JavaScript
19:39
séparé elle vous servira assez longtemps
19:41
dans ce cas là vous avez à exporter ces
19:43
différentes constantes et exporter votre
19:44
fonction à d'intervalle mais comme je
19:47
vous l'ai dit peut-être plus tard je ne
19:48
sais pas si ça va sortir et dans quelle
19:50
format ça va sortir on aura un nouvel
19:52
objet temporal qui va nous permettre
19:54
peut-être de gérer les intervalles et de
19:57
pouvoir automatiquement rajouter des
19:58
choses au niveau des dates mais à
20:01
l'heure actuelle quand on veut manipuler
20:02
des dates on est obligé de faire de
20:03
cette manière là un autre problème
20:05
typique que vous pouvez rencontrer c'est
20:07
d'essayer d'afficher une chaîne de
20:09
caractères qui dit quand est-ce que
20:10
quelque chose va sortir dans ce cas là
20:12
vous pouvez prendre par exemple si on
20:14
prend la date dans le futur ici que l'on
20:16
a si on veut afficher dans trois jours
20:19
ou ce genre de choses mais il faudrait
20:20
prendre la date du futur récupérer son
20:23
time donc ça ça nous donne l'homme de
20:25
millisecondes qui se sont écoulés et
20:27
comparé au nombre de millisecondes et
20:29
couler par rapport à la date du jour
20:32
donc on peut utiliser date point d'eau
20:33
par exemple et ça on le divise par 1000
20:36
et ça nous donne le nombre de secondes
20:39
entre aujourd'hui et cette fameuse date
20:41
donc si vous voulez connaître le nombre
20:43
de jours après faut diviser par le
20:45
nombre de secondes qu'il y a par jour et
20:47
ainsi de suite ainsi de suite donc vous
20:48
pouvez faire des calculs à la limite si
20:51
ça vous intéresse vous pouvez vous faire
20:52
un petit exercice comme ça qui consiste
20:53
à afficher en toute lettre dans combien
20:55
de temps cette date va se dérouler c'est
20:57
typiquement ce que j'utilise pour
20:58
graphicard par exemple quand vous avez
21:00
des tutoriels dans le futur quand on va
21:02
sur cette page là cette partie là qui
21:04
vous dit quand est-ce qu'une un tutoriel
21:06
est disponible c'est grâce justement à
21:08
cette comparaison de date comme quoi
21:09
c'est très très utile à ce niveau là
21:11
donc voilà pour les dates en javascript
