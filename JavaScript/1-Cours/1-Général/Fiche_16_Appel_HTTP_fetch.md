# Apprendre le JavaScript : Promise

Video : https://www.youtube.com/watch?v=z9pcgJX1DdY

## Transcription

alors bienvenue dans cette nouvelle
0:01
vidéo aujourd'hui je vous propose de
0:02
parler d'une méthode en particulier en
0:04
javascript qui est la méthode fech alors
0:06
aujourd'hui on va la voir côté
0:07
navigateur mais il faut savoir que c'est
0:09
une fonction qui est tellement
0:10
importante que elle est en général
0:11
disponible sur les autres environnements
0:13
aussi faites tu vas nous permettre de
0:15
contacter un serveur pour pouvoir
0:17
récupérer des informations donc on va
0:19
pouvoir faire des appels HTTP depuis le
0:21
Javascript si on fait ça côté navigateur
0:23
c'est le navigateur qui fera l'appel et
0:25
qui nous donnera la réponse et si on
0:26
fait ça à côté serveur c'est le serveur
0:28
qui contactera justement cette adresse
0:30
alors pour essayer faites on va utiliser
0:33
un site qui s'appelle J5 playsolder
0:35
c'est un site qui est intéressant parce
0:37
qu'en fait il propose des sortes de
0:38
petites API qui sont préconçues par
0:40
exemple si je fais un slash users mais
0:43
je vais obtenir directement des
0:45
informations sur les utilisateurs avec
0:46
un format particulier qui est le format
0:48
jyson donc c'est très pratique si on
0:50
veut tester justement ces API là pour
0:52
pouvoir commencer alors ce que je vais
0:54
faire ici sur ma page je sais que je
0:57
vais aller créer une constante que je
0:58
vais appeler R pour et je vais utiliser
1:01
cette méthode fetch cette méthode elle
1:03
prend un premier paramètre l'URL que
1:05
vous souhaitez appeler donc nous dans
1:07
notre cas on va mettre cette url là donc
1:09
pour récupérer une liste d'utilisateurs
1:12
ensuite en second paramètre on peut
1:14
avoir un objet qui va contenir tout un
1:16
tas d'options que l'on pourra passer à
1:18
notre requête quel type de méthode on
1:19
souhaite utiliser est-ce qu'on rajoute
1:21
des en-têtes donc on pourra faire plein
1:22
de choses mais pour l'instant on va se
1:24
contenter d'ignorer ce second paramètre
1:26
il est entièrement optionnel
1:29
ensuite on va faire une console point
1:30
log et voir qu'est-ce qu'il y a dans
1:32
cette fameuse variable R
1:34
si je sauvegarde et que je me rends dans
1:36
la console on va nous parler d'une
1:38
promesse donc c'est justement une des
1:40
fonctions javascript qui utilise les
1:42
promesses nativement et ça c'est plutôt
1:43
sympa si on déplie ben on va voir que
1:46
cette promesse là elle vient d'être
1:47
remplie donc ça veut dire qu'il a bien
1:49
contacté le serveur on peut vérifier
1:51
cela en allant dans un autre onglet au
1:53
niveau de notre navigateur c'est
1:55
l'onglet réseau cet onglet nous montre
1:57
les requêtes réseau qui sont faites par
1:59
la page et si on réactualise je vais
2:02
voir en bas que il va bien contacter
2:03
slash users voilà mais nous on va rester
2:06
ici dans la partie console c'est le plus
2:09
important donc idéalement on aimerait
2:11
bien attendre que cette requête est
2:13
finie donc là on a deux techniques soit
2:15
on fait une fonction asynchrone et
2:16
dedans on fait un wait soit on utilise
2:18
le système de callback avec veine donc
2:21
nous on va plutôt faire ça on va lui
2:22
dire lorsque tu as fini donc de
2:25
contacter le serveur j'aimerais bien que
2:27
tu me montres de quoi il en retourne
2:30
et je vais enlever cette variable là si
2:33
je sauvegarde maintenant ça met un petit
2:35
temps à se charger mais là c'est très
2:37
rapide vu que j'ai une bonne connexion
2:38
et à la fin je me retrouve avec un objet
2:40
de type responsable c'est un objet qui
2:43
est spécifique au navigateur mais on va
2:45
avoir le même type d'objet lorsque l'on
2:46
va travailler dans d'autres
2:47
environnements de manière générale les
2:49
gens qui développent des outils basés
2:50
sur le Javascript et c'est de faire en
2:52
sorte que ça soit assez unifié en termes
2:53
d'expérience dans cet objet on retrouve
2:56
plein d'informations on a le body qui va
2:58
être un flux de données on a les
3:00
en-têtes donc ça c'est ce que renvoient
3:02
le serveur donc on peut obtenir plein
3:03
d'informations sur ce qui était renvoyé
3:06
justement on a une propriété ok qui elle
3:09
est très importante ce qui nous permet
3:10
de savoir si la réponse est bonne ou non
3:12
on a ensuite redirectible qui permet de
3:14
savoir si ça a été redirigé le statut le
3:17
texte et ce genre de choses
3:19
si vous avez besoin de plus
3:20
d'informations sur cet objet responsable
3:22
vous pouvez chercher dans la
3:23
documentation donc là on va regarder la
3:25
documentation qui a créé au navigateur
3:27
et si on descend un petit peu on va
3:29
retrouver les différentes propriétés que
3:30
l'on a regardé rapidement alors nous ce
3:33
qui nous intéresse c'est de récupérer le
3:35
texte on aimerait bien avoir le contenu
3:37
de la réponse donc à ce niveau là je
3:40
vais exécuter une fonction et sur la
3:43
réponse on a une méthode qui s'appelle
3:45
texte cette méthode là si on regarde
3:48
dans la documentation hop
3:50
on descend un petit peu donc elles sont
3:52
ici
3:53
on a une méthode texte et on nous dit
3:56
que ça retourne une promesse avec une
3:58
représentation textuelle du body donc ça
4:01
veut dire qu'à ce niveau là je vais
4:03
retourner r point texte donc ça veut
4:06
dire que ça ça va nous renvoyer une
4:07
promesse
4:08
et cette promesse là nous renverra le
4:10
texte sous forme de chaîne de caractères
4:12
donc là on est typiquement dans la
4:14
situation que on avait vu avec les
4:16
promesses où on peut enchaîner les
4:17
choses je vais attendre la résolution de
4:20
cette seconde promesse là ce qui va me
4:22
donner le contenu on va appeler ça body
4:24
et là je peux faire un console pour un
4:26
log de body si je reviens au niveau de
4:29
ma page on va voir maintenant si je
4:31
réactualise ou si je sauvegarde tout
4:33
simplement que à ce niveau là j'obtiens
4:35
bien donc juste mon texte qui va
4:38
contenir tout le gyson alors si vous
4:40
n'êtes pas familier avec le format JSON
4:42
c'est un format qui ressemble beaucoup
4:44
au JavaScript c'est pour ça que les
4:45
développeurs JavaScript aiment beaucoup
4:46
ce format là on reconnaît ici la syntaxe
4:48
pour les tableaux on a aussi la une
4:50
syntaxe comme pour des objets sauf que
4:52
les clés doivent toujours être entre
4:53
guillemets et ensuite les valeurs ça
4:55
peut être soit des nombres soit des
4:57
chaînes de caractères et ce genre de
4:58
choses
4:59
et ce format là est aussi super
5:01
intéressant dans le cadre de
5:03
l'utilisation de fetch parce que si on
5:05
regarde dans la documentation on a aussi
5:07
une méthode JSON qui un petit peu comme
5:09
la méthode texte va permettre de
5:11
renvoyer le corps de la réponse par
5:14
c'est enregisone donc à ce niveau-là on
5:16
va remplacer notre r.texte par un r.son
5:19
donc on prend notre réponse et on va la
5:21
passer sans nous dit bien que ça renvoie
5:23
une promesse et du coup à l'après je
5:26
vais récupérer des données et je peux
5:27
faire une console point loc de body si
5:30
je sauvegarde maintenant hop je vais
5:32
voir que dans ma console je n'ai plus la
5:34
représentation textuelle de ma réponse
5:35
mais j'ai un objet qui contient les
5:38
différents utilisateurs que j'ai
5:39
récupéré depuis l'API donc c'est super
5:42
pratique pour ce genre de choses alors
5:44
par contre il faut faire attention
5:45
imaginons que j'essaie de contacter une
5:47
page qui n'existe pas là on tombe sur
5:49
une erreur ici on regarde un petit peu
5:51
hop ce que ça donne au niveau de la
5:52
console alors heureusement le serveur
5:55
répond toujours du JSON mais ce qu'il
5:57
faudrait faire c'est vérifier est-ce
5:58
qu'on a bien un statut de
6:00
donc imaginons nous on veut récupérer
6:02
les utilisateurs donc on va créer une
6:04
méthode que l'on va que l'on va appeler
6:06
fetch users et vu qu'on va utiliser
6:09
faite sur l'intérieur on va préciser que
6:10
cette méthode sera à synchrone
6:13
à l'intérieur on peut récupérer la
6:15
réponse par convention moi je vais
6:17
l'appeler R et je vais lui demander de
6:19
faire la partie fetch mais seulement
6:20
cette partie là
6:23
une fois que c'est fait donc je vais
6:25
attendre que cette promesse soit résolue
6:27
je vais lui dire si
6:29
r.ok est égal à trou ça veut dire qu'on
6:32
a bien une réponse de type de sang mais
6:35
dans ce cas là je peux lui demander de
6:37
faire la suite je peux lui demander de
6:38
passer en faisant un constat égal awate
6:42
de
6:44
r.gison et après je retourne les données
6:47
où là directement je peux retourner ma
6:49
promesse sans m'embêter
6:52
dans le cas où on a eu un problème on
6:54
pourra faire un Frau new
6:56
error et on mettra impossible de
6:59
contacter le serveur
7:01
maintenant que cette fonction asynchrone
7:03
existe je peux l'utiliser beaucoup plus
7:04
simplement à ce niveau là je peux faire
7:06
un feetch user et lui dire que lorsque
7:09
je récupérerai des résultats donc ça
7:11
sera des utilisateurs je pourrais faire
7:13
un console point log et dans le cas où
7:15
il y a une erreur je pourrais faire un
7:16
catch pour justement afficher les
7:19
l'erreur au niveau de ma console si je
7:22
réactualise la page je tombe bien ici
7:23
sur l'erreur qui me dit impossible de
7:25
contacter le serveur donc le reste du
7:27
code à savoir le parking du JSON ne se
7:30
fera que si la règle le serveur répond
7:32
avec une 200 je remets maintenant
7:35
users normalement et on voit que ça
7:37
fonctionne convenablement
8:20
une autre propriété intéressante c'est
8:22
la méthode par défaut on envoie tout en
8:25
utilisant la méthode GET donc si vous
8:27
avez besoin de plus d'informations sur
8:28
comment formaliser une requête HTTP
8:30
c'est vrai que là je vous donne les
8:32
informations directement mais je pars du
8:34
principe que vous avez déjà vu la partie
8:36
de la formation destinée à l'http c'est
8:38
normalement dans la partie cursus mais
8:40
si jamais vous faites une recherche et
8:41
vous cherchez HTTP voilà vous avez cette
8:44
vidéo là qui vous explique ce qui est
8:46
une requête HTTP comment les formalisée
8:48
les antennes tout ça tout ça ce qui va
8:50
être intéressant c'est aussi lorsque
8:52
l'on va avoir besoin d'envoyer des
8:54
données donc typiquement j'aimerais bien
8:56
poster des informations à un serveur si
8:59
par exemple que le cas rempli un
9:00
formulaire ou ce genre de choses alors
9:02
pour poster des informations on va
9:04
appeler une URL qui s'appelle poste ici
9:07
qui va permettre de créer un nouvel
9:08
article on va lui préciser que ça va
9:10
être une méthode de type post
9:13
on précise toujours le header on va en
9:16
rajouter un autre qui est le content
9:17
type qui permettra d'indiquer à quoi
9:20
ressemble les données que nous on va
9:21
envoyer souvent c'est ces deux en tête
9:23
que vous allez manipuler accepte pour
9:25
dire ce que vous vous attendez et que
9:27
vous acceptez comme format et quand elle
9:29
ce type ce que vous vous allez envoyer
9:31
ensuite vous pouvez rajouter body et
9:34
vous allez devoir mettre le body à
9:35
l'intérieur ça peut être une simple
9:38
chaîne de caractère ou des objets
9:39
spéciaux en fonction de la situation
9:41
nous on veut envoyer simplement un gyson
9:44
donc on va mettre ça sous forme de
9:45
chaine de caractère on va lui dire
9:47
j'aimerais bien un titre pour mon
9:49
article et on va l'appeler mon premier
9:51
article
9:53
si vous voulez automatiquement générer
9:55
un gestionnaire à partir d'un objet
9:57
JavaScript c'est possible de le faire
9:58
grâce aux méthodes qui sont disponibles
10:00
sur l'objet JSON encore une fois faites
10:03
un petit tour sur la documentation je
10:05
veux vraiment que vous preniez cette
10:07
habitude parce que souvent on va
10:09
découvrir plein de nouvelles choses et
10:10
surtout quand il y a de nouvelles choses
10:11
c'est important d'être capable justement
10:13
de découvrir les choses par soi-même
10:15
donc cet objet ne contient que deux
10:17
méthodes une qui permet de percer un
10:19
gyson et une qui permet de générer un
10:21
gyson à partir d'un objet donc c'est
10:23
très très facile à utiliser pour le coup
10:25
nous dans notre cas à ce niveau là on
10:28
peut lui dire plutôt que de manuellement
10:31
faire le gyson on fait un j5.stringify
10:33
et on lui donne un objet en mettant
10:36
title mon premier titre et
10:38
automatiquement le navigateur va le
10:40
convertir si vous voulez faire un petit
10:42
essai vous pouvez vous rendre sur votre
10:43
page vous mettez ça dans votre console
10:45
et vous voyez que ça me donne la même
10:47
résultats que moi que ce que moi j'avais
10:49
mis
10:50
voilà c'est un petit peu plus rapide un
10:52
petit peu plus simple d'utilisation
10:55
alors maintenant on va sauvegarder et
10:58
dans ma console voilà ce que j'obtiens
11:00
j'obtiens un nouvel objet c'est la
11:02
réponse du serveur le serveur me dit oui
11:04
j'ai bien enregistré ton article j'ai
11:06
mis light 101 et j'ai bien mis le title
11:08
que tu m'as demandé si je mets un autre
11:11
titre mon premier titre hop et dans ce
11:14
cas là il va répondre aussi avec ce
11:16
titre là donc on peut avec cette méthode
11:18
faite contactez un serveur et recevoir
11:20
les informations en retour si votre
11:22
serveur répond avec du gyson mais vous
11:24
pouvez le passer directement en
11:26
utilisant le système de promesses sinon
11:28
vous pouvez récupérer sous forme de
11:30
texte grâce à la méthode texte il faudra
11:32
bien faire attention à vérifier est-ce
11:34
que la réponse du serveur est
11:35
satisfaisante une réponse va être
11:37
considérée comme ok si son statut est
11:40
supérieur à 200 et inférieur à 400
11:43
alors on va regarder un petit peu plus
11:45
dans la documentation les différentes
11:48
options qu'il est possible d'utiliser
11:49
sur fetch donc on va chercher fetch on
11:52
va directement sur la partie API donc on
11:55
nous explique plein plein de choses donc
11:57
nous c'est fait ce qui nous intéresse et
11:59
on s'intéresse plutôt aux options donc
12:01
voilà les options que l'on a donc
12:03
méthode on a vu et d'ailleurs et body on
12:05
l'a vu on va avoir le mode mais ça c'est
12:07
spécifique au navigateur créditchell
12:10
social donc c'est pour ça qu'on s'y
12:11
intéresse pas et peut-être le redirect
12:13
qui peut être important qui spécifique
12:15
comment on doit suivre une redirection
12:17
par exemple si notre serveur renvoie une
12:19
301 ou 302 en disant ben en fait c'est
12:22
pas la bonne page ça en est une autre
12:23
par défaut le fait ici va suivre cette
12:26
redirection mais vous pouvez ensuite
12:27
gérer ça de différentes manières après
12:30
sur l'objet réponse au niveau des
12:32
méthodes que vous avez je suis pas sûr
12:34
qu'à des tonnes de super super
12:35
intéressantes peut-être pour la partie
12:37
headers si vous souhaitez extraire une
12:40
en tête en particulier le l'objet Eder
12:43
c'est un marché spécial c'est à dire que
12:44
si vous faites ici un console point log
12:47
r.eders ça ne vous donne pas simplement
12:49
un objet JavaScript mais ça vous donne
12:51
un objet de type eders qui va contenir
12:53
les différentes en tête si on veut
12:55
ensuite accéder à une enquête en
12:56
particulier on peut faire point get et
12:59
nous on va regarder quel containte type
13:01
utilise le serveur est-ce qu'il nous
13:03
répond avec du JSON ou pas et là on a ce
13:06
content de type si jamais vous mettez
13:08
une clé qui n'existe pas qui n'est pas
13:09
renvoyée par le serveur ça vous renverra
13:11
nul voilà donc si jamais vous avez
13:13
besoin de modifier les en-têtes ça peut
13:15
être fait de cette manière là de la même
13:18
manière lorsqu'on utilise le fetch en
13:19
premier paramètre on voit qu'on peut lui
13:21
passer autre chose effectivement je vais
13:25
revenir un petit peu en arrière le
13:27
premier paramètre peut être une chaîne
13:28
de caractère ou une requête une requête
13:31
c'est un objet qui va permettre de
13:33
représenter la requête donc on peut
13:34
construire cet objet là si on le
13:36
souhaite mais de manière générale quand
13:37
vous allez utiliser faite vous allez
13:39
essentiellement l'utiliser de cette
13:41
manière là en spécifiant une URL
13:43
d'expérience c'est assez rare qu'on
13:45
utilisait un objet
13:47
alors maintenant on va parler d'un
13:48
quelque chose qui est beaucoup plus
13:49
spécifique c'est la possibilité
13:51
d'arrêter une infech alors imaginons on
13:55
a deux serveurs à contacter et on
13:57
s'intéresse à la réponse hop dans les
13:59
deux cas donc on imagine contacter la
14:02
partie qui nous récupérez la liste des
14:04
articles et on va lui dire j'aimerais
14:06
bien récupérer que 5 voilà comme ça donc
14:11
ça c'est spécifique à
14:13
jasonplay solder qui nous permet de
14:15
choisir le nombre d'éléments que l'on
14:17
souhaite renvoyer si je fais ça on voit
14:19
que je vais récupérer que 5 articles et
14:21
on s'imagine faire le même fetch mais
14:23
pour récupérer 5 utilisateurs voilà donc
14:26
on va hop faire ce premier fetch et ce
14:29
second fetch et là ce qui m'intéresse
14:31
c'est de contacter ces deux URL et de
14:34
récupérer le premier résultat qui arrive
14:37
donc histoire de simuler une requête qui
14:39
est lente on a la possibilité avec J7
14:40
playsolder de rajouter un paramètre dans
14:42
l'URL délai et de lui dire on veut un
14:45
délai qui soit de
14:47
2000 millisecondes comme ça ça mettra de
14:50
seconde donc techniquement les
14:51
utilisateurs vont arriver avant les
14:53
articles donc ce que l'on peut faire
14:55
c'est utiliser promise.race lui passer
14:58
un tableau de promesses donc on lui
15:01
passerait notre première requête qui est
15:03
serait celle qui contacterait les
15:04
articles et une seconde requête qui
15:07
serait celle qui contacterait les
15:09
utilisateurs voilà je mets un peu
15:11
d'indantation ensuite je vais faire un
15:13
veine ce veine sera appelé lorsque une
15:16
des promesses sera résolue et je vais
15:19
lui dire de faire un r point JSON et
15:22
ensuite je vais récupérer le résultat en
15:24
faisant un veine et un console point loc
15:26
voilà si je sauvegarde maintenant et que
15:29
je regarde ma console je vois bien que
15:31
j'obtiens 5 utilisateurs parce que cette
15:33
requête là est plus rapide que l'autre
15:36
d'ailleurs je vais plutôt changer la
15:37
limite comme ça on pourra juste avec la
15:39
taille du tableau savoir lequel a
15:40
répondu le principal inconvénient de
15:43
cette approche là c'est que même si on
15:45
lui dit de continuer notre code dès que
15:47
la première requête a répondu l'autre
15:49
requête continue à se faire on peut
15:51
s'arrentre compte dans l'onglet réseau
15:52
ici hop hop je vais essayer de dégrossir
15:56
un tout petit peu voilà si je réalise on
15:59
voit bien que cette seconde requête met
16:01
deux secondes à s'exécuter mais elle
16:03
finit par s'exécuter ça serait bien de
16:05
lui dire au fait la première a répondu
16:07
et du coup c'est pas la peine de
16:08
continuer l'autre donc on a la
16:10
possibilité d'annuler une requête fetch
16:13
sauf que la manière de le faire est très
16:15
très bizarre vous allez le voir d'abord
16:17
on doit créer une constante qui va
16:19
s'appeler a mais vous pouvez l'appeler
16:21
comme vous voulez et on va initialiser
16:22
ce qu'on appelle un abort contrôleur
16:24
c'est un contrôleur qui va permettre
16:26
ensuite d'envoyer un signal pour annuler
16:29
des requêtes HTTP
16:31
ensuite lorsque l'on fait un fech on va
16:34
pouvoir lui passer en second paramètre
16:35
un objet d'option et il y a une option
16:37
qui s'appelle signal et on lui passe
16:39
comme signal le la propriété signale de
16:42
notre board contrôleur on va faire ça
16:44
pour nos deux requêtes si vous voulez on
16:47
va connecter en fait nos requêtes à ce
16:49
signal là et quand on le souhaitera on
16:51
pourra envoyer un signal d'annulation
16:52
ensuite lorsque j'ai fini d'effectuer
16:55
tout mon traitement on s'imagine ici
16:57
qu'on récupérerait le body
16:59
je vais faire le console.log de mon body
17:02
mais je vais aussi lui dire il faudrait
17:05
que tu annules les requêtes qui sont
17:06
toujours en attente donc ici je vais
17:07
faire un a point à Bordes ça va envoyer
17:11
un signal qui sera capturé par les
17:13
différentes requêtes HTTP qui vont être
17:16
toujours en cours et ça va les annuler
17:17
si je sauvegarde j'obtiens toujours mon
17:20
résultat donc on obtient 5 ou 3 suivant
17:23
laquelle répond la plus rapidement et
17:24
l'autre est automatiquement annulé et
17:26
c'est ce qu'on peut voir dans l'onglet
17:27
réseau ici on voit que celle-ci n'a même
17:30
pas de statut elle été complètement
17:32
coupé donc le navigateur a arrêté de
17:34
charger les choses et voilà comment on
17:36
peut gérer une annulation de requête
17:38
c'est un peu spécifique ça correspond à
17:41
des besoins très très particuliers mais
17:43
c'est important de savoir économiser les
17:44
ressources et d'annuler des requêtes si
17:46
jamais on a un système de requête
17:48
simultanée en même temps
17:51
et là on a fait le tour de ce qu'il y
17:52
avait à savoir de manière générale sur
17:54
faite donc si jamais vous avez besoin de
17:56
récupérer des informations depuis une
17:58
API il faudra utiliser cette méthode là
18:00
et après on obtient un objet réponse sur
18:02
lequel on peut faire différentes
18:03
traitements suivant le type de réponse
18:05
que l'on obtient
18:06
donc j'espère que ça vous servira et je
18:08
vous donne rendez-vous dans le prochain
18:09
chapitre