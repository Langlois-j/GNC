# Apprendre le JavaScript : Les fonctions usuelles

Video : https://www.youtube.com/watch?v=Qvr6Nh7rtAI

## Transcription
ah bienvenue dans ce nouveau chapitre
0:01
nous allons parler du sucre syntaxique
0:03
alors le sucre syntaxique pour le coup
0:04
c'est du bon sucre c'est bah en fait un
0:07
terme qui permet de désigner des
0:08
éléments de syntaxe qui vont nous
0:10
permettre d'écrire des choses plus
0:11
rapidement et plus simplement donc c'est
0:14
quelque chose que l'on avait vu par
0:15
exemple avec l'incrémentation on avait
0:17
créé une variable i qui était égale à 0
0:19
et si jamais on souhaitait incrémenter
0:21
cette variable là plutôt que d'écrire i
0:24
= I + 1 on a la possibilité de faire i++
0:27
voilà ça c'est du sucre syntaxique ça ne
0:30
nous apporte pas une nouvelle
0:31
fonctionnalité dans le langage ça nous
0:33
permet d'écrire d'une chose plus
0:34
rapidement alors il faut savoir qu'il y
0:37
a deux manières d'écrire les choses
0:38
d'abord on a le i plus plus ce que ça
0:41
fait c'est que ça incrémente la valeur
0:42
de I et ça nous renvoie une valeur qui
0:45
est la valeur qui est pas incrémentée
0:48
c'est à dire que i++ ça nous renvoie 0
0:50
ça nous renvoie la valeur avant
0:52
l'incrémentation il y a une autre
0:54
manière différente d'écrire les choses
0:55
qui est le plus plus i ça fait la même
0:57
chose au niveau de la valeur c'est à
0:58
dire que ça l'incrémente par contre la
1:00
valeur de retour sera la valeur après
1:02
l'incrémentation
1:03
dans certains cas mais c'est assez rare
1:06
franchement je vais pas vous mentir on a
1:08
parfois besoin d'incrémenter et de
1:09
récupérer la valeur mais ça peut être
1:12
intéressant de le faire de cette manière
1:14
là pour avoir la valeur après
1:15
l'incrémentation aussi vous avez la
1:17
possibilité lors de l'assignement de
1:19
directement faire des incrémentations
1:21
par exemple je peux lui dire je fais un
1:23
i plus = 3 dans ce cas là ça me donnera
1:26
à la fin un I qui sera égal à 6
1:30
je peux utiliser cette opération avec
1:31
des multiplications donc je peux lui
1:33
dire de multiplier par 3 et je peux
1:35
aussi faire ça avec des divisions et là
1:37
ça divisera par 3 ça nous renverra un
1:39
donc ça permet de décrire encore une
1:41
fois les choses légèrement plus
1:42
rapidement plutôt que de faire ça
1:45
donc ça c'est pour les nombres ensuite
1:47
on va parler des fonctions fléchées et
1:49
ça c'est quelque chose qui n'est valable
1:50
que pour les fonctions fléchées on l'a
1:52
vu il est possible d'avoir une fonction
1:53
qui renvoie directement le résultat en
1:55
ne mettant qu'une instruction si
1:58
j'utilise ensuite cette fonction-là on
2:00
va l'appeler double voilà je peux faire
2:03
double d'une valeur et ça va me donner
2:05
la valeur multipliée par deux ça
2:07
équivaut à avoir mis un retard petite
2:09
particularité les méthodes fléchies si
2:12
le paramètre il est unique il y a qu'un
2:14
seul paramètre pas deux mais dans ce cas
2:16
là on peut enlever les parenthèses voilà
2:19
et ça permet d'écrire le code de cette
2:21
manière là j'ai juste un petit raccourci
2:23
ça va un petit peu plus vite donc pour
2:25
des choses qui ne fonctionnent que sur
2:26
une seule ligne ça permet de d'éviter de
2:28
devoir se galérer à taper des caractères
2:30
spéciaux sur les claviers j'insiste ça
2:32
ne marche que sur les fonctions fléchées
2:34
si vous écrivez function vous ne pouvez
2:36
pas faire quelque chose
2:38
qui fonctionne comme ça votre éditeur va
2:39
complètement vriller il va vous dire non
2:41
là il vous manque des parenthèses donc
2:43
après on a les conditions sur les
2:45
conditions il y a pas mal de choses que
2:46
l'on peut écrire de manière raccourcie
2:48
donc imaginons on a une valeur a qui
2:51
vaut 3 et on aimerait bien que on est
2:53
une valeur B et lui dire en fait s'il y
2:56
a est défini je veux que ça prenne la
2:57
valeur de a mais s'il y a n'a pas de
2:59
bonne valeur je veux que ça prenne une
3:01
autre valeur mais on peut utiliser les
3:03
opérateurs logiques pour ça
3:05
si j'écris a ou 5 et que je fais une
3:09
console point log de B ici vaudra 3
3:12
parce que vu que A est une valeur qui
3:15
considérée comme trou souvenez-vous de
3:17
troufi et folsy mais dans ce cas là
3:19
c'est cette valeur là qui va être
3:20
utilisée quand on fait un quelque chose
3:22
ou quelque chose d'autre si la première
3:24
condition est vérifiée mais il ne va pas
3:26
aller sur la suite de la même manière si
3:29
jamais a valait 0 c'est une valeur qui
3:32
est considérée comme fausse mais
3:33
automatiquement B prendrait cette valeur
3:35
là par défaut c'est aussi une propriété
3:38
que l'on peut exploiter avec des
3:39
fonctions c'est à dire que si Ici vous
3:41
mettez une fonction on va l'appeler FN1
3:43
et que Ici vous mettez une autre
3:45
fonction FN2 si jamais cette fonction là
3:49
renvoie trop cette fonction-là ne sera
3:51
pas exécutée si vous utilisez un et si
3:55
cette fonction renvoie trou celle-ci
3:57
sera exécutée si cette fonction renvoie
3:59
Falls celle-ci ne sera pas exécutée et
4:01
vous allez obtenir le résultat de cette
4:02
première fonction seulement dans B
4:05
bon ça correspond à des besoins très
4:06
spécifiques donc je vais pas forcément
4:08
m'attarder sur cette syntaxe là par
4:11
contre il y a quelque chose qui est
4:12
intéressant de noter c'est qu'on a la
4:13
possibilité d'utiliser un double point
4:15
d'interrogation à la place du ou la
4:18
différence c'est que la verse la valeur
4:19
de a devra être nulle ou un define pour
4:21
que la valeur ici soit utilisée si je
4:24
sauvegarde là ça va me donner 0 parce
4:26
que 0 ce n'est pas nul ou un défi par
4:28
contre si on avait une variable a qui
4:30
était définie mais qui n'avait pas de
4:32
valeur automatiquement une utiliserait
4:34
plutôt la valeur par défaut que l'on a
4:35
mis là donc si on fait un ou il faut que
4:38
la valeur de gauche soit vrai et dans ce
4:40
cas là ça sera la valeur de gauche qui
4:42
sera utilisée si on met un double point
4:45
d'interrogation la valeur de gauche est
4:47
utilisée tout le temps sauf si elle est
4:49
nulle ou un defight si je fais un led a
4:51
= nul on verra que dans la console on
4:53
aura toujours 5 on a aussi la
4:55
possibilité de le faire de manière
4:56
directe lors d'une assignation je peux
4:59
faire un a point d'interrogation point
5:01
d'interrogation égale 3 ça ça voudra
5:03
dire je vais sauvegarder
6:04
le métier de la personne je peux faire
6:06
un console point log je peux faire
6:08
ensuite un personne point job.name et ça
6:12
va me donner ici le nom de son métier le
6:14
problème c'est que parfois ce métier
6:16
pourrait ne pas être défini typiquement
6:18
on pourrait se retrouver avec un objet
6:19
qui ressemble à ça si on essaie de
6:22
charger la page on obtient une petite
6:24
erreur parce que personne point job et
6:26
maintenant un define et du coup name
6:28
n'existe pas donc on serait obligé de
6:30
mettre une petite condition en lui
6:31
disant
6:32
if personne point job mais dans ce cas
6:34
là je peux faire un personne point de
6:36
job.name mais on a un petit raccourci
6:38
avec le point d'interrogation si vous
6:40
mettez un point d'interrogation devant
6:41
quelque chose par exemple ici ça
6:44
appellera la propriété Name seulement si
6:47
job est défini si job était nul ou un
6:50
define ben dans ce cas-là il renverrait
6:52
la valeur indie find si j'essaie ici de
6:54
dire par exemple le job est nul hop on
6:56
voit que ça nous donne toujours un
6:58
define donc parfois quand vous avez
7:00
besoin d'accéder à une propriété en
7:01
profondeur dans un objet et que vous
7:03
n'êtes pas certain que cette propriété
7:04
existe mais ça peut être très
7:06
intéressant et l'avantage c'est que vous
7:07
pouvez aussi les enchaîner par exemple
7:08
on peut s'imaginer dire j'aimerais bien
7:10
récupérer sur la personne mais personne
7:12
ne pourrait ne pas exister l'âge là je
7:14
pourrais ne pas être défini et je fais
7:16
tout string dessus cette méthode tout
7:18
string ne sera appelée que si age a une
7:20
valeur donc si je sauvegarde on voit que
7:22
ça marche bien si je venais à créer une
7:24
propriété personne qui est nulle mais ça
7:27
renverrait toujours un def find et si on
7:29
avait une personne qui avait
7:29
effectivement un âge qui est suffisant
7:32
dans ce cas là le tout string
7:33
fonctionnerait donc ça ça peut être
7:35
plutôt pratique dans certaines
7:36
situations où on ne contrôle pas
7:37
forcément l'apparence de l'objet initial
7:39
et on veut éviter de mettre plein de
7:41
conditions
7:42
alors maintenant on va parler de la
7:44
destructuration c'est quelque chose de
7:45
super pratique imaginons on a des notes
7:48
comme ça et on a par exemple 12 17 et 18
7:52
ce que j'aimerais bien faire c'est
7:54
récupérer la première et la seconde note
7:56
par défaut on serait obligé de faire
7:57
compte première note et de lui dire je
8:00
veux la note à l'index 0 et ensuite je
8:03
lui demande la seconde note donc je fais
8:05
seconde note et ça serait la note à
8:08
l'index 1 un peu compliqué on a la
8:11
possibilité d'utiliser la
8:12
destructuration ça veut dire que dans la
8:14
partie de gauche plutôt que de
8:15
simplement lui donner le nom d'une
8:16
variable on va pouvoir utiliser un
8:19
tableau et mettre le nom le nom de
8:21
constantes par exemple première note
8:25
et second de notes
8:28
dans ce cas là ce qu'il va faire c'est
8:29
que le premier élément du tableau sera
8:31
signé dans cette variable là le second
8:33
élément du tableau dans cette variable
8:35
là le troisième sera bonnement et
8:37
simplement
8:38
ignoré vu que on n'a pas de troisième
8:39
variable ici si je fais un console point
8:42
log et que je regarde première note et
8:44
second de notes ça nous donnera bien 12
8:46
et 17 on a aussi une autre possibilité
8:49
c'est de récupérer toutes les autres
8:51
notes ici je peux lui dire en deuxième
8:54
paramètre je vais mettre trois points de
8:56
suspension et appelé cette variable là
8:59
entre note
9:01
avec un S hop si je regarde la valeur de
9:03
ces deux variables là première note
9:05
vaudra 12 et en fait cette variable là
9:08
sera un tableau qui contiendra toutes
9:10
les valeurs restantes si on en avait une
9:13
troisième enfin une quatrième plutôt hop
9:15
elle apparaîtrait dans ce tableau ici
9:17
donc ça ça peut être pratique pour
9:19
extraire des valeurs et récupérer que ce
9:21
qui nous intéresse notamment si on veut
9:23
que le premier élément d'un tableau et
9:25
c'est super intéressant parce que ça va
9:26
aussi fonctionner avec les objets en
9:29
reprenant notre exemple d'une personne
9:30
on a une personne avec un first name on
9:34
l'appelle John un last name on va
9:36
l'appeler do et on va dire un âge de 18
9:39
ans maintenant si je veux recréer des
9:42
variables first name et last name je
9:44
suis obligé de faire first name et de
9:46
lui dire c'est égal à personne point
9:48
first name c'est pas très pratique
9:50
on peut faire la déstructuration comme
9:52
on le ferait avec les tableaux au niveau
9:55
de notre constante on va mettre un objet
9:57
et on va lui donner la clé que l'on soit
9:59
extraire first name ensuite on mettra un
10:02
deux points et en donnera le nom de
10:04
notre variable que l'on souhaite
10:05
appliquer par exemple on peut mettre ici
10:07
prénom dans ce cas-là la fin si je fais
10:10
une console point log de prénom ça va me
10:12
donner John il va prendre la propriété
10:15
qui correspond et la mettre dans cette
10:17
constante là si vous voulez créer une
10:19
variable qui a le même nom que la
10:20
propriété de l'objet vous n'êtes pas
10:22
obligé de faire un first name deux
10:24
points first name
10:25
vous pouvez simplement écrire first name
10:28
voilà donc là je peux extraire par
10:31
exemple le first name et le last name et
10:34
je vais avoir deux variables avec ces
10:37
informations là
10:38
et on a la même possibilité que pour les
10:40
tableaux on peut utiliser 3 points de
10:42
suspension on va appeler ça reste comme
10:44
le reste des propriétés et ça va nous
10:47
donner un objet qui contiendra toutes
10:48
les propriétés sauf celles que l'on a
10:50
extraites donc dans first name on aura
10:52
bien Jon et d'un reste j'aurai un nouvel
10:54
objet qui contiendra last name et âge
10:56
c'est-à-dire les propriétés qu'il reste
10:58
donc ça ça va être très utile notamment
10:59
pour les fonctions si vous souvenez on
11:01
avait créé une fonction
11:02
can drive qui permettait de vérifier si
11:05
l'utilisateur pouvait conduire et ce
11:07
qu'on avait fait c'est qu'on avait pris
11:08
un premier paramètre l'âge et un second
11:10
paramètre le pays le problème c'est que
11:12
peut-être plus tard on aura d'autres
11:13
paramètres qui vont se rajouter ou même
11:15
on pourrait retirer des paramètres
11:17
existants donc plutôt que de passer
11:19
plusieurs paramètres on peut lui dire en
11:21
fait j'attends un objet qui contient des
11:23
informations de l'utilisateur et
11:25
j'attends un objet qui contiendrait une
11:26
propriété âge et pays
11:28
mais ensuite dans le reste de mon script
11:30
je veux utiliser ces variables là mais
11:32
je peux utiliser la destructuration
11:33
directement à ce niveau là lui dire la
11:36
propriété âge deviendra âge et la
11:39
propriété pays sera dans le pays et
11:41
ensuite on s'imagine qu'on retournerait
11:43
trou quoi qu'il arrive mais l'avantage
11:46
c'est que ensuite quand j'appelle ma
11:47
méthode kan drive je peux lui dire je
11:49
l'appelle avec quelqu'un qui a un âge de
11:52
18 ans et qui a comme pays la France et
11:55
automatiquement ça va créer deux
11:57
variables ici âge et pays voilà si
12:00
demain on se dit ah ben j'ai besoin
12:02
d'une région en plus je peux le faire de
12:04
cette manière là et mettre Texas moi je
12:07
sais pas du tout comment ça fonctionne
12:08
et hop on en aurait juste à rajouter
12:10
cette propriété là
12:13
si jamais on attend trois propriétés et
12:15
que on en a pas une si je fais un
12:17
console point log de région à ce niveau
12:20
là il me renverra un de find donc je
12:22
peux agir en fonction de la
12:24
considération par exemple lui dire mais
12:25
si payer est un define je me base que
12:28
sur l'âge de 18 ans et ainsi de suite
12:29
donc vous pouvez faire pas mal de
12:31
logique mais ça peut permettre d'être un
12:33
petit peu plus flexible au niveau des
12:35
types des arguments d'ailleurs dans
12:37
cette situation là vous avez aussi la
12:39
possibilité de définir une valeur par
12:41
défaut c'est à dire que vous pouvez dire
12:43
si on n'a pas de région je veux que par
12:46
défaut ça soit par exemple Paris et dans
12:49
ce cas là plutôt que région prennent la
12:51
valeur indie find il prendra la valeur
12:53
Paris ça nous évite de faire ici
12:56
if région est égale à un def find mais
13:00
dans ce cas là je veux que région soit
13:02
égale à Paris c'est un petit peu plus
13:04
rapide à écrire de le faire directement
13:07
dans la déstructuration
13:09
on peut aussi le faire d'ailleurs pas
13:10
que dans la des structuration on peut le
13:12
faire dans une fonction de base par
13:14
exemple si on crée une fonction qui est
13:16
capable de calculer une puissance on
13:18
peut lui dire ben je veux un chiffre et
13:20
je veux la puissance cette puissance je
13:22
peux lui dire que par défaut c'est la
13:24
valeur de ça fonctionne de la même
13:26
manière si jamais on ne passait pas de
13:28
second argument à la fonction si je le
13:30
dis je fais un pot et j'aimerais bien
13:32
faire une puissance de 3 vu que je n'ai
13:34
pas précisé de ce gant argument il
13:36
mettra comme valeur deux par défaut
13:38
encore une fois avant ça ça n'existait
13:40
pas on était obligé de mettre des
13:41
conditions en disant si power était égal
13:43
à un def find mais dans ce cas là je
13:45
donnais une valeur par défaut c'était un
13:47
petit peu plus long et c'était toujours
13:49
pénible d'avoir ces conditions en début
13:50
de fonction donc vous pouvez dans la
13:53
destructuration mais aussi dans les
13:54
arguments mettre des valeurs par défaut
13:56
directement comme ça ensuite on va
13:58
parler encore une fois des tableaux et
14:00
des objets cette fois-ci pour les
14:01
manipuler alors imaginons on a un
14:04
tableau qui contient des notes et on va
14:06
mettre 1 et 2 bon c'est pas de très si
14:10
je veux rajouter des valeurs à ce
14:12
tableau là la première chose que l'on
14:14
avait vu c'est d'utiliser la méthode
14:15
push c'est à dire que je peux faire un
14:16
autre point push et je rajoute la valeur
14:18
3 le truc c'est que le tableau qui en
14:21
résulte est modifié ce qui peut être
14:22
dérangeant dans certaines situations on
14:25
a une syntaxe un petit peu plus simple
14:26
là j'ai remis la valeur initiale c'est
14:29
une syntaxe qui consiste à créer un
14:31
nouveau tableau vous faites un 3 points
14:33
de suspension note dans ce cas là ça va
14:36
créer un nouveau tableau qui contiendra
14:38
directement les valeurs qui on en a dans
14:41
le tableau original et ensuite on peut
14:43
même rajouter de nouvelles valeurs 3 4
14:45
et vous voyez que ça va nous donner un
14:47
nouveau tableau de notes qui contiendra
14:49
la liste des notes que l'on avait dans
14:51
le premier tableau plus les autres
14:52
valeurs que l'on met derrière si je
14:54
regarde mon objet original contrairement
14:56
à la méthode push ça ne modifie pas
14:58
l'objet tableau original on peut le
15:01
faire de cette manière là mais on peut
15:03
aussi le faire différemment en lui
15:05
disant je veux mettre les éléments à la
15:06
fin
15:07
et je peux même continuer à re-rajouter
15:10
des éléments et refaire du spread
15:11
opératoire avec d'autres éléments encore
15:13
et ainsi de suite ainsi de suite donc ça
15:15
c'est plutôt pratique si vous voulez
15:16
créer un nouveau tableau rajouter des
15:18
éléments par exemple si on veut inverser
15:21
un tableau qui se fait très souvent
15:23
c'est d'écrire les choses de cette
15:24
manière-là on fait ça et on utilise
15:27
reverse pourquoi parce que ça nous
15:30
permet comme ça de créer un nouveau
15:31
tableau qui contient les mêmes éléments
15:32
d'inverser ce nouveau tableau sans
15:34
affecter le tableau original ça nous
15:37
permet d'éviter ce problème de
15:38
modification en place à la fois pour les
15:40
méthodes rivières sortent et autres
15:42
cette propriété là va aussi fonctionner
15:44
sur les objets si je recréer notre
15:47
nouvel objet on va l'appeler personne et
15:49
on va lui donner comme prénom John
15:51
et comme last name do
15:56
donc ça on va l'appeler personne encore
15:57
une fois
15:58
si je regarde mon objet c'est bien ce
16:01
que j'ai mais ce que je peux faire c'est
16:03
utiliser la syntaxe objet lui dire
16:06
j'aimerais bien réutiliser les
16:07
propriétés de personnes et ensuite
16:10
rajouter de nouvelles propriétés comme
16:12
par exemple lâche dans ce cas-là ça ça
16:14
va me renvoyer un nouvel objet qui
16:16
contiendra les propriétés que l'on a
16:18
dans personne plus se lâche et ça sera
16:20
un nouvel objet si je regarde l'objet
16:22
original lui n'a pas été modifié il
16:24
contient seulement encore mais deux
16:26
propriétés on peut se poser la question
16:28
qu'est-ce qui va se passer si on
16:30
redéfinit une propriété qui existe déjà
16:31
c'est à dire que par exemple je décide
16:33
de rajouter un first name et de mettre
16:35
Jane si je fais ça je me retrouve avec
16:38
un objet nouveau mais qui va contenir le
16:41
first name qui a été modifié
16:43
comme pour les tableaux on peut faire
16:44
les choses en sans inverse dans ce cas
16:47
là c'est toujours en fait la dernière
16:48
propriété qu'il l'emporte si je décide
16:50
de faire personne à la fin c'est le nom
16:54
de la personne qui va être conservée et
16:55
on conservera John voilà et on peut si
16:59
je remets le système de l'âge le faire
17:00
de cette manière là aussi donc on peut
17:02
comme ça facilement créer de nouveaux
17:04
objets en réutilisant les propriétés
17:05
d'un autre donc typiquement si je veux
17:08
l'âge de la personne et là il les
17:10
informations de la personne en plus je
17:12
peux faire ça voilà c'est intéressant et
17:15
dans pas mal de situations finalement
17:17
vous allez vous en rendre compte c'est
17:18
plutôt utile alors un dernier petit
17:20
morceau de sucre avant de nous quitter
17:21
c'est quelque chose qui concerne les
17:24
conditions donc imaginons on crée une
17:26
constante âge égal 18 et on aimerait
17:29
bien afficher un message mais ce message
17:31
dépense si la personne est majeure ou
17:33
pas donc on serait obligé de créer une
17:35
variable message de ne pas lui assigner
17:37
de valeur de dire si l'âge est supérieur
17:40
à 18 dans ce cas là on ferait message
17:43
égal vous êtes majeur voilà on mettra
17:47
juste majeur et dans le cas contraire on
17:50
le dira que le message ça sera mineur
17:54
et après on peut enfin faire un truc
17:56
console point log de notre message
18:00
alors le problème c'est que c'est un
18:01
petit peu long d'ailleurs on va mettre
18:02
supérieur ou égal à 18 pour finalement
18:05
pas beaucoup de logique donc on a la
18:07
possibilité de créer des conditions en
18:09
utilisant la syntaxe ternaire c'est une
18:11
syntaxe que l'on retrouve en Javascript
18:12
mais aussi dans d'autres langages de
18:14
programmation elle fonctionne de la
18:16
manière suivante vous allez d'abord
18:17
commencer par mettre une condition donc
18:20
ici je peux créer une constante et je
18:23
vais mettre un égal et commencer par une
18:25
condition ma condition c'est que l'âge
18:27
soit supérieur ou égal à 18 ensuite on
18:30
va mettre un point d'interrogation et on
18:32
mettra la valeur que l'on souhaite
18:33
assigner si jamais la condition est
18:35
vérifiée nous ici c'était majeur
18:39
ensuite on mettra deux points et on
18:41
mettra la valeur à assigner si la
18:43
condition est fausse donc nous ici on
18:46
mettra mineur
18:48
si je sauvegarde on voit bien que ça me
18:50
donne toujours majeur ce que je peux
18:51
faire c'est carrément enlever la
18:53
variable intermédiaire et faire ça
18:54
directement dans mon console.log si là
18:57
j'ai supérieur ou égal à 18 on me dira
18:59
que je suis majeur si là j'étais fire ou
19:01
à 18 mais dans ce cas là on me dira que
19:04
je suis mineur donc ça ça peut permettre
19:06
d'écrire les choses un petit peu plus
19:07
rapidement pour éviter une condition
19:09
donc très souvent lorsque vous avez un
19:11
IF condition et que vous assignez la
19:13
même valeur dans le I et dans le else on
19:16
va plutôt utiliser cette syntaxe
19:17
ternaire qui est un petit peu plus
19:18
simple
19:19
on notera peut-être même si je vous
19:21
déconseille de le faire donc je vous le
19:23
dis mais oubliez le tout de suite vous
19:25
pouvez avoir des ternaires dans des
19:26
ternaire hop moi j'ai pas forcément
19:29
avoir un exemple super idéal mais on
19:32
pourrait ici avoir un sillage et
19:34
supérieur à 16 mais dans ce cas-là à ce
19:36
niveau là on va regarder est-ce que le
19:38
pays est égal à la France et si le pays
19:41
est égal à la France on le dira conduire
19:42
et dans le cas contraire on mettra à
19:45
autre chose et du coup on a deux
19:46
ternaires impliquées pourquoi on
19:48
l'évitera tout simplement parce que
19:50
c'est est absolument illisible quand on
19:52
relie ce code là donc gardez le ternaire
19:54
vraiment pour des conditions de niveau 1
19:56
n'allez pas imbriquer du Turner dans du
19:58
ternaire parce que c'est
19:59
l'assurance de ne plus rien comprendre à
20:01
votre code dès que vous clignez des yeux
20:04
et là on a terminé du coup avec ces
20:06
éléments de syntaxe lorsque je ferai
20:08
c'est que je vais toutes les lister dans
20:09
l'article qui est en bas de cette vidéo
20:12
si jamais il y a de nouvelles éléments
20:14
de syntaxe et de nouveau petit truc
20:16
syntaxique qui sont intéressants mais je
20:18
vous les mettrai dans l'article pour les
20:19
rajouter mais là je vous ai montré les
20:21
principaux que vous avez besoin de
20:22
connaître et de reconnaître surtout dans
20:24
le code encore une fois ne vous sentez
20:25
pas obligé de les utiliser si vous les
20:28
voyez c'est important de savoir de quoi
20:29
il en retourne mais quand vous écrivez
20:31
du code au jour le jour si vous n'êtes
20:32
pas à les axes syntaxe ce n'est pas
20:33
dramatique il y a toujours des moyens
20:35
détournées de faire les choses
20:37
j'espère que ça vous servira et je vous
20:39
donne rendez-vous dans le prochain
20:39
chapitre

