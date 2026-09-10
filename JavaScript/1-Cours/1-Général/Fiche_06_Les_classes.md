
Rechercher dans la vidéo
0:00
alors bienvenue dans ce nouveau chapitre nous allons parler maintenant de la notion de prototype et nous allons voir les classes et la programmation orientée
0:06
objet en Javascript alors d'abord on peut euh remarquer quelque chose c'est
0:11
que lorsque je crée un objet un objet simple avec par exemple une propriété lorsque je regarde dans la
0:17
console cet objet-là et que je fais point on me montre des propriétés ou des
0:23
méthodes qui existe déjà pourtant on peut se dire bah d'où ça ça vient parce que moi je n'ai jamais écrit un as on
0:30
property pourtant ben il me dit bien que ça existe sur cet objet a ce phénomène
0:36
est dû au système de prototype alors on va regarder notre objet a et on va le déplier au niveau du navigateur si je le
0:44
déplie on voit qu'on me parle de ma propriété que j'avais bien définie et on me montre quelque chose qui est le
0:49
prototype si je le déplie on reconnaît les différentes méthodes qui m'étaient suggérer lorsque j'ai fait point en fait
0:56
lorsque l'on cherche à accéder à une propriété ou une méthode il va d'abord regarder dans l'objet mais s'il ne le
1:01
trouve pas il va le chercher dans le prototype et ce prototype peut aussi être obtenu en faisant
1:08
objectget prototype of et on lui passe notre variable par exemple a si on fait
1:15
ça ça nous donne accès aux méthodes telles qu'elles sont écrites ici dans l'inspecteur ce qu'il est intéressant de
1:22
noter c'est que si on fait un get prototype off d'une chaîne de caractère qu'est-ce qui se
1:27
passe on voit que l'on obtient quelque chose chose qui s'appelle string et c'est un objet qui contient tout un tas
1:33
de méthodes et si on descend descend descend on voit que cet objet là a aussi
1:39
un prototype et c'est ce que l'on reconnaît c'est le prototype de nos objets donc finalement qu'est-ce qu'on
1:46
remarque une chaîne de caractère peut avoir ses propres méthodes ensuite elle a un prototype que l'on va appeler
1:52
string. prototype qui contient ben des méthodes particulières comme par exemple
1:58
split to de ch et ce prototype aura lui-même les méthodes de l'objet et
2:06
c'est comme ça que fonctionne le système d'héritage en Javascript lorsquon utilise une méthode il va d'abord
2:11
regarder est-ce qu'on l'a dans notre objet courant si on l'a pas il va regarder dans le prototype de cet objet et si notre objet a luiême un prototype
2:18
il va continuer comme ça de chercher d'élément en élément ça explique si par
2:24
exemple je reviens sur la documentation et que on cherche uner
2:30
voilà cette méthode elle nous est montrée non pas directement sur string mais on nous dit c'est sur le prototype
2:36
de string donc ça veut dire que toutes les chaînes de caractère y auront accès parce que les prototypes des chaînes de
2:42
caractère sont de cette manière-là et on remarquera que ça c'est la même chose aussi pour les tableaux par exemple si
2:47
on regarde ay on va avoir le ay.protype point quelque chose typiquement on va avoir par exemple une
2:53
méthode push qui permet de rajouter un élément à un tableau c'est sur le prototype donc tous les tableaux on
2:59
comme prototype cet élément- là et ont du coup accès à toutes ces méthodesl et ils ont aussi accès aux méthodes des
3:06
objets de manière général dans le langage de base du Javascript vous vous allez avoir que deux niveaux de
3:11
profondeur c'est-à-dire que vos objets que vous allez créer donc vos entiers vos nombres vos tableaux et tout ça ils
3:17
vont avoir les méthodes qui sont disponibles dans leur prototype associé et ensuite dans le prototype des objets
3:23
et c'est tout vous n'aurez pas trois ou quatre niveaux de profondeur mais c'est toujours intéressant de savoir que ça fonctionne de cette manière- làà en
3:29
interne alors vous vous dites c'est vachement bien mais est-ce que nous du coup on peut se créer nos propres prototypes
3:35
c'est-à-dire lister tout un tas de méthodes et de choses comme ça comme ça après on pourra créer des objets plus
3:40
facilement typiquement pour représenter un élève par exemple on a envie de préciser un prénom un nom et peut-être
3:46
ensuite avoir une méthode qui permet de récupérer le nom tout attaché ça serait pas mal de pouvoir avoir une sorte de
3:53
type personnalisé mais c'est ce que l'on peut faire grâce à la syntaxe des classes alors on va remettre ça
4:00
on peut écrire classe et donner un nom à notre classe par convention on mettra ce nom en majuscule mais c'est pas du tout
4:07
une obligation et ensuite on écrira des accolades rien qu'en faisant ça on a
4:12
créé si vous voulez notre type personnalisé si je regarde à quoi ressemble student on me dit pour
4:18
l'instant que c'est une classe mais juste en regardant comme ça le navigateur nous dit aussi que c'est une
4:24
fonction si on regarde d'ailleurs le type of de Student on nous dit que c'est une fonction les prototypes sont des
4:31
fonctions par exemple string qui est donc le truc sur lequel on a les prototypes les différentes méthodes si
4:37
je regarde le type of de string on me dit bien que c'est une fonction mais c'est une fonction qui va marcher un
4:43
petit peu particulièrement on a la possibilité d'abord de donner des propriétés par exemple on peut
4:48
s'imaginer que tous nos étudiants seront dans la même école on peut mettre à l'intérieur une propriété école et on
4:54
lui dira que c'est Jules Ferry bon en état ça ne change rien
5:01
maintenant la particularité c'est que je peux créer un objet qui aurait comme prototype cet élément là pour cela on ne
5:08
le l' crée pas de manière classique en écrivant un objet mais on va créer un nouvel étudiant on va l'appeler John et
5:16
on va mettre le mot-clé new suivi du nom de notre classe student et ensuite on va
5:22
mettre des parenthèses comme si on appelait une fonction et juste derrière on va faire un console. log de John
5:28
histoire de vous montrer un petit peu de quoi il a retourne donc là on voit bien qu'on a notre objet si je le déplie on
5:35
voit que il a tout de suite une propriété qui va être défini qui sera école qui se fait automatiquement grâce
5:42
à ce que j'ai mis au niveau de la classe et si je regarde le prototype on me dit que c'est bien ma classe student et si
5:49
je regarde ce prototype ensuite mais là on reconnaît le prototype des objets de base ce que l'on peut faire c'est
5:54
définir une manière de construire nos élèves typiquement on aimerait bien que les personnes précise un prénom et un
6:01
nom alors pour définir un constructeur on va utiliser une méthode à l'intérieur
6:06
de ces classes que l'on va appeler constructor donc là vous n'avez pas le choix dans le nom de vos fonctions c'est
6:13
systématiquement constructor ensuite vous allez ouvrir et fermer la parenthèse et mettre une acolade la
6:20
particularité c'est que les fonctions qui vont être défines dans les classe il n'y a pas besoin de mettre le mot-clé function devant automatiquement on les
6:28
définit de cette manière-là donc ce constructeur on avait dit qu'on allait attendre deux paramètres le
6:33
prénom et le nom maintenant quand j'initialise mon
6:39
étudiant je vais devoir lui passer un nom John et un prénom do voilà en état ça ne changera pas
6:47
grand-chose mais ce que l'on va pouvoir faire c'est définir des propriétés à l'intérieur de notre objet et c'est là
6:52
queon va revenir à notre fameux vis que on avait un petit peu oublié depuis qui
6:58
nous permettra d'accéder à l'objet alors on va faire un console. log de vis avant même d'aller plus loin histoire que vous
7:04
voyez de quoi il en retourne donc vis nous fera référence à notre étudiant actuel donc notre étudiant que l'on
7:11
initialise si je veux définir des propriétés dessus je peux faire
7:17
vis.fstname et dire ben je prendrai le paramètre qui est passé et faire la même
7:22
chose pour le last name voilà si je fais ça maintenant je
7:29
vois voit que lorsque j'initialise mon étudiant il va avoir trois propriétés école qui est prédéfinie en Durre parce
7:35
qu'on avait mis dans la classe mais aussi les propriétés first name et last name ce que je peux faire c'est créer un
7:42
nouvel étudiant on va créer Jane donc il va s'appeler jeo dans ce cas-là vis dans le premier
7:50
appel fera référence au premier étudiant et vis dans le second appel fera référence à notre second étudiant si je
7:56
débug maintenant les deux étudiants on voit qu'on a d'un d'une part John do et
8:02
d'autre part Jane do maintenant on va s'imaginer que on puisse passer des notes au à nos étudiants mais on veut
8:09
pas forcément le faire systématiquement donc on va pas le faire dès le constructeur on va se créer une méthode qui permettra de renseigner les notes
8:16
pour créer une méthode on donne un nom à notre méthode donc là c'est comme les fonctions on peut donner le nom que l'on
8:21
veut donc en respectant les règles des de définition des variables évidemment on utilise pas le motcé function on met
8:28
les parenthèses pour les paramètres et ensuite on va mettre le corps de notre fonction moi dans mon cas je
8:33
m'attendrais à avoir des notes et pour mémoriser ces notes je vais les définir comme une propriété de notre objet comme
8:41
ceci je sauvegarde si maintenant j'ai envie de sauvegarder dans John des notes
8:47
je peux faire john.7 notes je lui donne un tableau de notes par exemple on imagine que il a 10
8:53
et 20 pas très régulier si je regarde maintenant à quoi ressemble John tient
8:59
donc toujours mon élève sauf que à l'intérieur il a les notes si je regarde mon étudiante Jane elle elle n'a pas de
9:07
notes parce qu'on n'a pas utilisé la méthode 7 dessus donc grâce à ce système de prototype on peut créer des méthodes
9:13
qui vont être partagées on voit effectivement que dans notre objet on na pas la méthode set notes on n' pas la
9:18
méthode constructor elle est directement disponible au niveau du prototype c'est pour ça qu'on peut l'appeler à la fois
9:24
sur Jane et sur John parce qu'ils vont utiliser ce même prototype étudiant et il nous permettent de définir des
9:30
propriétés qui vont ensuite être disponibles au niveau de l'objet alors ce cette note on va le faire directement
9:36
au niveau de notre code on va faire un set notes et on va imaginer que John finalement il est plutôt régulier mais
9:43
il a 10 à chaque fois ce qui est pas terrible et à la limite à un moment donné bon il est chaud il a un œuf et
9:48
par contre Jane est un petit peu plus doué elle elle va avoir des notes qui vont être toujours des 15 VO des 18 et
9:55
un 19 elle a une jolie marge de progression voilà donc nos deux objets sont maintenant remplis avec des notes
10:01
on peut aussi utiliser les méthodes pour pouvoir effectuer des retours et avoir des informations sur nos étudiants par
10:08
exemple je peux avoir une méthode can pass qui nous dirait si l'étudiant a le
10:15
droit ou non de passer son année en regardant si la moyenne de ces notes est supérieure à 10 donc typiquement on a
10:23
besoin de calculer la moyenne c'est peut-être l'occasion de Ben recopier la fonction qu'on avait écrit dans les
10:28
exercices précédents dans chapitre précédent hop donc là moi je vais reprendre cette fonction
10:35
là je vais lui dire je vais calculer la moyenne donc de de cette personne là
10:41
pour obtenir ces notes mais je peux y accéder grâce à vis et maintenant je
10:46
peux faire un vis.nes et regarder si c'est supérieur ou égal à 10 et je vais return ça donc
10:54
dans mes étudiants je peux regarder à la fois si John et Jane il passent
11:01
voilà si je sauvegarde on on voit bien que John n'a pas le droit de passer son
11:06
année parce que il a pas eu des très bons résultats par contre Jane elleelle a le droit donc vous pouvez comme ça
11:12
créer tout un tas de méthodes que vous allez mettre sur votre prototype student et qui va ensuite être utilisable par
11:17
tous les objets alors maintenant il y a des méthodes que l'on peut définir qui vont être appelé automatiquement alors
11:23
je vais continuer avec mon système de notes et on s'imagine que plutôt que d'utiliser une méthode cette note on
11:29
envie de donner des notes aux étudiants de cette manière-là si je fais ça ça n'empêche pas du tout mon script de
11:35
s'exécuter c'est juste que là je définis moi-même les notes au niveau de John et donc c'est défini au niveau de cet objet
11:41
là et lorsque je fais un can pass c'est bien calculé le problème c'est que si j'essaie de faire par exemple quelque
11:48
chose et que je lui passe simplement une seule note ben ça fait planter mon script parce que lorsque j'essaie de calculer la moyenne je m'attends à avoir
11:55
un tableau j'aimerais bien pouvoir mettre en place des vérifications à ce niveau là donc vous avez la possibilité
12:01
de définir ce que l'on appelle les seturs et des getterurs donc les setteurs vont être automatiquement appelés lorsque vous définissez une
12:08
valeur typiquement ici ce que je peux faire c'est utiliser une méthode qui va
12:13
s'appeler notes cette méthode elle prendra en paramètre la valeur que moi je vais mettre par exemple ici ça sera
12:19
19 et ensuite elle peut faire un code particulier pour définir que cette méthode va être appelée lorsqu'on
12:26
utilisera cette notation on utilisera le mot-clé 7 et ensuite on mettra un petit
12:31
espace voyez que mon éditeur comprend bien les choses il met ce 7 en bleu un petit peu plus foncé et à ce niveau-là
12:38
je peux lui dire je veux faire un vis point note égal la valeur qui a été précisée moi j'aime bien mettre V comme
12:44
value si je mettais notes on s'y mélangerait un petit peu les pinceaux je trouve bon si je sauvegarde ça ne va
12:51
rien changer au problème ça va créer encore plus de problèmes d'ailleurs ça nous amène à une nouvelle erreur maximum
12:56
call stack size exceeded ce qui se passe c'est qu'ici quand vous faites un vis.notes il va essayer de réappeler le
13:03
setteur vu que dès qu'on essaie de définir une propriété qui s'appelle note il faut appeler ce setter et il s'appelle en boucle puis au bout d'un
13:09
moment il plante donc ça on peut pas l'appeler note donc nous on va l'appeler par exemple underscore notes si on
13:15
l'appelle de cette manière-là il faudra penser à ce niveau-là à l'appeler undersc notes si je sauvegarde
13:22
maintenant on me dit dans le cadre de Jane il y a un problème effectivement on n' plus accès à cette méthode cette note
13:30
mais à la place maintenant on peut utiliser un simple égal voilà l'avantage c'est que maintenant
13:37
qu'on a des méthodes on peut faire des vérifications et vérifier par exemple est-ce qu'on a un tableau pour vérifier
13:43
si quelque chose est bien un tableau on peut utiliser la méthode is array cette méthode est directement disponible sur
13:50
le gros objet global array donc moi je peux lui dire ici if
13:56
Eray isray V dans ce cas-là je remplis le tableau des notes pas de problème
14:03
dans le cas contraire je ne fais rien parce que j'estime que c'est une erreur histoire de ne pas avoir de problème dès
14:09
le début je vais définir les notes de l'élève comme un tableau vite voilà si
14:14
je rauvegarde et que je regarde maintenant à C à ce niveau-là on va considérer que notre premier utilisateur
14:21
John a une moyenne de zé parce qu'il n'a aucune note là on n pas réussi à lui définir des notes si je lui passe
14:28
quelque chose qui est bien tableau dans ce cas-là on voit qu'il a 19 de moyenne et on nous dit bien qu'il peut passer à
14:33
l'année suivante donc ça ce sont les sepurs on a la même chose pour les getterur qui permettent d'accéder à une
14:39
propriété imaginons qu'on aimerait bien que on ait un moyen magique d'obtenir le nom d'un utilisateur et que ça soit son
14:47
prénom suivi de son nom avec un espace bah on peut créer comme on l'a fait pour les notes un getter donc on peut faire
14:54
un get on mettra le nom de notre propriété magique par exemple ici nous ça va s'appeler name et ensuite ça sera
15:00
une fonction attention ici on ne mettra pas de paramètres parce que pour avoir accès à cette nouvelle propriété on
15:07
pourra simplement faire ici un john.name si je sauvegarde ça me renvoie
15:12
un defin parce qu'il n'y a pas de retour dans cette fonction et on a vu que s'il n'y a pas de retour ça r def donc ici je
15:19
peux faire return on va utiliser les bactic je mets d'abord le prénom de
15:24
l'utilisateur un petit espace et le nom de l'utilisateur
15:30
comme ça maintenant lorsque je lui demande est-ce que tu peux me donner le nom automatiquement il l'appellera cette
15:35
fonction là qui va récupérer les propriétés first name et last name et me les
15:40
afficher si on regarde notre objet John hop on voit bien que on a des propriétés
15:47
donc école first name last name et not et on nous montre name ici mais en
15:52
réalité hop il se situe dans le prototype parce que c'est lui qui définit la manière d'y accéder si on
15:58
fait la même chose avec Jane hop il nous montre que c'est un étudiant et il nous
16:03
montre que name est entre parenthèses parce que ben c'est seulement quand on clique dessus qu' va exécuter la
16:08
fonction pour nous le montrer voilà et c'est la même chose dans le prototype à ce niveau-là mais on remarque que on a
16:15
bien le Getter et le setter qui est affiché dans le prototype justement alors les méthodes on peut aussi
16:20
directement les définir sur notre objet student donc par exemple on peut se dire que on a besoin de la valeur
16:29
correspondant à la moyenne donc dans ce cas-là on peut écrire statique suivi d'une propriété par
16:36
exemple on va écrire moyenne et on peut mettre une valeur par exemple on mettra
16:42
10 si je regarde mon objet student maintenant donc l'objet qui contient le
16:47
prototype on voit pas grand-chose malheureusement mais si je fais student point moyenne ça va me donner 10 donc
16:56
avec le motcé statique on peut définir des choses qui ne seront pas dans le prototype des objets initialisés de
17:02
cette manière-là mais qui seront directement disponibles sur l'objet student en effet si je regarde par
17:09
exemple John ou Jane on voit que dans cette partie prototype bah il a aucun
17:14
endroit en voie moyenne voilà c'est juste une manière un petit peu plus simple d'écrire les choses on peut le
17:20
faire pour des valeurs mais on peut aussi le faire pour des méthode on peut avoir par exemple un statique hello qui
17:25
serait une fonction qui ferait un console. log bonjour et dans ce cas-là c'est
17:32
appelable directement sur l'objet student ça globalement ce n'est pas bien
17:38
compliqué ça équivaut à écrire les choses de cette manière-là comme si on écrivait student point hello é= une
17:45
fonction et de la même manière pour la moyenne ça équivaut à faire student. moyenne = 10 c'est intéressant d'avoir
17:53
ces mots- clés là parce que ça se rapproche des principes de programmation orientée objet qu'on peut connaître sur
17:58
sur d'autres langages de programmation donc ça évite d'avoir à faire trop de gymnastique si on passe d'un langage à
18:04
l'autre mais au niveau du principe ça revient vraiment au même donc là je vais remettre par exemple que la moyenne je
18:10
la sauvegarde comme une sorte de constante et ensuite ici plutôt que de lui dire il faut que ça soit supérieur à
18:15
10 je peux lui dire il faut que ça soit supérieur à student donc mon ma classe
18:20
Point moyenne ce qui est intéressant avec cette approche là c'est que vous pouvez facilement changer la valeur si vous
18:26
voulez que bah les étudiants au-delà de zé B il passe vous pouvez changer la valeur de moyenne plus plus facilement
18:32
c'est surtout intéressant si c'est utilisé dans différentes dans différentes méthodes donc quand on regarde la documentation justement de de
18:39
MDN ou n'importe quelle documentation on va avoir cette distinction qui va être faite par exemple la méthode is array
18:46
que l'on a évoqué où on voit ici la méthode from ou où je crois qu'il y a tout aussi ce sont des méthodes qui sont
18:53
directement disponibles au niveau de l'objet Ray lorsqu'on a besoin de les utiliser on fera ay point quelque chose
18:59
alors que les méthodes qui sont dans le prototype seront des méthodes qui vont être disponibles sur les tableaux d'ailleurs en programmation
19:06
orientée objet on va dire que John ou Jane ici ce sont des instances d'étudiants bien qu'en JavaScript ça va
19:14
pas forcément la même signification on a juste créé des objets qui ont comme prototype le prototype créé par student
19:21
mais en réalité vous pouvez imaginer ça comme une version d'un étudiant si ça vous aide au niveau du du concept alors
19:28
une dernière on va voir c'est justement comment on peut faire un prototype d'un prototype alors ça paraî compliqué mais
19:34
rassurez-vous c'est très simple on peut imaginer qu'on a une classe qu'on va appeler super
19:40
student et cette classe là on aimerait bien que son prototype à l'intérieur
19:46
soit student on peut l'écrire en faisant ext
19:52
student je peux alors préciser que John je peu importe va être un superstudent
19:58
et par défaut on va imaginer qu'il a des mauvaises notes on va imaginer qu'il a 0
20:05
10 et 8 voilà donc lorsque je regarde au niveau de ma console si je regarde à
20:12
quoi ressemble John on va voir cette chaîne de prototype on voit que ici notre élément a comme
20:18
prototype un superstudent qui lui-même a comme prototype student qui est lui-même
20:24
à comme prototype object donc ça veut dire que quand une méthode va être recherchée elle va être recherchée
20:29
d'abord dans Super student vu que j'en ai aucune ben il il va l'ignorer il va les chercher ensuite dans student donc
20:36
c'est ce qui lui permet d'accéder par exemple aux méthodes can pass ou autre et s'il les trouve il les appelle
20:42
l'avantage c'est que on peut comme ça garder le comportement pour tout le reste mais modifier certains
20:48
comportements par exemple on peut se dire ben là on va avoir une méthode canp et on imagine qu'un super étudiant même
20:54
si c'est pas forcément très régloot mais on a le droit de le faire passer d'une année à l'autre quoi qu'il arrive si je
21:01
réactualise la page je regarde maintenant John qui est mon élève qui est un petit peu pistonné ben mon élève
21:08
ici on voit que dans son prototype super student il a une méthode can pass et du coup si je l'appelle c'est celle-ci qui
21:15
sera appelée plutôt que celle dans la classe parente si je fais maintenant un John
21:20
point can passe on voit que ça me donne bien trou d'ailleurs on a aussi la
21:27
possibilité de utiliser les méthodes qui sont dans les prototypes supérieurs imaginons je définis ici get name et
21:35
j'aimerais bien réutiliser la logique que l'on avait ici mais rajouter devant super suivi du nom normal si je fais
21:43
juste un return de super si maintenant je regarde le nom de John ben malheureusement on va juste me donner
21:49
super si je veux appeler une méthode qui est disponible dans le prototype supérieur je peux utiliser le mot-cés
21:56
super pointn et ça me donnera la méthode parente et
22:01
je peux accéder comme ça à n'importe quelle propriété qui est un niveau au-dessus donc ça c'est pas mal si on ne
22:07
veut pas écraser la logique au niveau supérieur sur la méthode canp si je
22:12
voulais garder le comportement précédent je pourrais tout à fait lui dire je veux que tu appelles la méthode parente qui
22:18
va s'appeler can pass et du coup lorsque je vais demander est-ce que l'étudiant peut passer mais ça réutiliserait la
22:24
logique originale qui serait la logique des moyennes et effectivement on lui donne donne le droit de passer parce queon avait mis la moyenne à Z mais si
22:31
je remets la moyenne à 10 on voit que il n'a plus le droit de passer donc avec super on peut appeler une méthode du
22:38
prototype par an enfin une dernière petite chose sur ce super si vous l'appelez dans le constructeur par
22:44
exemple on s'imagine que le constructeur on a envie de le changer on a envie de lui dire bah tu peux prendre un prénom
22:51
toujours un nom mais je veux aussi que tu prennes des notes comme ça ça se fait
22:56
directement donc à ce niveau-là je n'ai pas envie de refaire ce que j'avais écrit ici donc je peux utiliser super et
23:04
directement l'utiliser sous forme de fonction et lui passer first name et last name vous vous imaginez que
23:11
finalement super c'est un peu l'équivalent de cette valeur là et après
23:17
je peux en profiter pour définir ma propriété note et la définir à partir de
23:22
ce qui a été renseigné par l'utilisateur donc maintenant si je reviens ici je vais directement finir
23:28
les notes de John en 3oème paramètre parce que je peux le faire grâce au fait qu'il soit un super students et si je
23:35
réactualise la page ça va toujours fonctionner j'auraai dans John les différentes propriétés à savoir first
23:41
name et last name mais aussi les notes qui vont être préenseignées enfin un dernier point vous avez la possibilité
23:47
d'avoir des variables internes comme je l'ai fait ici moi j'ai mis und note pour
23:52
me dire en fait c'est une variable qui sert à l'intérieur de la classe mais que je n'ai pas forcément l'intention de
23:58
regarder depuis l'extérieur parce que ce qui m'intéresse c'est de savoir s'il a le droit de passer ou non si une
24:04
variable ne doit pas être exposée à l'extérieur vous pouvez la définir avec un diè devant donc par exemple si je
24:11
fais ici un di secret et que je mets hello comme valeur si je regarde mes
24:18
différents objets si je regarde John par exemple et que je déplie je vois que
24:23
j'ai accès à secret dans la partie debug par contre si je fais un Jun point
24:28
dollar secret hop il me dit non tu n'as pas accès à cette propriété privée on ne
24:34
peut pas l'utiliser en dehors de de la classe donc dans le cadre de nos notes
24:39
c'est idéal je peux la définir comme ça j'ai le droit de modifier cette propriété directement dans la classe ça
24:46
ça ne lui pose aucun souci par contre je n'ai pas le droit de le faire en dehors je n'aurais pas accès aux notes en
24:52
dehors de mon système si ce n'est si je le choisis évidemment à travers des getterurs et des Setur comme je l'ai
24:57
fait ici par contre ça aura un petit effet de bord c'est que à ce niveau-là si
25:03
j'essaie de transformer vis di note on voit que mon éditeur va souligner ça en rouge en me disant non ce n'est pas
25:09
accessible je n'y ai accès que dans la le contexte de la classe student en dehors c'est interdit donc là ce qu'il
25:16
me faudrait faire c'est hop redéfinir la propriété comme un tableau vide et dans
25:22
ce cas-là il va me laisser y accéder donc si on regarde mon super étudiant si
25:27
je regarde jaune on voit bien que il a une propriété et qu'il a les différentes notes par contre on voit qu'il a deux
25:34
propriétés notes qui sont différentes parce que ça dépend du contexte dans lequel elles existent imaginons je crée
25:40
un getter ici je crée un getter note et là je fais un console. log de vis et je
25:48
récupère di note si je sauvegarde et que je regarde au niveau de John est-ce que
25:54
il a des notes on va me donner quoi on va me donner un tableau vide si par
26:00
contre je mets la même chose à ce niveau-là et que j'aurais essayé de
26:05
faire la même méthode on va me donner un tableau rempli parce que les propriétés privées elles dépendent du contexte dans
26:12
lequel elles sont appelées si je reprend mon système avec des undcore notes donc je remets undcore note un petit peu
26:19
partout voilà ici ici
26:26
ici là et normalement
26:33
là-haut si je regarde les notes de l'utilisateur ça fait 0 10 et 8 et si je
26:38
regarde les notes en enlevant ce getterter à ce niveau-là ça me donne aussi 0 10 et 8
26:47
parce que c'est directement la propriété de John qui va contenir l'information lorsqu'on définit des propriétés privées
26:54
elles sont limitées à la portée de votre de votre classe donc il faut ça savoir que cette notion de propriété privée
27:00
c'est quelque chose qui est relativement récent à l'échelle de vie du javascript donc de manière générale beaucoup de
27:05
développeurs vont avoir tendance à ne pas les utiliser pour l'instant et plutôt utiliser les undcore pour dire
27:11
que ce sont des variables qui sont internes sans forcément non plus qu'il y ait une vérification côté navigateur
27:17
c'est juste une convention qui permet de dire ok ça c'est interne et je n'ai pas vocation à les utiliser en dehors
27:24
l'avantage qu'apportent les propriétés privées avec le di c'est qu'on peut vraiment pas les appeler depuis l'extérieur et donc il y a une
27:31
vérification qui est faite au fonctionnement mais si vous voyez très peu dans dans du code que vous allez explorer de diè c'est tout à fait normal
27:38
c'est que c'est très récent et il y a des comportements qui peuvent être un petit peu handicapants comme celui que l'on vient de voir et c'est pour ça que
27:43
vous ne le verrez pas forcément partout donc voilà un petit peu pour ce chapitre là donc qu'est-ce qu'on doit retenir on
27:50
va retenir que toutes les tous les objets et tous les types en fait de base en Javascript vont fonctionner avec un
27:56
système de prototype lorsque lorsquon utilise une méthode ou lorsqu'on accède à une propriété on va regarder si cette
28:02
propriété existe sur l'objet courant et si ce n'est pas le cas on va regarder sur son prototype en remontant jusqu'à
28:08
arriver à l'objet qui n'aura plus de prototype si on le souhaite on peut créer nous-même nos propres prototype
28:14
grâce à le le motcés classe on met classe suivi du nom de notre prototype
28:19
et ensuite on peut définir des propriétés qui vont automatiquement être injectés dans nos objets et des méthodes
28:25
et surtout on peut définir un constructeur qui permet d'expliquer comment notre nouvel objet va être
28:31
initialisé en général dans ce constructeur on va faire ce que l'on appelle de l'initialisation c'est-à-dire
28:37
qu'on va définir des propriétés à partir des paramètres qui nous auront été envoyés ces propriétés vont être propres
28:43
à chaque instance c'est dire à chaque objet qui va utiliser ce prototype là
28:48
ensuite à l'intérieur on peut définir des méthodes et on peut aussi définir des seturs et des Gurs les seturs et les
28:54
Gurs permettent d'avoir une syntaxe qui va être un petit peu plus simple et plus naturel à écrire par la suite par
29:00
exemple ici ça nous permet de faire un jin.ne égal plutôt que de faire un jin.7 notes et d'avoir une méthode
29:07
particulière on a aussi la possibilité de définir des propriétés ou des méthodes comme statiques et dans ce
29:13
cas-là elles seront directement disponible sur l'objet qui sert de prototype plutôt que sur les différentes
29:20
instances et après on a vu le principe de l'héritage si on veut on peut avoir un prototype d'un prototype mais on peut
29:25
continuer on pourrait tout à fait avoir une classe qui extend de super student qui extende lui-même de Student et là on
29:31
peut définir bah de de nouvelles choses et modifier le comportement de cette certaines méthodes ou rajouter de
29:37
nouvelles méthodes par rapport à nos besoins donc ça c'est tout un plan du javascript qui nous permet de faire de
29:42
la programmation orientée objet c'est une manière d'organiser le code qui va permettre de représenter des notions
29:48
complexes sous forme d'objets qui vont être réutilisables ça va être très pratique et suivant les situations ça
29:54
peut être plus ou moins utile alors ce que je vous propose dans le chapitre suivant c'est de faire quelques exercices liés à la programmation
30:00
orientée objet pour vous mettre à l'aise un petit peu avec ces concepts là
 
 
 
 video 2

 0:00
Alors, bienvenue dans ce nouveau
0:01
chapitre où nous allons faire un petit
0:02
peu de TP pour bien être sûr que vous
0:05
ayez compris la syntaxe des classes et
0:06
même leur utilisation. Donc, on va
0:08
commencer par un premier exemple, c'est
0:10
qu'on travaille sur un site qui utilise
0:11
des formes géométriques et on a besoin
0:13
de faire différentes opérations dessus.
0:15
Donc ce que l'on va faire, c'est qu'on
0:16
va se créer des classes qui vont nous
0:18
permettre justement de créer ces
0:19
nouveaux types d'objets. Donc d'abord,
0:22
je vais vous demander de créer une
0:23
classe rectangle qui sera initialisé
0:25
avec une largeur et une hauteur. Sur
0:27
cette classe, on créera des getteurs
0:29
particuliers. On aura un getteur
0:30
périméteur qui permettra d'obtenir le
0:32
périmètre de notre rectangle. Donc pour
0:34
rappel, c'est deux fois la largeur plus
0:36
de fois la hauteur. Et on aura une
0:38
méthode is valide qui permettra de
0:39
savoir si notre forme géométrique est
0:42
valide. Typiquement ici, on va
0:43
initialiser un rectangle avec une valeur
0:45
négative et il faudra que Isvalide
0:47
renvoie false parce que une dimension ne
0:49
peut pas être négative. Ensuite, vous
0:52
allez faire le système d'héritage et
0:54
vous allez créer une autre classe qui va
0:55
s'appeler square qui permettra de
0:57
représenter un carré. Un carré au final,
0:59
c'est simplement un rectangle qui a à la
1:01
fois la même largeur et la même hauteur.
1:03
Donc vous allez utiliser le système
1:04
d'extend pour réutiliser ce que l'on a
1:07
déjà fait pour les rectangles. Enfin,
1:09
vous allez devoir créer une méthode is
1:11
bigger van.
1:13
Cette méthode sera disponible à la fois
1:14
sur les carrés et sur les rectangles. Et
1:16
l'objectif, c'est de vérifier si la
1:18
forme est plus grande ou plus petite.
1:20
Pour cela, on comparera tout simplement
1:22
les périmètres. Donc ici, j'ai mon carré
1:24
et j'aimerais regarder est-ce que mon
1:26
carré est plus grand que mon rectangle
1:27
que j'ai ici. Donc votre objectif, c'est
1:30
de créer les différentes méthodes, les
1:32
différents getur et les différentes
1:33
classes qui vont permettre à ce code de
1:35
fonctionner
1:38
convenablement. Donc maintenant, on va
1:40
corriger ça ensemble. Donc d'abord notre
1:42
système de rectangle. Donc je vais
1:43
commencer par créer une classe
1:45
rectangle. Et cette classe, je vais
1:47
ouvrir mon accolade et la fermer. Mon
1:50
rectangle, j'ai besoin de le construire
1:51
avec des paramètres. Donc ça veut dire
1:53
que j'ai besoin d'un constructeur. Donc
1:54
je vais taper
1:56
constructor et je vais avoir besoin de
1:58
deux paramètres, la largeur et la
2:00
hauteur. Donc à partir de maintenant, on
2:02
va prendre cette convention de tout
2:04
écrire en anglais. C'est en général ce
2:05
que vous allez faire lorsque vous allez
2:07
écrire du code professionnellement, mais
2:09
aussi lorsque vous allez lire du code.
2:10
Donc autant prendre l'habitude de le
2:11
faire de suite. La largeur c'est Width
2:14
et la hauteur
2:16
c'est ces propriétés je vais en avoir
2:18
besoin plus tard à la fois pour savoir
2:20
si euh c'est une forme valide mais aussi
2:22
pour connaître le périmètre. Donc j'ai
2:24
besoin de faire ce que l'on appelle une
2:25
initialisation.
2:27
C'est d'ailleurs très souvent ce que
2:28
vous allez faire de toute façon dans les
2:29
constructeurs, c'est initialiser les
2:31
propriétés au sein de l'objet histoire
2:34
de pouvoir les réutiliser plus tard.
2:36
Donc là, je fais un vis. É = width et
2:38
vis.8 = 8. Si je sauvegarde, on voit
2:42
qu'on a un petit peu moins d'erreur en
2:43
console et les trois premières
2:45
instructions s'affichent. Lorsque
2:47
j'essaie d'accéder au périmètre, il me
2:48
dit que c'est undefined parce que pour
2:50
l'instant bah on n pas cette propriété
2:52
périmètre sur notre objet. Donc il va
2:54
falloir la créer. Je vais créer un
2:56
getter. On va l'appeler périméter. Et ça
2:59
va être une fonction qui va renvoyer le
3:01
périmètre. On fera un return. On a
3:03
besoin d'accéder à la largeur. Donc on
3:05
fera
3:06
10.8 multiplié par 2 et ensuite on
3:09
ajoutera 10.8 multiplié par 2
3:13
aussi. Voilà. Donc là on voit que pour
3:15
notre rectangle qui a une longueur ou
3:18
une hauteur de 10 et une largeur de 20,
3:20
ça nous donne bien un périmètre de 60.
3:22
D'ailleurs, on pourrait peut-être
3:24
refactoriser ça en lui disant en fait,
3:26
on fait l'addition des deux valeurs et
3:28
c'est cette addition que l'on multiplie
3:29
par 2. Ça nous donne le même résultat.
3:32
Voilà. Donc ensuite, on a is valide.
3:34
Donc pareil, vu qu'on y accède comme une
3:36
simple propriété, c'est que l'on a
3:38
besoin d'utiliser un getter. Là, on va
3:41
retourner. Est-ce que vis. WiF est
3:44
supérieur à
3:45
0. On va dire strictement parce que une
3:48
forme géométrique qui a zéro, on va
3:49
considérer que elle n'existe pas. Donc
3:51
c'est pas possible. Et on veut aussi que
3:54
vis. Soit supérieur à 0. Donc je vais
3:58
sauvegarder et j'obtiens ici true et
4:00
false. Effectivement la première forme
4:02
est bien valide par contre la seconde
4:04
forme ne l'est pas. Donc là on a terminé
4:07
avec notre architecture des rectangles.
4:09
Alors maintenant on a besoin de créer
4:11
notre classe square qui va représenter
4:13
un carré. Donc classe square. Et cette
4:17
classe-là elle va avoir besoin des mêmes
4:19
propriétés finalement que notre
4:21
rectangle. Donc un carré, ce n'est ni
4:23
plus ni moins qu'un rectangle
4:24
particulier. Donc là, on est typiquement
4:26
dans une situation où on va pouvoir
4:28
utiliser le système d'héritage. Donc on
4:30
va lui dire que ça extense de rectangle
4:33
et on va changer le
4:35
constructeur. Ce constructeur, il
4:37
prendra qu'une dimension, on va
4:39
l'appeler Widf. Et ensuite, on doit
4:41
initialiser les propriétés. Donc ce que
4:44
l'on va faire ici, c'est qu'on va plutôt
4:45
appeler le constructeur parent grâce à
4:48
au mot clé super et on lui passera la
4:52
largeur mais on lui donnera aussi la
4:54
hauteur en réutilisant finalement la
4:56
même valeur. Donc comme ça en fait on
4:58
est en train si vous voulez de
5:00
construire un rectangle spécial et on
5:02
pourrait avoir des méthodes qui seraient
5:04
spécifiques au carré ou ne rien faire de
5:06
plus. Si je sauvegarde hop, on voit
5:09
qu'il y a une ligne de plus qui
5:10
s'affiche. C'est le périmètre de notre
5:12
carré qui est une taille de 10 et ça
5:14
nous donne bien 40. Donc le dernier
5:16
objectif, c'est de faire la méthode is
5:18
bigger van. Cette méthode, on peut la
5:20
mettre sur les carrés, mais on peut se
5:22
dire que finalement c'est quelque chose
5:24
qui fonctionne aussi sur les rectangles.
5:25
Donc là,
5:27
hop, on va se créer une méthode is
5:30
bigger van. C'est une méthode qui
5:32
prendra en paramètrre une forme. Donc,
5:34
on va dire que c'est shape. Là, vous
5:37
pouvez mettre le nom que vous voulez. Si
5:38
quelque chose vous va mieux, n'hésitez
5:40
pas à changer ça. Et on va retourner
5:42
ici. Est-ce que le périmètre de notre
5:45
objet, donc c'est le périmètre de
5:47
l'objet sur lequel on appelle la méthode
5:49
est plus grand que le périmètre qui est
5:51
passé en paramètres. Donc pour avoir le
5:53
périmètre de notre objet courant, on
5:55
fera vis. périmèteur et on va regarder
5:58
est-ce que c'est supérieur à shape, donc
6:00
ce qui est passant paramètre point
6:02
périmé. Et là effectivement ça nous
6:05
donnera un résultat. Donc notre
6:07
rectangle qui mesure 60 est plus grand
6:10
que notre carré. Donc lorsqu'on lui
6:11
demande est-ce que le carré est plus
6:13
grand que le rectangle, ça nous renvoie
6:14
bien false. Si on faisait les choses en
6:16
sens inverse, est-ce que le rectangle
6:18
est plus grand que le carré ? Ça nous
6:20
renverrait trou. Voilà. Et là bah vous
6:23
avez un exemple d'utilisation des
6:25
classes. Encore une fois, c'est un
6:28
exemple simple mais c'est en général pas
6:30
plus compliqué que ça. La principale
6:32
problématique que vous allez avoir avec
6:33
les classes et les objets, c'est de
6:34
savoir un petit peu comment découper les
6:36
choses. Typiquement dans le cadre de
6:38
forme géométrique, on pourrait même
6:40
avoir une classe d'un niveau supérieur
6:42
shape qui représente une forme de
6:44
manière générale où on mettrait des
6:45
méthodes qui concerneraient à la fois
6:48
les rectangles. Mais si plus tard on a
6:49
des formes comme des cercles ou autres,
6:51
ça serait englobé dans cette dans cette
6:53
cette chose là. Donc ça va dépendre
6:55
encore une fois des
6:57
situations. Alors maintenant, on va
6:58
commenter et on va passer à l'exercice
7:00
suivant. Comme d'habitude, les énoncés
7:02
de tous ces exercices sont disponibles
7:04
dans l'article. Donc n'hésitez pas à
7:06
copiercoller le code plutôt que voilà à
7:08
essayer de recopier ce que vous voyez à
7:10
l'écran. Alors pour ce second exercice,
7:12
on fait une petite mise en situation. On
7:14
va gérer en fait une librairie de livres
7:18
et on va avoir besoin de gérer ça avec
7:20
des objets encore une fois. Donc on va
7:22
avoir besoin de deux classes. Une
7:24
première classe qui va permettre de
7:25
représenter un livre. Ce livre sera
7:27
construit à partir de deux informations.
7:29
Le titre et ensuite le nombre de pages
7:32
qu'il y a dans le livre. On aura ensuite
7:34
la possibilité de récupérer la page sur
7:36
laquelle on est actuellement. Donc par
7:38
défaut, un livre commencera à la page
7:40
numéro 1. On aura une méthode next page
7:42
qui permettra de tourner la page et
7:44
d'aller à la page suivante. Donc dans ce
7:45
cas-là, lorsque l'on log, on devrait
7:47
être à la page numéro 2. On aura une
7:50
méthode close qui permettra de fermer le
7:51
livre, donc globalement de réinitialiser
7:53
la page et de revenir à 1. Donc nos
7:57
livres, ben vont être un petit peu
7:58
construits de cette manière-là, mais on
7:59
a besoin de les organiser. Donc on va
8:01
créer une autre classe qui va s'appeler
8:02
library qui va permettre de ranger nos
8:04
livres. Cette classe aura trois
8:07
méthodes. Une première qui va s'appeler
8:09
Adbook qui permettra de rajouter un seul
8:10
livre. Une méthode AdBooks qui permettra
8:13
de prendre en paramètre un tableau de
8:15
livres et qui rajoutera tous les livres
8:17
à notre à notre librairie. Et enfin, on
8:20
aura une méthode Find Books by Letter
8:23
qui prendra paramètre une lettre et qui
8:25
trouvera tous les livres qui commencent
8:26
par cette lettre là. Donc dans notre cas
8:29
ici, c'est censé trouver le seigneur des
8:30
anneaux et sillage vu qu'on les a tous
8:32
les deux rajoutés à notre librairie. Je
8:35
vous ai donné un petit indice mais vous
8:37
n'êtes pas forcément obligé de le
8:38
respecter si vous trouvez une autre
8:39
manière de faire les choses. C'est
8:41
l'utilisation de la méthode filter pour
8:43
filtrer dans un tableau. Donc je vous
8:45
laisse essayer de le faire et encore une
8:47
fois on corriger ensemble juste
8:49
après. Alors au début c'est toujours
8:52
très simple. On crée une classe. Voilà,
8:55
on met le nom de notre classe. Ensuite,
8:57
on sait comment c'est construit parce
8:59
que je vous l'ai dit. Et on va mettre à
9:01
l'intérieur donc le title et le nombre
9:04
de pages. Ces propriétés tout de suite
9:06
on les initialise en faisant vis.title
9:09
égal title et en faisant vis. Page égal
9:11
page. Donc ça c'est un petit peu
9:14
classique. Maintenant on a parlé de la
9:17
possibilité de mémoriser la page sur
9:19
laquelle on est. Donc c'est ça qui est
9:20
un peu particulier par rapport à tout à
9:21
l'heure. Donc on va créer dès le
9:23
constructeur une nouvelle propriété page
9:26
et on va lui donner comme valeur 1.
9:28
Maintenant si je regarde dans mon
9:30
console.log, le premier fonctionne et me
9:32
donne bien 1. Donc là je me dis que je
9:34
n'ai peut-être même pas besoin de getter
9:36
à ce niveau-là. Le seul avantage
9:37
qu'offrent les getters, c'est qu'ils
9:38
permettent d'empêcher le setter. Par
9:40
exemple, un utilisateur ne pourrait pas
9:42
faire B point page = 5 ou égal une
9:45
valeur si on utilisait euh le système de
9:47
getters. Donc c'est pour ça que ça peut
9:49
être intéressant. Donc là, c'est un cas
9:51
d'utilisation pour les propriétés
9:53
privées. Donc on va plutôt dire que page
9:55
est une propriété privée. On peut
9:57
l'initialiser dès le constructeur ou on
9:59
peut l'initialiser en dehors de cette
10:01
manière-là. Ça revient absolument à la
10:04
même chose. Moi, j'aime bien cette
10:05
syntaxe là. C'est un petit peu plus
10:08
clair. Donc on a besoin maintenant du
10:10
getter page justement. Donc on va créer
10:12
un getter page qui fera un return de
10:15
vis. test page. J'ai le droit de le
10:17
faire parce que je suis dans la classe
10:18
donc j'ai le droit d'accéder aux
10:20
propriétés qui sont privées et j'obtiens
10:22
bien ici 1. Maintenant on va avoir
10:24
besoin de tourner la page. Donc on va
10:27
créer une méthode next page qui va se
10:29
charger d'incrémenter le numéro de page.
10:32
Il y a peut-être un détail à prendre en
10:33
compte c'est que si on est sur la
10:35
dernière page bah il ne faudra pas
10:36
tourner la page. Donc on va lui dire ici
10:39
if vis.
10:43
est inférieur strictement au nombre de
10:46
pages. Donc on y accède en faisant vis.
10:49
Page avec un s. Dans ce cas-là, je vais
10:52
faire
10:53
vis. Et l'incrémenter. On pourra
10:55
utiliser la syntaxe courte plus.
10:59
Je vais sauvegarder. On voit bien qu'ici
11:01
je suis sur la page numéro 1. Je fais la
11:03
méthode next page et je suis sur la page
11:06
numéro 2. Maintenant, j'ai besoin
11:08
d'implémenter la méthode close. Cette
11:09
méthode, elle va se charger de
11:11
réinitialiser la page. Donc là, je vais
11:13
faire un vis. Page = 1. On va remettre
11:17
la valeur initiale. Impeccable. Donc là,
11:20
on a géré le système qui fonctionne pour
11:22
les livres et on a besoin de gérer la
11:25
bibliothèque. Donc, on voit que c'est un
11:27
objet qui est construit à partir de
11:28
rien. Donc, on a'ura pas besoin de
11:30
constructeur à ce niveau-là. Donc, je
11:31
vais créer ma classe library. Et cette
11:35
classe là, elle va avoir trois méthodes.
11:38
Add book qui prendra en paramètre un
11:40
livre, une méthode Ad books qui
11:43
permettra de rajouter plusieurs livres.
11:46
Donc là, on mettra
11:47
books. Et enfin, hop, une dernière
11:50
méthode qui va
11:53
s'appeler find books by letter et on lui
11:56
passera en paramètrre une
11:58
lettre. Voilà. Donc, je note déjà toutes
12:01
les méthodes comme ça, je suis bien
12:03
organisé et au moins je peux travailler
12:05
ensuite sur la logique. Vous avez ici
12:08
deux possibilités. La première
12:09
possibilité serait de se dire dans la
12:11
librairie, je vais créer une propriété
12:14
que je vais appeler books et cette
12:16
propriété sera un objet vide. Et on
12:19
pourra s'imaginer par exemple créer un
12:21
objet qui aura comme clé une lettre et
12:24
ensuite les différents livres à
12:25
l'intérieur comme ceci. Et on aurait les
12:28
informations organisées de cette
12:30
manière-là. On peut se dire que c'est
12:32
une bonne idée parce que finalement on
12:34
va avoir besoin ensuite de les récupérer
12:35
par lettre. Cependant, peut-être que
12:38
dans notre librairie, plus tard, on aura
12:40
besoin de les récupérer par date ou ou
12:41
d'une autre manière. Donc, le plus
12:43
simple serait de sauvegarder les livres
12:45
à l'intérieur sous forme de tableau. On
12:48
va mettre tous les livres au même niveau
12:50
et ensuite on utilisera une fonction
12:51
pour parcourir le tableau et n'extraire
12:53
que les livres qui nous
12:55
intéressent. Cette propriété, on aura
12:57
pas besoin d'y accéder depuis
12:58
l'extérieur. Donc, on prend ce réflexe
13:00
de la mettre en privé pour l'instant.
13:02
Alors, quand on souhaite rajouter un
13:04
livre, ben on va utiliser la méthode
13:06
push pour pousser un nouvel élément dans
13:08
ce tableau là. Donc là, ça se fait très
13:10
simplement. On fait
13:13
vis.dooks pointpush et on pousse un
13:16
nouveau
13:17
livre. La méthode push modifie le
13:19
tableau sur lequel onappelle. Donc ça
13:21
modifié automatiquement books. Au niveau
13:24
de l'ajout de plusieurs livres, ben là
13:26
il va falloir faire une petite boucle
13:27
pour parcourir tous les livres et les
13:29
envoyer dans notre librairie. Donc on va
13:31
utiliser ici la boucle for off. Donc on
13:34
fera un for let book of books et on
13:38
utilisera la méthode push où ce que l'on
13:40
peut faire c'est utiliser les méthodes
13:41
que l'on a déjà créé et lui dire ben je
13:43
veux que tu rajoutes individuellement
13:46
chaque livre. Voilà, maintenant on va
13:49
avoir besoin d'implémenter la dernière
13:50
méthode qui va nous permettre de trouver
13:51
les livres qui commencent par la lettre
13:53
en question. Alors là, on a plusieurs
13:56
manières de faire les choses. La
13:57
première, c'est la manière plutôt
13:59
traditionnelle. On va créer un tableau
14:01
qu'on va appeler fond qui sera un
14:04
tableau contenant les livres que l'on a
14:06
trouvé. On va parcourir l'ensemble des
14:08
livres que l'on a dans notre librairie.
14:11
Donc, on fera un for let book of vis.d
14:16
diz
14:17
books. Et ensuite à ce niveau-là, on va
14:20
regarder est-ce que le livre
14:21
correspond. Donc la lettre, on va la
14:23
mettre en minuscule et on comparera à la
14:25
première lettre de notre titre en
14:28
minuscule. Donc on pourra faire ici une
14:30
condition en lui disant if
14:34
booktitle, on récupère l'élément à
14:36
l'index 0.2
14:38
tout lower
14:40
case est égal à la lettre qu'on va aussi
14:45
mettre en lower case. Voilà, comme ça,
14:47
ça nous permet de comparer sans prendre
14:49
en compte la casse, les majuscules, les
14:51
minuscules. Si c'est identique, dans ce
14:53
cas-là, on peut pousser dans notre
14:56
tableau d'éléments trouvés notre livre.
14:59
Et enfin, on peut faire un return et lui
15:02
dire voilà les différents livres que
15:04
j'ai trouvé. Alors, j'avais oublié de
15:06
faire un petit console. ici. Donc on va
15:09
le rajouter mais je vous le mettrai dans
15:11
dans l'énoncé directement. Et on voit
15:13
que il trouve deux livres. Si je lui
15:15
demande est-ce que tu peux me trouver
15:16
les livres qui commencent par Z, il m'en
15:18
trouve aucun. S minuscule, il m'en
15:21
trouve toujours deux. O, il m'en trouve
15:22
un et ainsi de suite, ainsi de suite. Et
15:24
là, bah vous avez un exemple
15:26
d'utilisation et
15:28
d'organisation. Alors, on va parler de
15:30
quelques petits points d'optimisation.
15:32
Donc d'abord pour cette boucle là, il y
15:34
a une autre manière de faire les choses,
15:36
c'est la méthode filter dont je vous ai
15:38
parlé dans le commentaire ici. Donc on
15:41
va chercher un petit peu des
15:42
informations sur cette méthode là. Donc
15:44
on va faire filter
15:47
NDN. Donc c'est une méthode qui est
15:49
disponible sur les tableaux vu que c'est
15:50
dans le point prototype et ça crée une
15:53
shallow copie. Donc vous pouvez voir un
15:55
petit peu de quoi il a retourne.
15:56
N'hésitez pas à mettre en français si ça
15:58
vous va mieux. Mais globalement ça crée
16:00
une copie du tableau et ça crée une
16:02
copie en utilisant une fonction qui va
16:04
permettre de filtrer les éléments. Si
16:06
cette fonction renvoie true, l'élément
16:08
est conservé. Si cette fonction renvoie
16:10
false, l'élément n'est pas
16:12
conservé. Donc à ce niveau-là, on
16:14
pourrait écrire les choses différemment
16:16
en utilisant vis.dooks
16:19
Books pointfilter et on lui passera en
16:22
paramètre une fonction qui prendra en
16:24
paramètre le livre. On va utiliser une
16:26
fonction fléchée parce que c'est plus
16:28
court ici. Et on va lui dire de
16:30
retourner. Donc quand est-ce qu'on garde
16:32
la valeur ? Quand le
16:36
book.title0. Est
16:38
égal à letter. Too lower case aussi.
16:42
Et vu que c'est une fonction qui
16:44
retourne directement qu'une seule chose,
16:46
on pourrait s'abstenir de mettre la
16:48
collade ici et tout mettre sur une seule
16:50
ligne. Parce qu'on l'avait vu hein, ça
16:52
renvoie directement. Voilà, si je fais
16:55
ça et que je regarde mon
16:57
document, il me le dit undefined parce
16:59
que j'ai oublié le return mais on
17:01
obtient bien un tableau vide dans le
17:03
cadre de Z. Mais si je retape S, j'ai
17:05
bien mes deux livres. Donc c'est une
17:07
manière un petit peu raccourcie d'écrire
17:09
les choses. Et vous avez encore une fois
17:11
un petit exemple d'utilisation des
17:13
classes. Donc le plus compliqué avec les
17:15
classes, c'est de trouver une bonne
17:16
organisation au final. C'est-à-dire que
17:18
lorsque vous allez avoir un exercice ou
17:20
quelque chose à faire, ben il faudra
17:22
savoir comment vous allez décomposer
17:23
votre code. Est-ce que vous avez
17:25
réellement besoin des classes ? C'est
17:27
vraiment ça qui est le plus compliqué.
17:28
C'est pas forcément leur utilisation
17:29
parce que vous voyez c'est finalement
17:31
plutôt naturel.
17:33
Alors, je voulais vous parler d'un petit
17:34
détail sur cette partie AdBooks. Donc,
17:38
on a une méthode sur les tableaux qui
17:40
est la méthode for each qui pourrait
17:42
nous permettre de simplifier un petit
17:44
peu notre code. Elle est disponible ici.
17:47
C'est une méthode qui prendra par mettre
17:49
une fonction et cette fonction sera
17:50
appelée pour tous les éléments. Donc, on
17:52
pourrait créer notre boucle ici
17:54
différemment en lui disant je vais faire
17:57
un books pointfor. Donc ça me permettra
18:00
de parcourir chaque livre. Et pour
18:02
chaque livre, je vais faire un vis. Add
18:06
book et je vais lui passer le livre en
18:09
question. Là, j'utilise un return, même
18:11
s'il n'est pas utilisé, ça n'a pas
18:13
d'importance. Si je supprime, ça
18:16
équivaut à la même chose que la boucle
18:18
que l'on avait vu. Et dans mon document,
18:20
ça ne change rien. Mais on pourrait se
18:22
dire, c'est un petit peu dommage là de
18:24
faire cette fonction là. Pourquoi tu ne
18:26
lui passes pas
18:27
directement notre fonction ? Et ça
18:30
aurait bah le même résultat parce que
18:32
finalement ça va appeler cette fonction
18:33
là en lui passant le paramètre livre.
18:36
Pourtant si je sauvegarde, je vais
18:37
tomber sur une erreur. On va me dire
18:39
cannot read property of undefined
18:41
reading DS books. Et c'est une erreur
18:43
qu'on a à la ligne 40. Et ici on a ce
18:47
que l'on appelle la stack trace. Ça nous
18:48
explique comment cette erreur est
18:50
survenue. Elle survient dans cette ligne
18:52
là parce qu'elle est appelée par un for
18:54
each qui est appelé par AdBooks à la
18:56
ligne 44. Et c'est comme ça qu'on peut
18:58
explorer un petit peu le déroulement du
19:00
code. Et c'est finalement la ligne 62
19:02
qui est le réel origine du problème.
19:04
C'est cette ligne là qui a déclenché
19:07
l'appel à cette fonction là qui appelé
19:10
qui a déclenché l'appel à cette fonction
19:11
là qui a l'erreur. Ça rejoint ce que je
19:13
vous avais évoqué avec les vis.
19:15
Lorsqu'on utilise For each et certaines
19:17
méthodes qui sont disponibles au niveau
19:18
du JavaScript, lorsque la méthode va
19:20
être appelée, elle va être appelée avec
19:23
un vis qui sera défini comme undefined.
19:26
Donc ça veut dire que dans cette méthode
19:27
là, vis ne sera pas ne fera pas
19:29
référence à l'objet comme on pourrait
19:30
l'attendre mais fera référence
19:32
finalement à rien du tout. Et lorsqu'il
19:34
essaie d'appeler vis.dook
19:36
Book, ben ça fait rien du tout point
19:38
quelque chose et donc il a il obtient
19:40
une erreur. Donc c'est ce que l'on voit
19:42
un petit peu dans la partie syntaxe. Le
19:44
forage peut prendre en second paramètre
19:46
ce qui va être utilisé comme vis. Donc
19:48
là dans cette situation, on serait
19:51
obligé de lui passer deux paramètres et
19:53
notre code se remettrait à fonctionner.
19:55
Donc lorsque vous passez des méthodes
19:57
directement à d'autres fonctions, il
19:58
faudra faire attention que ces fonctions
20:00
ne modifient pas vis, sinon on peut
20:02
avoir des des petites surprise. On n'
20:04
pas eu le problème tout à l'heure quand
20:05
j'ai écrit les choses de cette
20:06
manière-là. Hop, en faisant
20:10
vis. Pour la bonne et simple raison que
20:12
je vous l'avais dit, quand on utilise
20:14
une fonction fléchée, à l'intérieur de
20:15
la fonction fléchée, Visifiée et du coup
20:19
vis fait référence à ce que l'on a dans
20:21
cette fonction là. Et c'est pour ça
20:22
qu'on avait aucun problème. Dès qu'on a
20:24
enlevé cette fonction fléchée, ben le
20:26
vis a pu être modifié et on a pu
20:28
rencontrer des problèmes. Donc faites
20:30
attention à ça. Si jamais vous obtenez
20:31
ce genre d'erreur alors que vous dites
20:32
"Mais mon code est censé fonctionner,
20:34
c'est parce que vous avez le vis qui a
20:36
été modifié par une fonction." On aura
20:38
l'occasion de refaire des exemples où ça
20:40
arrive un petit peu plus tard. Vous
20:42
inquiétez pas. Si cette partie-là vous a
20:44
perdu, ce n'est pas bien grave. Si vous
20:46
avez utilisé la boucle for off, ça
20:48
revient à la même chose. Si c'est plus
20:49
clair pour vous, n'allez pas trop vous
20:51
prendre la tête avec ce genre de
20:52
syntaxe. C'est justement l'intérêt
20:53
d'avoir plusieurs approches, bah c'est
20:55
que vous pouvez choisir l'approche qui
20:56
vous va le mieux en terme de syntaxe.
20:59
Donc j'espère que ces deux petites épé
21:00
vous auront permis d'asseoir un petit
21:02
peu vos compétences. J'essaierai de
21:04
rajouter dans l'article de d'autres
21:05
d'autres petits exercices si vous voulez
21:07
continuer à pratiquer et que vous n'avez
21:09
pas été à l'aise avec les exercices que
21:10
l'on a fait jusqu'à maintenant. Et
21:12
sinon, ben je vous donne rendez-vous
21:13
dans les chapitres suivants.
