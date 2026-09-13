# JavaScript cote navigateur : Pratiquons avec une To-Do List

Video : https://www.youtube.com/watch?v=55EXq7ZjL4Q

## Transcription

0:00
bienvenue dans ce nouveau chapitre où
0:01
nous allons maintenant parler du
0:02
javascript côté client côté navigateur
0:04
donc on va pouvoir utiliser tout ce que
0:07
l'on a vu jusqu'à maintenant pour
0:08
pouvoir interagir avec la page et faire
0:09
des modifications donc il faut savoir
0:11
que les navigateurs modernes enfin Fox
0:14
Chrome et Safari dispose en noeud d'un
0:17
moteur de JavaScript

[ERREUR HUMAINE DE COPIE - CE BLOC N'EST PAS LE BON, VOIR CI-DESSOUS LE VRAI CONTENU]

bienvenue dans ce nouveau chapitre aujourd'hui je vous propose encore une fois de pratiquer un petit peu à travers un exemple concret c'est important de
0:06
pratiquer pratiquer pratiquer pour bien comprendre les choses et on va créer un exemple qui est assez classique lorsqu'on fait du javascript c'est la to
0:12
do list donc notre objectif ça va d'abord être de créer quelque chose qui va ressembler à ça avec les to do listes
0:18
qui vont être chargés depuis un serveur en utilisant encore une fois JSON play solder pour ça une fois que les to do
0:24
listes sont chargés on aura la possibilité aussi d'en rajouter par exemple on pourra ajouter un élément et
0:29
dès que j'appuie sur Entrée ou lorsque je soumets le formulaire automatiquement l'élément va être rajouté une fois qu'il
0:35
est ajouté on a la possibilité de cocher ou des cocher la case et d'utiliser des filtres pour ne voir que les éléments à
0:40
faire ou les éléments qui sont déjà fait et enfin on aura la possibilité de supprimer un élément de notre liste avec
0:46
cette petite corbeille je vous donne déjà la structure HTML et le CSS qui permet d'avoir cette page là et votre
0:53
rôle c'est de rajouter le javascript qui permet à tout ça de fonctionner alors pour vous donner peut-être une
0:59
piste moi je vous conseille d'utiliser des classes pour représenter votre structure deux classes qui peuvent être utiles ça serait une classe to do list
1:06
pour représenter une autre todolist dans sa globalité et une classe peut être tout douce item pour représenter un
1:11
élément dans cette liste là et rajouter les comportements qui peuvent être intéressants dessus après je vous donne
1:17
pas plus de pistes que ça chacun va essayer de le faire à sa façon et je vous proposerai une correction après comme d'habitude ce que je voulais vous
1:24
proposer ce n'est pas forcément la solution optimale ni il a la solution à utiliser c'est une solution parmi tant
1:29
d'autres donc si vous êtes arrivés à votre solution avec un moyen différent il n'y a pas de problème c'est une bonne
1:34
chose je vous laisse essayer de pratiquer encore une chance suite ensemble
1:41
alors je vais commencer comme d'habitude par importer notre JavaScript donc on va recréer une balise écrite on va lui
1:47
préciser que le fichier s'appellera app.js et on va préciser que ça va être quelque chose de type module et on
1:53
rajoute le défaire même si il ne sert à rien je vais ensuite aller créer ce fichier app.js à ce niveau là et on va
2:00
commencer par la première partie le chargement des différents éléments dans notre to do list donc à ce niveau là je
2:06
vais contacter le serveur et récupérer les informations si vous voulez vous pouvez réutiliser le code que vous aviez
2:12
déjà écrit dans les chapitres précédents pour contacter un serveur avec du gyson nous on va réécrire ce code ici je
2:19
trouve que c'est intéressant de retra pratiquer à chaque fois et on va donc se mettre ça dans un fichier api.js donc on
2:25
va mettre dans ce fichier tout ce qui concerne les API et qui nous permet de communiquer avec plus facilement
2:31
on va se créer une nouvelle fonction que l'on va appeler faits JSON qui va permettre de récupérer un gyson et qui
2:37
prendra un paramètre une URL et un second paramètre les options qui par défaut seront vides
2:42
donc nous ce que l'on commence par faire c'est modifier le header donc je vais créer un header je vais peut-être
2:48
effacer ça pour gagner un petit peu de place et resserrer ça pour gagner encore plus de place donc dans le header je
2:55
vais lui dire de prendre d'abord les options que l'on aurait déjà envoyé
3:00
donc c'est avec un S ici voilà et de rajouter aussi un et d'heures pour
3:05
accepter le gysom donc je vais lui dire peut-être même en amont je veux un accepte et on mettra application slash
3:14
JSON donc ça c'est quelque chose d'assezone donc on va déclarer notre fonction asynchrone et on va aussi en
3:20
profiter pour l'exporter maintenant je vais pouvoir lui dire de faire un fech donc je vais récupérer la réponse en
3:27
faisant awate de fetch je vais lui passer l'URL et je vais lui passer ensuite les options auxquels je rajoute
3:34
mes en-têtes maintenant je regarde est-ce que la réponse est ok si la réponse est ok on
3:42
peut faire un return et par c'est ça sous forme de GSM si la réponse n'est pas ok on peut renvoyer une nouvelle
3:49
erreur en mettant impossible de contacter le serveur ou plutôt
3:54
erreur serveur parce que là c'est clairement le serveur qui nous répond incorrectement et on rajoute dans la
3:59
cause l'erreur originale donc nous je me dis que ça serait bien d'avoir directement la réponse dans la partie
4:05
dans la partie cosse voilà donc maintenant dans mon app.js je vais pouvoir utiliser un top level wait pour
4:12
lui demander de charger les tout doux donc on va faire un wait et on va utiliser fetch jisson
4:19
on va penser ici à rajouter l'extension.js parce qu'il ne le fait pas automatiquement et je vais lui
4:24
demander de contacter cette url là au niveau des options je ne vais rien préciser de plus je veux juste les
4:31
options de base donc une méthode GET tout ça tout ça et ça ça va me permettre du coup d'obtenir les différentes to do
4:37
donc on va le sauvegarder à ce niveau là ensuite on va faire une console poids
4:43
log pour voir déjà si on est sur la bonne piste et si on obtient bien le résultat donc je sauvegarde ça je me
4:48
rends dans ma console et j'ai bien mes tout doux imaginons par contre que je me trompe et que le nom de domaine ne correspond pas il va me falloir capturer
4:55
cette erreur là et afficher un message au niveau de l'utilisateur donc dans le cadre du CSS que j'ai importé c'est
5:01
bootstrap on peut utiliser des alertes qui ressemblent à ça ça va être un petit peu plus joli que simplement mettre un message en rouge donc là on va entourer
5:08
notre code d'un try catch pour capturer l'erreur dans notre cash on se fiche un petit peu de la cause de l'erreur tout
5:15
ce qu'on sait c'est que finalement on ne peut pas charger les différents éléments dans notre to do list donc on se contentera simplement ici d'afficher un
5:21
message en disant impossible de charger les éléments donc on va devoir créer une div donc on fera un document Creed
5:29
Télément ensuite on va devoir lui donner des classes et on va aussi devoir lui donner un rôle alors je me dis que ça
5:36
c'est un petit peu pénible on le voit c'est quelque chose qu'on va avoir besoin de faire très très souvent de créer un élément HTML avec des attributs
5:42
mais la structure par défaut elle est pas forcément terrible parce qu'on est obligé de décrire une ligne avec
5:47
l'élément ensuite on est obligé de 7 des attributs les uns derrière les autres bon je sais pas ce que vous en pensez
5:54
mais je trouve que c'est pas super pratique parce qu'on se retrouve souvent avec 4 ou 5 lignes pour créer juste un
5:59
élément peut-être une méthode un petit peu plus pratique serait d'avoir une sorte de cruauté élément
6:10
[Musique]
6:51
j'en profite pour ajouter un petit peu de documentation donc je vais préciser que le tag name sera une chaîne de caractère et la tribu ça sera tout
6:59
simplement un objet peut-être on peut même préciser que c'est un objet vide par défaut au niveau du retour que l'on
7:05
aura le retour de cette fonction là ça sera un HTML et les maths
7:10
donc au niveau de ma fonction cruauté les ment je vais commencer par créer l'élément en faisant un document point
7:16
cruauté les mains et je vais créer le tag name maintenant je vais avoir besoin de
7:22
récupérer les clés et les valeurs de cet attribut donc on peut utiliser pour cela la fonction intrise au niveau des objets
7:29
donc si vous cherchez un trise on l'avait vu brièvement lorsqu'on avait parcouru un petit peu les fonctions mais
7:35
ça permet facilement d'itérer à la fois sur les clés et les valeurs d'un objet donc à ce niveau là on peut lui dire
7:41
fort on va utiliser une constante ça va être un tableau de taille 2 et en extra
7:47
la clé donc nous on va appeler ça la tribu et un extrait aussi la valeur et
7:53
on fera off object pointes et on lui donnera notre objet d'attribut donc ça
8:00
c'est une boucle que vous allez assez fréquemment utilisée lorsque vous avez besoin de parcourir un objet de clé valeur
8:06
maintenant il me faut faire simplement un élément.7 attribute et je lui donne un premier paramètre le nom de la tribu
8:12
et en second paramètre la valeur associée une fois que cet élément est créé je peux le retourner voilà donc si
8:20
je reviens maintenant au niveau de mon app.js je peux lui demander d'importer le cruauté et les ment donc je peux
8:26
réécrire critiquer les ment voilà pour le forcer à importer ça et à ce niveau là maintenant je vais récupérer ma div
8:34
cette diva à l'intérieur je vais y mettre mon texte donc je vais faire un immortex et mettre impossible de charger
8:41
les éléments ce que vous pouvez aussi faire c'est
8:47
modifier votre fonction cruauté élément si vous voulez lui passer un paramètre supplémentaire pour faire un inertex moi
8:52
je me dis que là ça me gêne pas d'avoir une ligne en plus à ce niveau là et après on va rajouter ça au niveau de mon
8:58
body donc je vais faire un document de point maudit point append et rajouter Madi peut-être cette dive là je vais la
9:04
nommer alerte et les menthe voilà pour avoir une un nom de variable qui est
9:10
plus clair quand on le relieve c'est un peu trop générique à mon sens donc si je reviens au niveau de ma page ici et que
9:16
je réactualise on va voir en bas qu'on a notre petit alerte alors peut-être nous
9:21
ça serait plus judicieux effectivement de la mettre en amont pour qu'il y ait un petit peu d'espace
9:27
on va rajouter ici au niveau de la classe un peu de marge autour et voilà donc là on a comme ça ce système là qui
9:34
nous permettra d'afficher une alerte pour indiquer que il y a un problème donc dans le cas contraire on est ici on
9:40
a pas de problème on peut continuer donc notre objectif ça va être de construire cette structure là donc au niveau de mon
9:47
HTML hop hop dans ma liste je vais temporairement commenter cette partie là je vais la garder parce que je vais
9:53
avoir besoin de la structure HTML d'un élément et ensuite on va supprimer le reste voilà
10:00
maintenant notre objectif c'est de créer le code qui va venir remplir tout ça et comme je vous l'ai dit on va utiliser des classes pour mieux organiser notre
10:07
code alors finalement on aimerait bien créer une sorte de composants qui va représenter une to-do list donc je vais
10:12
aller créer un nouveau dossier je vais pas mettre ça dans function parce que ça pas des fonctions mais je vais créer un nouveau dossier component et dedans je
10:19
vais créer un fichier que je vais appeler tout doux list.js alors je mets ça moi en majuscule c'est une convention
10:26
personnelle parce que ma classe va s'appeler to do list dedans je vais exporter ma classe tout doux list
10:33
l'objectif de cette classe ça va être d'être construite avec des éléments donc on va lui dire je vais te construire en
10:40
te passant des tout doux donc c'est l'ensemble des tâches que l'on va avoir besoin de faire ensuite je me dis ce
10:46
serait intéressant d'avoir une méthode à peine tout qui permet d'indiquer à quel élément on souhaiter les notre to do
10:53
list et là on lui dirait j'ai envie d'ajouter ça à notre notre div ici
10:58
donc là ça prendra un paramètre un élément et ça ferait la logique pour ajouter notre to do list à cet élément
11:04
là et enfin dernier petit reflexe lorsque j'utilise le constructeur je vais commencer par initialiser les
11:10
propriétés et là on va s'imaginer que c'est une propriété pour l'instant qui est privée parce qu'on en aura pas
11:15
besoin depuis l'extérieur donc au niveau de mon index.tml je vais finalement
11:20
commenter tout le reste voilà comme ceci
11:27
je vais ensuite au niveau de mon app.js lu précisé que je veux construire une nouvelle to do list donc on va l'appeler
11:33
liste également new to do list je l'importe aussi en haut et ensuite je
11:39
vais préciser que je lui passe la liste des tout doux une fois que j'ai cette liste je vais lui dire j'aimerais bien
11:45
que tu le rajoutes à l'élément qui a l'ID c'était tout doux list
11:55
voilà donc là on a une structure qui est assez simple à comprendre au niveau du code on crée une to do list et ensuite
12:01
on choisit de l'ajouter à l'élément que l'on souhaite bon il râle un petit peu à ce niveau là
12:06
parce qu'on n'a pas défini la propriété privée en amont donc ça c'est pas bien grave on lui dira que ici par défaut
12:12
tout doux sera un tableau vide et là on n'a pas de problème si ce n'est que on a
12:17
laissé l'alerte parce que on a mis une URL qui est incorrecte donc dans notre appât de tout il va
12:23
falloir commencer par créer la structure HTML donc on va pas s'embêter ici on va tout simplement prendre tout notre code
12:29
comme ceci donc toute la partie formulaire et la partie main et on va lui dire lorsque je fais un appel je
12:36
veux que tu prennes l'élément et que tu fasses un mineur HTML et que tu mettes toute cette structure là je vais
12:42
utiliser des back TIC pour que ça soit un petit peu plus simple autre petit détail je ne fais pas
12:48
correctement ma documentation ici donc je vais déjà documenter à quoi ressemble une to do grâce au système de type def
12:54
donc je vais faire unrobase type def ça va être un objet que je vais appeler tout doux cet objet il va avoir
13:01
différentes propriétés je ne suis pas intéressé forcément par le useradies mais tout le reste m'intéresse je vais donc rajouter une propriété qui sera de
13:09
type number et qui sera l'ID ensuite on aura une propriété title qui sera une
13:15
chaîne de caractère et enfin on aura un boulet 1 pour compléter ce qui permettra de savoir si la tâche a été complétée ou
13:21
non maintenant que j'ai ce type là je vais pouvoir l'utiliser et je vais ici lui dire que le type de cette variable
13:27
là c'est quelque chose de type tout doux et c'est un tableau de tout doux pareil dans le constructeur je vais
13:34
préciser que le paramètre que l'on attend ça va être un tableau de tout doux au niveau du à peine de tout je
13:40
vais lui préciser que moi ce que j'attends encore une fois c'est un HTML LMN voilà donc je documente tous c'est
13:46
important si j'essaie maintenant de regarder ma page hop on voit bien que ça rajoute la
13:51
structuration HTML et si jamais on avait une erreur encore une fois donc si je reviens dans mon app.js et que je mets
13:58
une URL incorrect on a aucun élément d'interface qui s'affiche donc c'est impeccable donc là on va avoir besoin de créer
14:04
chaque élément dans notre liste et ensuite de rajouter des comportements donc on pourrait tout à fait dans le leader HTML générer la liste directement
14:12
sous forme de chaîne de caractère le problème c'est qu'après on va devoir ajouter des comportements et dire quand tu cliques sur la poubelle il faut que
14:18
tu supprimes quand tu vas cliquer sur la checkbox faudra peut-être que tu fasses des choses donc ça risque d'être après
14:24
un peu compliqué parce qu'on va devoir ajouter des événements et c'est plus simple de travailler avec des petits morceaux de code qui contiennent leur
14:30
propre logique donc je me dis que là ce qui serait intéressant c'est d'avoir une classe pour représenter un élément donc
14:37
on va créer une nouvelle classe je vais le mettre dans le même fichier je me dis que c'est pas intéressant ici d'aller
14:43
séparer et en fait ça va nous permettre de construire un item pour construire cet élément là ben on va avoir besoin de
14:49
lui passer la tâche donc à ce niveau là je recevrai un paramètre tout doux et je ferai ma logique à l'intérieur je ne
14:54
vais pas forcément initialiser quelque chose et je précise le type avec la JS doc
15:00
donc mon idée c'est de construire notre alli on va avoir besoin peut-être de greffer des comportements sur les check
15:05
box ce genre de choses donc plutôt que de créer un leader HTML à ce niveau là on va utiliser notre méthode créer
15:11
télémment donc ici je vais lui dire je vais créer une variable li et je vais faire un cree télémment donc je vais
15:17
importer ce que moi j'ai déjà créé donc attention à bien rajouter l'extension ici il met un chemin relative donc il
15:23
dit c'est un dossier en arrière et ensuite c'est dans le dossier function c'est ensuite on a Dom point JS
15:29
cette partie inporte je vais la mettre avant les commentaires de préférence on mettra les inportes au tout début des
15:34
fichiers je vais redescendre maintenant je vais donc créer un lit et je vais lui donner une classe et je vais prendre la
15:41
classe que j'avais normalement dans l'HTML c'est cette classe là
15:46
voilà alors on voit que on a aussi une classe is compléty donc on va la retirer ça ça
15:53
sera des classes qui permettra de savoir dans quel état est notre élément ensuite à l'intérieur on a un input donc on va
16:00
aussi le créer de cette manière là donc on va créer un input ça va être la checkbox finalement et on fera un create
16:06
et les ment et on va créer un élément de type input on va lui dire que ça va être de type checkbox on va lui donner une
16:15
classe particulière voilà et on va aussi avoir besoin de lui donner un ID parce qu'ensuite on a un label qui va être
16:21
connecté dessus pour les ID on ne peut pas commencer par une lettre donc on va commencer par tout doux et on va
16:27
rajouter tirer suivi de l'ID de la de la tâche donc on va utiliser plutôt des back tics à ce niveau là voilà et là je
16:34
vais pouvoir utiliser tout doux voilà donc là on a créé notre check box
16:40
et cette checkbox on va la rajouter à notre Ali donc on fera un lit point à
16:45
peine de checkbox après la checkbox qu'est-ce qu'on a on a un label donc il y a cette classe là
16:52
donc on va aussi le créer de cette manière là donc on fera un constat label
16:58
= create et les mêmes on lui passera le tag name ça sera label on va une suite
17:04
lui passer la classe voilà et on va lui donner le fort donc la tribu fort il
17:10
permet de relier à un input particulier donc ce qu'on peut faire c'est sauvegarder peut-être l'ID en amont pour
17:16
éviter de répéter deux fois ce petit bout de code une fois qu'on a cet ID on peut l'utiliser ici et aussi dans le
17:22
fort voilà c'est plus pratique je continue une fois qu'on a le label on
17:30
veut avoir le titre à l'intérieur donc là on va utiliser inertex parce qu'on sait jamais depuis notre API on pourrait
17:35
avoir de des gens qui essaieraient d'injecter de l'acheter ml donc au fur et un label point inertext et en lui
17:41
donnerait le title donc ça serait tout doux points
17:49
donc pour le petit bouton on va créer une variable encore une fois button on fera un Creed et les mêmes en lui
17:56
passera le bouton hop on lui donnera la classe donc la classe ça sera ça et ensuite on fera un Button point HTML
18:03
parce que là j'ai directement envie de lui injecter l'icône et en utilisera l'icône que l'on a à ce niveau là
18:10
voilà hop hop ici et enfin on rajoute notre bouton à notre label
18:18
donc moi je vais juste peut-être regrouper toute la partie à peine je me dis que c'est plus logique entre
18:23
guillemets de créer les éléments en amont et de faire un appel de juste après donc j'ajoute la checkbox j'ajoute
18:29
le label et enfin j'ajoute le bouton donc maintenant il va me falloir pouvoir aussi récupérer cet élément là vu que
18:36
cet élément-là est construit dans notre classe par an on va pouvoir faire une petite boucle et on aimerait bien récupérer l'élément pour pouvoir
18:42
l'ajouter à notre structure donc soit on peut se faire une méthode à peine de tout soit on peut sauvegarder cet
18:48
élément là et le renvoyer plus tard là c'est vraiment à vous de voir moi je me dis que l'histoire d'être raccord avec
18:54
l'autre classe que l'on a créé on va créer une méthode à peine de tout aussi donc je vais créer une méthode à peine
18:59
de tout ça prend en paramètre un élément donc ça on va le documenter tout de suite prenez ce réflexe là c'est
19:06
important je ne mets pas forcément d'explications sur le nom de cette méthode parce que je trouve que le nom
19:11
de la méthode explique suffisamment ce que ça fait au niveau du à peine tout je vais être un petit peu embêté parce que
19:16
j'ai besoin de le dire ajoute le l.i dans cet élément là et le lit on y a accès que à ce niveau là donc je vais me
19:22
créer une propriété privée qui sera l'élément et je vais lui dire ici sauvegarde dans
19:28
vis point element notre élément une fois que j'ai cet élément là dans mon open de
19:34
tout je pourrais lui dire et les mains point à peine et rajoute notre élément voilà
19:42
maintenant que cette logique a été créée je vais pouvoir dans la classe parente venir supprimer cette partie là donc on
19:49
a maintenant une liste vide je vais lui dire de récupérer la liste en faisant element parce qu'on ne va pas partir sur
19:55
tout le body on veut juste se baser sur l'élément qui était envoyé dans le à peine de tout et on fera un quarry
20:01
selector pour trouver le list groupe ensuite on va pouvoir boucler sur nos to do nos tâches à faire et pour chaque
20:07
tâche à faire on va construire un to do list item et ensuite on va le dire de le rajouter à la liste donc on va faire une
20:14
boucle fort on va lui dire pour l'aide to DOF vis point tout doux je veux que
20:21
tu crées une nouvelle tâche donc nous on va l'appeler t ici en faisant un new to
20:26
do list item je lui passe en paramètre la tâche à faire et ensuite je peux lui dire à peine de tout ajoute ça à notre
20:34
liste je vais sauvegarder et maintenant j'ai automatiquement cette liste qui a été créée
20:40
alors peut-être un petit détail si on regarde notre API il y a certaines tâches qui sont déjà complétées par
20:46
exemple la quatrième tâche ici pourtant dans notre HTML ce n'est pas le cas donc là il faudrait lui dire rajouter un
20:52
attribut de check sur notre input si la case est cochée donc là je vais rajouter un chèque et je vais lui dire de
20:59
d'utiliser tout doux point complétide au niveau de ma méthode crit élément il
21:06
va falloir que je rajoute une petite condition en lisant si
21:26
comme ça maintenant hop on voit que seul la case qui a été sélectionnée la quatrième a été coché toutes les autres
21:33
ne recevront pas d'attributs de check c'est input n'a pas l'attribut de check par contre celui-ci vu qu'il a check à
21:39
trou il aura bien cette valeur là par contre peut-être on peut mettre un attribut différent parce que normalement certains avoir juste un attribut de
21:46
check on s'était pas forcément une voilà à avoir une valeur comme ça là le navigateur le comprend mais c'est pas
21:52
forcément idéal donc nous ce que l'on pourrait faire c'est plutôt utiliser ici du ternaire dans notre to do list.js et
21:57
lui dire en fait si la tâche est complétée je veux que tu mettes une chaîne de caractère vide sinon je veux que tu mettes nul
22:04
et dans mon cruauté elements à ce niveau là j'ai plus qu'à mettre cette condition là et ça sera suffisant donc maintenant
22:11
dans mon input qui a la check box check on voit que ça met juste check c'est un peu plus raccord avec ce que l'on attend
22:17
normalement voilà donc là on est bon on est capable de générer cette to do list
22:23
maintenant on aimerait bien que l'utilisateur et la possibilité d'en supprimer une l'avantage c'est que vu
22:28
qu'on a séparé dans des classes on peut se concentrer ici que sur cette classe là pour gérer la logique individuelle
22:34
d'une tâche donc typiquement je vais pouvoir ajouter des comportements donc je vais le faire à ce niveau là on va le
22:41
dire lorsque tu cliques sur le bouton donc on fera un Button point A des vent listener et on va lui dire lorsque tu
22:47
cliques j'aimerais bien que tu supprimes la tâche pour ne pas mettre trop de logique à ce niveau là je vais créer une
22:54
fonction en dehors donc cette fonction je vais l'appeler remove
22:59
tout simplement j'allais trouver un nom un petit peu plus original mais remove c'est très bien cette fonction elle est
23:05
très simple elle va se contenter juste de prendre l'élément et de le remove
23:11
donc au niveau de mon advance je pourrais être tenté ici de faire juste un vice-prés reboot pour lui passer la
23:16
fonction mais attention si on fait ça on a vu le event listener ils appellent la fonction avec un bind particulier donc
23:23
vice ne fera pas référence à ce que l'on pourrait imaginer mais il faudra référence au courant de Target donc ça
23:28
ne nous va pas donc on va utiliser une petite fonction fléchée voilà si on veut
23:34
empêcher le comportement par défaut du bouton il faudra lui passer l'événement donc on pourra ici lui dire qu'on aura
23:40
un paramètre qui sera de type pointer event vu que c'est un événement de type clic et on lui dit demandera de faire un
23:47
e point prévente des volts pour empêcher le comportement par défaut voilà donc je
23:53
vais cliquer sur cette tâche là et on voit que cette tâche là est bien supprimée impeccable donc maintenant on
23:59
va passer à ce formulaire là on aimerait bien être capable d'ajouter un élément donc l'avantage c'est qu'on a déjà posé
24:05
une partie de la logique quand je vais soumettre le formulaire je vais récupérer ce qui a été mis dans ce champ
24:11
créer un nouveau élément tout doux et ensuite je vais pouvoir instancier un nouveau to do list item pour pouvoir
24:17
l'ajouter à ma liste donc à ce niveau là je vais avoir besoin de récupérer le formulaire donc je ferai un élément
24:24
point queri selector je vais trouver le formulaire il y en a qu'un seul donc j'ai pas besoin d'un sélecteur plus
24:29
spécifique et je vais lui dire directement je veux que tu ajoutes un éventice
24:34
et un second paramètre je vais le passer une fonction fléchée pour éviter aussi que le vice se fasse modifier et je vais
24:41
appeler une fonction dans mon objet alors là il y a plusieurs conventions certaines personnes mettent on s'amit donc ils mettent on suivi du nom de
24:47
l'événement d'autres préfèrent utiliser undel parce que ça traite l'événement nous on va ici utiliser un 7 meet donc
24:54
on va faire un vis.on 7 meet et en lui passera l'événement donc à ce niveau là je vais pouvoir
25:00
créer cette méthode là donc c'est on s'amit qui prend un paramètre l'événement qui sera de type selpite et
25:06
20 voilà donc qu'est-ce que fait cette fonction comme d'habitude en prévente
25:12
des fautes parce qu'on ne souhaite pas envoyer le formulaire ensuite on va avoir besoin de récupérer le title qui a
25:18
été rentré donc le title si on regarde notre input ici
25:23
est-ce qu'il a un name il a un name title impeccable donc à ce niveau là je vais pouvoir lui dire je veux récupérer
25:29
un new forme data je vais lui passer un paramètre le formulaire donc c'est le
25:35
courant target sur ce formatage je vais faire un get et je vais lui demander de récupérer la valeur qui correspond au
25:43
champ qui s'appelle title et ça ça nous donne un objet un peu spécial on peut utiliser tout string pour s'assurer
25:48
d'avoir une chaîne de caractère si ensuite je fais une console point log de title et que je regarde ma page hop
25:55
si je clique sur Ajouter j'ai bien mon titre et on voit que le formulaire n'est pas soumis impeccable première chose que
26:01
je peux vérifier c'est regarder est-ce que le titre n'est pas vide par
26:07
défaut j'ai ici mis un attribut require ce qui fait que si jamais en réactualise la page et qu'on essaie de soumettre on
26:13
arrive même pas dans cet événement si on a des règles de validation qui sont mises dans l'HTML ces règles là prennent
26:19
le précédent par contre ce qui peut se passer c'est que l'utilisateur peut mettre des espaces donc là dans ce cas
26:24
là on va lui dire au niveau du title je veux en plus en profiter donc là désolé
26:30
j'ai cliqué je vais en profiter pour trim la chaîne de caractères trim ça permet de retirer les espaces en début
26:36
et en fin de chaîne et lui dire si le title est vide dans ce cas là je return
26:42
je ne vais pas plus loin parce que on va pas vouloir créer des tâches qui sont vides donc si je fais ça et que je
26:47
clique sur Ajouter il ne se passera rien maintenant on peut continuer donc là
26:54
l'idée ça va être de créer une to do donc on va faire un constat tout doux égal on a besoin de lui passer un Heidi
27:01
pour l'idée on va pas s'embêter on va soit on peut mettre un nombre qui s'incrémentera soit on peut le donner un
27:07
time Stampe sachant qu'on peut se dire que c'est quasi impossible de créer une même tâche en une minute ensuite on va
27:15
lui passer le title le title c'est ce que l'on a ici donc c'est plutôt facile et on peut même retirer cette notation
27:21
là ensuite on va lui passer complétide par défaut bah la tâche n'est pas complétée maintenant que j'essaie tout
27:28
doux c'est super parce que je vais pouvoir l'utiliser dans mon constructeur ici donc je vais créer un nouvel item en
27:33
faisant un new tout ou list item je lui passe ma tâche et je vais pouvoir le
27:40
dire maintenant j'aimerais bien que tu rajoutes ça à mon élément donc mon élément c'était hop hop le list groupe
27:48
et là je suis un peu un peu bêta parce que finalement même pas accès à ce cet élément là donc
27:53
ça veut dire peut-être que ça peut être intéressant de créer une propriété pour pouvoir y avoir accès donc je vais dupliquer cette ligne là on va ici créer
28:01
une variable liste et les menthe on va préciser que ça va être HTML
28:07
UL et les maths voilà donc ça c'est pour être extra-prés mais vous pouvez mettre un simple HTML et lemens ça marcherait
28:13
tout aussi bien à ce niveau là plutôt que de simplement créer cette variable liste je vais lui dire de créer
28:20
et de mettre la valeur dans liste élément attention faudra aussi modifier l'autre occurrence de liste qui est ici
28:28
maintenant à ce niveau là je peux lui dire je vais utiliser mon appel de tout et je veux que tu rajoutes ça dans mon
28:35
liste élément je vais descendre un petit peu mon inspecteur je vais essayer de rajouter une tâche et dès que j'appuie
28:41
sur Entrée on voit que cette tâche est rajoutée le problème c'est qu'elle est rajoutée enfin de chaîne ça ne me va pas
28:47
trop bien donc là on a deux solutions soit on crée une nouvelle méthode très peine de tout à ce niveau là soit on se
28:54
dit que est-ce que c'est vraiment le rôle de cette fonction de gérer comment elle va être ajoutée au reste moi
29:00
personnellement je me dis que non donc plutôt que d'avoir ça je pense que ça serait plus logique d'avoir un guetteur
29:06
qui nous permettrait d'avoir l'élément associé donc cette méthode là elle retournerait un HTML element et elle se
29:13
contenterait de retourner la propriété privée et les maths ce qui fait que maintenant lorsque à ce
29:20
niveau là je fais un appel de tout bah ça ne va plus marcher en fait on partira de notre liste element et on lui dira il
29:26
faut que tu prépares le l'item point et les ment à ce niveau là aussi je ne vais
29:33
plus avoir besoin de faire un appel de tout je vais pouvoir partir de mon liste et les menthe et lui dire j'aimerais
29:38
bien que tu apprennes et que tu appelles la tâche et sur cette tâche là je veux l'élément aussi si je sauvegarde
29:46
maintenant on voit que la structure marche toujours aussi bien et si je j'ajoute un élément automatiquement il
29:52
est ajouté en début de chaîne le petit problème c'est qu'on aimerait bien peut-être vider ce champ là donc
29:58
vous avez plusieurs solutions la première c'est de récupérer l'input et de définir une value qui est vide et
30:03
dans ce cas là ça videra le champ sinon sur les formulaires vous avez une méthode qui est plutôt cool donc si je
30:09
vous montre les HTML form et les ment donc vous avez quelques petites méthodes dessus et on a une méthode reset qui
30:15
permet de réinitialiser la valeur du formulaire à son état initial ça prend tous les champs et ça allait réinitialise c'est un peu comme un
30:21
bouton de type reset si vous voulez donc nous c'est idéal par rapport à ce que l'on veut faire donc à ce niveau là on
30:27
va faire un e point courant target pour récupérer le formulaire et on voit que on le fait deux fois donc
30:33
ça veut dire c'est le bon moment pour introduire une nouvelle variable voilà
30:40
et on va lui dire plutôt ici de prendre le formulaire et de le reset
30:45
voilà donc si je reviens sur ma page je réactualise je mets ajouter j'appuie sur
30:51
Entrée l'attache est ajoutée le formulaire est réinitialisé on voit aussi qu'on ne perd pas le focus donc
30:56
automatiquement on est focus sur ce champ là et on peut ajouter une autre tâche et continuer
31:02
voilà et on peut ensuite les supprimer c'est fonctionnels donc on arrive à la
31:08
partie qui peut sembler un petit peu compliqué c'est ce système de filtre alors là on a deux solutions la première
31:13
c'est de gérer cette logique là entièrement en JavaScript on pourrait se créer sur ce TO DO lister une méthode
31:19
hide et une méthode show pour afficher ou masquer l'élément hide ferait un display non et show retirerait le
31:26
display sur chaque élément et ensuite on pourrait détecter quand on coche une des cases et on afficherait ou
31:33
en masquerait les éléments en fonction le problème c'est que il va falloir aussi gérer quand on ajoute une un
31:38
élément dans la liste est-ce qu'on est actuellement dans le filtre fait et dans ce cas là il faudrait que l'élément soit
31:44
ajouté mais sans être visible donc très rapidement on va avoir une logique qui serait un petit peu complexe donc
31:49
parfois il faut se dire que la meilleure solution ce n'est pas forcément d'utiliser que du javascript utilisez du
31:54
CSS peut être intéressant en fait quand on va cocher une case ici on va automatiquement mettre en une classe
32:00
particulière au niveau de notre liste par exemple on mettra une classe show all quand on voit toutes les afficher
32:05
une classe chaud tout doux quand ça sera les éléments à faire et chaud donne
32:11
quand ça sera les éléments fait et ensuite pour chaque élément dans ma liste je vais rajouter une classe il se
32:17
complétie de si la tâche est complétée et rien sinon donc à ce niveau là dans nos to do list
32:23
item je vais détecter quand est-ce qu'on change l'état de notre tâche pour cela on va avoir besoin de se greffer sur la
32:29
check box donc on va faire un check box point A des vent listener et on va écouter le change lorsque la valeur
32:37
change on va lui demander d'appeler une méthode qui va s'appeler toge tout
32:42
simplement et on lui passera alors je suis pas sûr que ce soit intéressant de lui passer la totalité de l'événement je
32:48
vais simplement lui passer le courant target voilà à ce niveau là je vais créer la méthode
32:54
donc on va la mettre ici donc toggle ça permet de changer l'état d'une checkbox
32:59
et en lui passant par mètre l'élément donc ici ça sera la checkbox je rajoute
33:04
un petit peu de PHP doc donc ce sera un HTML input element ça peut être intéressant de mettre une description
33:10
parce que ça c'est peut-être pas forcément clair donc on va mettre ici change l'État
33:16
à faire slash fait
33:22
de la tâche voilà donc au niveau du togol qu'est-ce qu'on va faire on va regarder est-ce que la
33:29
case est cochée donc on va mettre if check box point check ben dans ce cas là
33:34
je veux rajouter au niveau de mon élément je vais lui dire ajouter la classe donc
33:40
on va utiliser classe liste et on rajoute is complétite dans le cas contraire je veux que tu
33:46
supprimes cette classe là on fera un remove
33:52
si maintenant je réactualise le problème c'est que cette tâche là quand lorsqu'elle arrive dans la structure HTML j'aimerais bien qu'elle est déjà la
33:58
classe is complétide et c'est pour ça que ici j'ai préféré du passé un htmlinment parce que ça fait en sorte
34:03
que cette méthode puisse aussi être utilisée directement ici lorsque j'ai rajouté noëli et tout ça je peux lui
34:09
demander ici de faire un vice-pointe togun et d'utiliser la checkbox la
34:14
checkbox est encoché ou non cocher il va pouvoir appliquer le comportement et directement nous mettre la bonne classe par contre on voit que ça crée une
34:21
erreur donc ça c'est parce que notre travail catch racine ben il a lieu ça veut dire qu'on a une erreur quelque
34:27
part dans notre code ça ça peut être gênant si vous mettez un travail catch aussi global vous ne voyez pas forcément
34:32
en erreur en console donc ce que vous pouvez faire dans le catch c'est laisser l'erreur aller jusqu'à la console grâce
34:37
à une console point erreur de e comme ça au moins vous comprenez de quoi il a retourne mais en fait le problème ici
34:43
c'est que on lui demande de faire un comportement avant que la propriété privée et les mêmes soit définie et du
34:48
coup il râle donc à ce niveau là on va définir l'élément beaucoup plus tôt dans votre code dès qu'on a notre Ali donc là
34:55
ce niveau là hop je lui demande d'initialiser les choses si je regarde mon
35:01
item qui a la case cochée on voit bien que il a cette propriété il se complétisme l'avantage c'est que
35:07
maintenant CSS c'est très facile je peux lui dire finalement par exemple avec du style j'ai envie que toutes les tâches
35:13
qui sont complétées donc toutes les tâches x compliquées je veux qu'elle soit indice les nonne et je vais mettre
35:19
même un important voilà pour prendre vraiment la priorité et dans ce cas là
35:25
ça nous permet de masquer les tâches mais il va falloir faire ça en fonction d'une condition particulière il faudra faire ça que si
35:31
on a tel ou tel filtre d'activé donc pour chaque filtre on va rajouter une classe au niveau de notre structure HTML
35:37
et là il va falloir revenir dans le code principal de notre to do list donc on a une série de boutons qui ont un attribut
35:44
data qui permet de savoir quel est le filtre qui est actif ORL si on veut voir toutes les tâches tout doux si on va
35:50
avoir qu'une seule et donne sinon donc à ce niveau là hop hop on va rajouter des eventlisseneurs pour ces boutons là donc
35:57
je vais lui dire prends l'élément trouve moi les boutons qui sont dans le groupe donc
36:03
on lui dira prend le Btn groupe et trouve moi tous les Button et je veux que tu parcours chacun de ces boutons là
36:10
et pour chacun de ces boutons là tu vas ajouter un lisseur de type clic et je
36:16
veux que tu lances une fonction et nous on l'appellera ici Google filter et en
36:22
lui passera en paramètre l'événement et attention cette fonction-là elle va être dans l'objet je vais pouvoir la déclarer
36:29
de manière privée parce que je me dis que je n'en ai pas besoin depuis l'extérieur d'ailleurs la méthode ons of
36:35
meat pareil elle peut être tout à fait privée il n'y a pas de souci on n'a pas l'intention de l'utiliser depuis l'extérieur
36:41
donc je vais maintenant créer cette méthode là petit détail si vous êtes sur votre éditeur vous pouvez replier les
36:47
méthodes je voulais pas forcément expliquer mais ça permet d'avoir un petit peu plus de clarté et de voir
36:52
seulement ce qui vous intéresse voilà et donc de pouvoir naviguer un peu plus facilement dans votre code donc là on va
36:59
lui dire je vais créer ma méthode togolf filter qui prend en paramètre un événement et ça sera donc un événement
37:04
de type pointer event vu que c'est un clic pointer event première chose que je
37:10
fais vu que c'est un bouton et si jamais on a un formulaire qui entourait ça on fait un prévoit des volts pour empêcher
37:16
le comportement par défaut ensuite on va avoir besoin de récupérer le filtre qui a été demandé donc on va
37:22
l'appeler filter et on lui demandera de récupérer la couronne target ça sera le bouton sur lequel on a cliqué et on
37:28
récupère la tribu data si je regarde en console je vais me
37:35
faire un petit console point log de filter et je vais regarder est-ce que je détecte bien le clic c'est effectivement
37:42
le cas première chose que je peux faire c'est faire en sorte que ce bouton là soit actif donc là je peux lui dire fais un e
37:50
point courant target et rajoute la classe active
37:59
si je fais ça lorsque je clique sur un élément il a bien la classe active le problème c'est qu'il faudrait supprimer la classe active de l'élément qu'il
38:05
avait à au préalable ici le tout par exemple donc là on peut utiliser un e point courant target pour trouver le
38:12
bouton sur lequel on a cliqué remonter à l'élément par an faire un quarry selector pour trouver l'élément qui est
38:18
actuellement actif prendre ça en classe liste et le supprimer
38:25
voilà comme ça dès que je clique sur un élément l'élément qui avait actuellement la classe active ne l'a plus et on peut
38:31
comme ça toggle nos différents éléments donc ça c'est la partie visuelle du filtre maintenant on va mettre une
38:38
petite condition on va lui dire si le filtre est égal à tout doux ça veut dire qu'on veut afficher les tâches qui sont
38:45
à faire on va prendre notre élément qui contient la liste et on va lui rajouter
38:51
une classe particulière alors je me dis que ça serait intéressant d'avoir deux classes une classe qui permettrait de masquer les tâches complétées et une
38:58
classe qui permettrait de masquer les tâches à faire donc si j'ai ici la tâche à faire ça veut dire que je veux masquer
39:05
les complétides donc je vais mettre une classe A et de completed par contre je
39:10
ne veux pas que en est la classe donc on fera un remove hide to do
39:16
maintenant on a un autre cas si le filter il est égal à c'était quoi
39:21
c'était hop hop si je reviens dans ma liste c'était donne si mon filter il est à
39:27
donne ça veut dire que je veux masquer les tâches qui sont en tout doux donc je vais lui dire dans ce cas là je veux que
39:34
tu rajoutes un ail de tout doux par contre je veux que tu retires le I de
39:39
complétite parce qu'on veut justement afficher les tâches qui sont complétées et ça ça sera un lsif
39:44
dans le dernier else ça veut dire qu'on est sur le petit bouton toute mais dans ce cas là on supprimera les deux classes
39:50
on ne veut masquer aucune des tâches de notre liste donc on supprimera la classe
39:56
aille de to do et high de completed je vais faire un essai maintenant si je reviens au niveau de mon élément je vais
40:01
regarder mon UL celui qui entoure nos listes donc on voit que par défaut il n'a pas de classe et si je clique sur
40:07
affaire on voit qu'on a un hide complétid il masquerait les tâches complétées et si je mets un fait il
40:13
masquerait les tâches à faire donc il me reste plus qu'à faire du CSS pour que la magie opère donc dans mon index.html je
40:21
vais rajouter un tout petit peu de CSS et je vais lui dire si on est sur un hide complet Ted
40:27
et que la tâche est complétée dans ce cas là il faudrait mettre un display non en importance
40:35
j'essaie de actualiser je fais un affaire et on voit bien que ça masque les tâches complétées ensuite si on est
40:42
dans une dans le cas hide to do ça veut dire qu'on veut masquer les tâches qui n'ont pas la classe compliquée donc je
40:48
vais lui dire trouve les éléments qui n'ont pas la classe is complétides le
40:53
problème c'est que ça sélectionnerait un peu trop d'éléments donc je vais lui dire sélectionne que les to do qui sont comme ça je vais dire trouve les tout
40:59
doux qui n'ont pas la classe ils se complétides et dans ce cas là lorsque je clique sur affaire ça masque les tâches
41:05
à faire lorsque je clique sur fait ça masquera les tâches qui sont à faire et
41:10
lorsque je reviens ici ça me relire réaffiche toutes si je suis sur la partie filtre avec le à faire et que je
41:16
rajoute une tâche elle va bien s'ajouter mais elle ne se verra pas parce qu'on a toujours le filtre qui est actif si je reclique sur
41:23
toute on voit bien que la tâche revient et redevient visible donc parfois il faut faire un petit combinaison entre du
41:29
CSS et du Javascript pour arriver à notre résultat final et là vous avez un cas d'utilisation du Javascript pour
41:35
créer un élément un petit peu dynamique sur une sur une page et qui permet de gérer différentes choses et comme
41:40
d'habitude j'insiste vraiment sur ce point ce que je vous propose ici c'est une des solutions ce n'est pas forcément vraiment la meilleure c'est pas
41:47
forcément la seule donc si vous êtes arrivés à cette solution là d'une autre manière c'est très bien si jamais vous avez des questions sur peut-être votre
41:53
solution ou votre approche vous pouvez venir sur le chat poser votre question peut-être montrer votre code et comme ça
41:58
vous aurez peut-être en retour sur est-ce qu'il y a des choses que vous pourriez à vélo améliorer est-ce que vous étiez dans la bonne direction voilà
42:04
donc pour la suite de cette formation on va garder cet exemple là en tête donc me supprimer pas le code parce qu'on va
42:10
rajouter des fonctionnalités par dessus et ça va permettre de découvrir des choses par exemple on va voir comment on
42:15
peut faire en sorte que tout soit persistant typiquement ça serait bien que si je réactualise la page je garde les tâches que j'ai déjà créé on va voir
42:22
comme ça comment utiliser le stockage on va aussi découvrir comment on peut faire en sorte d'éviter d'avoir des gros
42:27
inners HTML dans notre code comment on peut améliorer un petit peu certaines éléments de syntaxe on va découvrir des
42:33
fonctionnalités supplémentaires au niveau de notre code et j'utiliserai cette base pour vous montrer des cas pratiques pour chacune des nouvelles
42:39
fonctionnalités que l'on va découvrir donc j'espère que cette épée c'est bien passé j'espère que vous avez réussi un
42:44
petit peu avancer par vous même dessus et je vous donne rendez-vous dans le prochain chapitre
