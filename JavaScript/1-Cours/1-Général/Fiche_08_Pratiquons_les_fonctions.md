# Apprendre le JavaScript : Pratiquons les fonctions

Video : https://www.youtube.com/watch?v=2HAPViIAYjc

## Transcription

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
