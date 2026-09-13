# JavaScript cote navigateur : Les ecouteurs d evenements

Video : https://www.youtube.com/watch?v=TicxcEDiP3U

## Transcription

bienvenue dans ce nouveau chapitre nous allons parler des événements en Javascript donc lorsque on va écrire du
0:05
code pour des pages web en général ce qu'on va faire c'est qu'on va vouloir réagir à des événements utilisateurs par exemple dire lorsque tu cliques sur un
0:11
bouton j'aimerais bien déclencher tel ou telle action donc les écouteurs d'événements vont fonctionner vous allez le voir assez simplement dans le sens où
0:17
il y a qu'une seule méthode à connaître alors pour l'exemple nous ce qu'on va faire c'est qu'on va créer un petit bouton sur notre page et on va mettre
0:24
bonjour dessus et on aimerait bien que lorsque l'utilisateur clique sur ce bouton automatiquement on affiche une petite alerte donc la première étape ça
0:32
va être de sélectionner l'élément donc avec les méthodes que l'on a vu dans le chapitre précédent moi ici je vais créer une variable Button et je vais faire un
0:38
document points selector et aller trouver l'élément par rapport à son tag une fois que j'ai ce bouton on va
0:44
pouvoir utiliser une méthode qui s'appelle add event dictionnaire qui va permettre de rajouter un écouteur d'événements donc on fait un AD et vent
0:51
lister et un premier paramètre on va lui passer le type d'événements que l'on souhaite écouter donc il y a plein plein
0:57
d'événements ça va dépendre aussi des éléments HTML mais dans le cadre d'un clic mais l'événement s'appelle tout
1:02
simplement clique ensuite on se comprend paramètre on va lui passer une fonction et cette
1:07
fonction elle va être appelée lorsque on déclenchera l'événement en question donc nous dans notre cas on va simplement
1:13
mettre un à l'alerte bonjour voilà donc c'est vraiment la syntaxe de base pour les écouteurs on va préciser le type
1:19
d'événement que l'on souhaite écouter et le code à exécuter lorsque l'événement va être renvoyé si maintenant je me
1:25
rends sur ma page et que je clique sur bonjour on a bien cette alerte qu'ils affiche lorsque je clique alors maintenant il y a quelques petits
1:31
détails en plus à connaître donc d'abord cette fonction-là elle va prendre un paramètre un événement donc ici on peut
1:36
lui dire je vais avoir un paramètre event et plutôt que d'afficher l'alerte je vais pour l'instant faire un console
1:42
point loc de event pour voir de quoi il a un retour si maintenant je clique sur la page et que je clique sur le bouton bonjour on
1:48
voit qu'on obtient un pointer event pointer event qui contient tout un tas de propriétés il y en a pas mal qui
1:54
concerne ce type d'événement là si on se rend sur la documentation de MDN et que l'on cherche ce type d'événement donc on
2:00
va faire pointer event voilà on nous explique un petit peu les différentes propriétés et on a encore une fois ce
2:07
système d'héritage donc les points intervent ils héritent des maux 7 qui eux-mêmes
2:12
héritent des ui events qui eux-mêmes héritent des events donc toutes les méthodes que l'on va avoir
2:18
ben ce seront les méthodes de tous ces objets là alors il y a quelques petites propriétés intéressantes à connaître sur cet
2:25
événement là et ça va être valable quel que soit le type d'événements que l'on va avoir donc on a deux propriétés
2:30
intéressantes qui sont event point target et event point target
2:36
si j'essaie de cliquer sur mon bouton par défaut ça va être le même la même chose c'est à dire que ça ça va nous
2:41
renvoyer la cible de l'événement donc typiquement notre bouton par contre si dans mon index.html j'entoure mon
2:48
bonjour d'une semaine et à l'intérieur je mets mon bonjour si je clique sur le texte on va voir que on a des
2:54
consoles.lo qui sont différents le target va nous donner la cible sur laquelle on a véritablement cliqué donc
3:00
dans mon cas en fait là lorsque j'ai cliqué j'ai cliqué sur la span qui est dans le bouton donc il détecte bien
3:06
qu'il y a eu un clic sur le bouton par contre effectivement l'élément sur lequel j'ai cliqué c'est la span alors que le courant se target nous donnera
3:12
toujours le sujet du liceneur donc si j'ai fait le a des 22 listeners sur le bouton le e2.carante target sera
3:19
toujours égal au bouton alors pourquoi ça ça peut être intéressant imaginons que dans notre index.html on va retirer
3:25
cette panne là voilà et on est un second bouton que l'on appelle bonjour les gens
3:32
dans mon app.js si je souhaite écouter le clic sur plusieurs éléments il va me falloir faire une boucle donc à ce
3:38
niveau là je vais plutôt faire un document pour un query selectoral je vais aller sélectionner tous les boutons
3:43
et faire un petit forage dessus je vais récupérer un paramètre chaque bouton et
3:48
je vais pouvoir exécuter une fonction dessus donc là je lui dirai de faire un Button point add event listener j'écoute
3:56
le clic et je vais lancer une fonction cette fonction pour éviter de la répéter dans la boucle on peut s'imaginer que je
4:02
la crée un amant donc on peut s'imaginer créer une fonction on button clic qui
4:08
prendra un paramètre un événement et qui fera quelque chose donc maintenant je peux utiliser cette fonction là à ce
4:14
niveau là mais dans cette fonction j'aimerais bien savoir sur quel bouton on a cliqué ben c'est là que le courant target est
4:20
intéressant si je fais un event pour un courant target ça va me donner
4:26
hop les informations sur l'événement donc si je clique ici c'est bien le bouton bonjour sur lequel on va cliquer
4:31
alors que si je clique ici c'est le bouton bonjour les gens donc ça ça va être super pratique pour accéder à ces
4:37
informations là petit détail hop on n'oubliera pas dans le cas où on décide de se séparer les
4:43
choses à utiliser la JS doc et donc là je précise que c'est un pointer event
4:49
comme ça après dans ma fonction j'ai de l'autocomplétion et c'est plus pratique autre petit détail dans le cadre des
4:55
éventes listeners le vice est automatiquement modifié dans les fonctions si je fais une console point log de vis on va voir que là je vais
5:02
obtenir l'élément sur lequel on a cliqué donc vis sera l'équivalent d'un courant target si vous voulez donc faudra faire
5:09
attention si vous avez des fonctions qui sont en fait des propriétés dans un objet là il faudra il faudra utiliser
5:15
bind soit utiliser des fonctions fléchées pour éviter que le contexte de vis soit perdu on s'est un petit détail
5:20
mais c'est important c'est un petit peu comme le forage qu'on a vu dans les chapitres précédents il injecte un vis qui peut être embêtant alors ensuite on
5:27
a des méthodes intéressantes aussi sur cet événement là une première méthode c'est le prevent des Volt prévente des
5:33
volts va permettre d'empêcher le comportement par défaut de l'élément apprenons un exemple concret avec un
5:39
lien imaginons je fais un lien vers graphicard.fr au hasard et lorsque je clique dessus je veux
5:46
utiliser ce même lisseur donc je vais modifier mon quadrice élector hall pour lui dire agit aussi sur les liens
5:52
lorsque je vais cliquer sur graphique art vu que j'ai un préventes des volts on empêche le comportement par défaut
5:58
des liens qui est de rediriger vers une autre page si je retire ce préventes des foltes lorsque je clique ici on voit
6:04
bien que je suis redirigé donc le prevanne défolt va permettre d'empêcher le comportement de base de l'événement
6:09
donc par exemple ça sera utile dans les formulaires pour empêcher la soumission du formulaire typiquement on peut
6:15
s'imaginer que si on a des erreurs on empêche la soumission du formulaire pareil dans un champ si on veut limiter
6:20
le nombre de caractères si on détecte qu'il y a suffisamment de caractères on peut empêcher d'aller plus loin et on
6:25
peut faire pas mal de choses avec ce préventes des fautes ensuite une autre méthode utile c'est le stop propagation
6:31
alors pour comprendre ça il va falloir comprendre le principe même de la propagation alors on va s'imaginer que
6:36
autour de notre bouton on va avoir une DIF donc ici je vais créer une div et
6:41
cette div là je vais lui donner un peu de style donc on va simplement s'imaginer que ça va être un élément qui
6:47
va avoir une largeur de 100 une hauteur de 100 et un background color on va mettre du gris
6:54
si je lui demande de rajouter un comportement sur ce cette diva on va faire un document un élector on va lui
7:01
demander de sélectionner la Dive et on va lui dire lorsque tu cliques dessus hop j'aimerais bien que tu nous lances
7:07
une fonction qui fera qui fasse une console point log clic div voilà et lorsque l'on clique sur les
7:13
boutons on va faire une console point log button click voilà donc maintenant imaginons que je
7:21
clique sur le bouton qu'est-ce qu'on remarque on remarque que l'on a à la fois ce liceneur là et ce lisseur là qui
7:27
est exécuté en effet lorsque je clique sur le bouton intrinsèquement je clique aussi sur la DIV l'ordre d'appel est
7:34
important d'abord il va appeler le lisseur sur l'élément le plus petit et on l'a vu aussi lorsqu'on a cliqué sur
7:40
l'Espagne donc il va dire tu as cliqué sur le bouton et cet événement va se propager sur les éléments par an donc
7:46
j'ai vu que tu as cliqué sur le bouton tu as aussi cliquer sur cette div et tu vas aussi cliquer sur le body les
7:52
liceneurs vont être appelés dans cet ordre on va d'abord voir s'il y a des liceneurs sur le bouton et les appeler
7:57
ensuite est-ce qu'il y a des liceneurs sur les div et on va les appeler et ensuite est-ce qu'il y a sur le body et
8:02
on va les appeler donc on dit que l'événement se propage vers le haut le stop propagation va justement permettre
8:08
de stopper cette propagation donc si au niveau de mon bottenclick je lui dis de faire un event point stop propagation
8:16
automatiquement vous allez voir que lorsque je clique sur le bouton on a plus le lisseur de la div qui est appelé donc ça permet comme ça de stopper la
8:22
propagation donc ça ce sont vraiment les quatre choses que vous devez comprendre sur les événements le target courant
8:28
target le prévente des folt et le stop propagation ce sont les quatre méthodes qui sont principales vraiment dans l'utilisation des événements après vous
8:34
avez des propriétés mais elles vont dépendre en fait du type d'événement que vous recevez donc dans le cas par
8:40
exemple du des Mao sevent et des points inter event on a des informations comme par exemple la position en x et en y
8:46
donc là par exemple j'ai le page X et le page y qui me donne la position de mon
8:51
clic dans la page j'ai le offset X qui me donne la position par rapport à l'élément relatif vous avez le chemin
8:57
vous avez le type de pointer vous avez la possibilité de savoir si on avait maintenu contrôle en même temps donc il
9:02
y a plein plein de choses mais ça va vraiment dépendre de ce que vous avez besoin de faire alors maintenant on va parler d'un
9:08
troisième paramètre dans le ad event parce qu'effectivement il y a trois paramètres possibles donc on va se
9:13
rendre dans la documentation et on va chercher ad event listener donc le troisième paramètre c'est un objet
9:19
d'option qui contient trois propriétés la première propriété elle est très simple c'est once elle permet d'indiquer
9:25
que le lisseur ne va être appelé qu'une seule fois donc si au niveau ici de mon clic sur le bouton je lui dis je veux un
9:32
hands et je mets trou dans ce cas là l'écouteur ne va être exécuté qu'une seule fois si je clique sur le bouton on
9:39
a bien notre console.log si je reclique sur le bouton on n'a plus rien seul le lisseur de la DIV c'est exécute celui du
9:46
bouton a été supprimé a disparu ensuite dans l'objet d'option on a une propriété passive qui permet d'indiquer
9:52
que notre lisseur va être passif c'est-à-dire qu'il n'appellera jamais le prévente des volts l'avantage c'est que
9:57
ça permet ensuite au navigateur d'améliorer les performances sur certains événements qui sont appelés fréquemment on peut imaginer que par
10:03
exemple si on écoute le scroll le défilement de la page par l'utilisateur si à chaque fois que l'on défile un
10:08
petit peu le navigateur doit vérifier si il y a eu un prévoit des folles qui est appelé mais ça va être lent donc l'avantage c'est que lorsque les
10:14
événements sont passifs le navigateur peut se dire broker moi je peux défiler sans aucune attente parce que je sais que à aucun moment il y aura un prévu
10:21
donc ça a créé notamment la performance il faut savoir que suivant certaines navigateurs certains événements peuvent
10:28
être définis comme passif par défaut et vous aurez besoin de mettre un passif à folz si vous voulez faire un prévode
10:33
juste pour vous montrer à quoi peut ressembler l'erreur on va s'imaginer dans notre document modifier la
10:39
structure HTML pour créer une div qui voilà prend plus de place histoire d'avoir le défilement et on va écouter
10:45
lorsque l'utilisateur défile donc dans notre app.js je vais lui dire sur le document c'est sur le document qu'on
10:51
lance cet événement là je veux faire un Advent listener et écouter le défilement lorsque le défilement a lieu je vais
10:58
récupérer l'événement moi je vais l'appeler e parce que je trouve que c'est plus court et je vais faire un e point prevent des folles sauf que je
11:06
vais lui préciser en plus ce qui n'est pas possible normalement que notre lisseur va être passif si je sauvegarde
11:12
et que je scrol voilà le type d'erreur que vous allez avoir en console on vous dit Annabelle to preven defold inside
11:18
passive event l'isner invocation donc si jamais vous avez ces erreurs là c'est
11:23
que votre lisseur est passif et que vous faites un préventes des folles dedans donc dans ce cas là il faudra mettre passive à fols et vous n'aurez pas de
11:29
problème encore une fois ça va dépendre des cas de manière générale vous n'aurez pas trop besoin de toucher ce paramètre
11:35
là vous aurez juste besoin de savoir à quoi il sert et où il faut le toucher si jamais vous avez l'erreur que je viens
11:40
de vous montrer en console voilà alors maintenant le dernier la dernière propriété c'est la propriété capture
11:47
elle permet d'indiquer que l'événement sera distribué au lisseur enregistré avant d'être déstribué sur les éléments
11:53
enfants en fait ça va permettre d'inverser le système de propagation dont on a parlé tout à l'heure alors
11:58
pour vous donner un exemple on va remettre l'introdiv avec une bonne taille on va lui redonner sans pixels et
12:05
on va laisser les deux consoles que l'on avait mis on va peut-être retirer cette
12:10
partie là voilà donc si je clique sur le bouton dans la DIV on voit bien que c'est le lisseur du bouton qui est
12:16
exécuté puis le lisseur de la DIF par contre on l'a dit peut dire ben moi je veux être en capture donc ça m'est
12:23
capture à trous et dans ce cas là si je clique on voit que c'est d'abord le clic de la div qui est exécuté et ensuite
12:29
seulement le clic du bouton de la même manière si dans la DIV je fais un
12:34
event.-stop propagation dans ce cas là l'événement ne va pas descendre vers les
12:40
enfants et c'est seulement le clic sur la DIV que l'on donc maintenant si je reprends l'exemple
12:46
de la propagation lorsque je clique le navigateur va exécuter tous les liceneurs en mode Capture sur le body
12:52
tous les lisseurs en mode Capture sur la DIV puis tous les 19 en mode Capture sur le bouton ensuite il va exécuter tous
12:58
les liceneurs qui ne sont pas en mode Capture sur le bouton puis tous les lisseurs sans capture sur la DIV puis
13:03
les lignes sans capture sur le boîtier donc on a ce système qui descend puis qui remonte et si jamais on a un stop
13:10
propagation mais on peut stopper la propagation soit vers le haut soit vers le bas suivant le type de d'événements
13:15
que l'on a et d'ailleurs on en a pas forcément parlé mais vous avez la possibilité de regarder les lisseurs qui
13:20
sont disponibles sur vos éléments HTML pour cela il faut vous rendre dans l'inspecteur vous cliquez ici sur éléments et vous allez sélectionner les
13:27
mains qui vous intéressent nous ici on va sélectionner par exemple cette div là si je change un peu la taille voilà vous
13:33
avez à droite la partie qui vous permet de voir les styles et si je clique sur cette petite flèche on a aussi une
13:39
partie event listeners quand je clique dessus on voit tous qui sont disponibles au niveau de cette variable là et vous
13:46
pouvez déplier cette petite partie là pour voir les différents dis sonores qui ont été injectés donc là on voit que
13:51
c'est un bouton et on nous dit où est-ce que ça a été injecté ça a été injecté dans le app.js à la ligne 4 et là on a
13:57
le lisseur qui va correspondre à notre bouton voilà donc ça peut être intéressant ça peut aussi vous permettre
14:02
de détecter pourquoi il se norme ne marche pas s'il est pas branché ou qu'elle fonctionne JavaScript agit sur
14:07
l'élément donc ça peut être ça peut être assez intéressant et globalement c'est tout ce qui à savoir sur le système
14:13
d'écouteurs d'événements en tout cas en terme de syntaxe maintenant ce que je vous propose c'est de passer en revue certains événements qui peuvent être
14:19
intéressants donc principalement ce que vous allez avoir besoin de faire c'est souvent le clic qui va être utilisé mais
14:24
il y a pas mal d'autres événements qui sont intéressants alors on va s'imaginer que dans notre page on va créer un formulaire donc je crée un formulaire on
14:31
va lui préciser aucune action et à l'intérieur on va avoir un input
14:37
de type texte et on aura un bouton qui va mettre envoyé voilà donc lorsque je clique sur envoyer
14:44
la page est soumise on a la possibilité sur les formulaires de faire un préventes des volts et de pouvoir
14:50
récupérer des informations donc on va retirer tout ce que l'on a fait jusqu'à maintenant et on va faire un document
14:55
point corrector et on va sélectionner le formulaire et on va lui dire j'aimerais
15:00
bien avoir dessus un lisseur et le lisseur va s'appeler submit donc ça ça
15:06
va nous permettre d'avoir un événement qui permettra de contenir les informations sur notre formulaire si je
15:11
fais une console point log de e hop et que je vais dans ma console et que je
15:16
clique sur Envoyer on va voir les informations mais que très brièvement parce que le formulaire a été soumis
15:21
donc il faudra faire un Prévent des volts si on souhaite empêcher le comportement par défaut de ce formulaire
15:28
là qui est d'envoyer les informations on obtient alors un set mit event on peut se rendre dans la documentation pour
15:33
voir de quoi il en retourne mais globalement ça ne nous donne pas forcément des informations super utiles
15:38
en dehors du courant de Target en notera peut-être que pour les formulaires on a
15:43
un objet spécial qui va être intéressant donc on imagine que de cette c'était beau il reçoit un name et on va
15:50
l'appeler par exemple first name si vous voulez traiter les données qu'il y a à l'intérieur d'un formulaire vous
15:56
avez un objet qui est intéressant qui s'appelle forme data cet objet il est
16:01
construit à partir d'un élément de formulaire donc nous dans notre cas ce qu'il faudrait faire dans notre lisseur
16:07
si on veut récupérer ce qui était tapé par l'utilisateur ici on pourrait lui dire j'ai besoin de récupérer le
16:13
formulaire avec un e point court target et ensuite je peux faire un constat égal
16:20
new forme data et je lui passe un premier paramètre notre élément qui est
16:25
notre formulaire dans ce format on a par exemple get qui permet de récupérer une propriété 7 qui permet dans cette une on
16:33
va pouvoir lui dire j'aimerais bien récupérer le champ first name donc on pourra faire un data point get first
16:41
name et à ce niveau là je vais faire un console point log
16:46
ici donc si je sauvegarde et que je rentre quelque chose et que je clique sur Envoyer on voit que ça n'affiche ça
16:52
donc ce qu'on pourrait faire c'est faire une constante ici first name voilà et
16:59
lui dire par exemple si le la taille du first name est trop courte par exemple
17:04
cet inférieur à 2 on fait un e point près 22 volts pour empêcher la soumission du formulaire et la
17:10
typiquement on empêche le formulaire d'être soumis tant que les données ne sont pas valables bon c'est un exemple
17:15
simple mais vous voyez que si je clique sur Envoyer ici le formulaire ne fonctionne pas si je rentre une chaîne
17:20
de caractère suffisamment longue il va fonctionner concrètement on pourrait faire la même chose avec des attributs HTML mais
17:26
c'était pour vous montrer un petit exemple un petit peu plus dynamique des liceneurs sur les formulaires donc
17:32
ensuite on va parler de l'input donc on va rajouter un liceneur sur linpool et
17:37
sur les champs on a pas mal de choses que l'on peut écouter donc d'abord on a un événement qui s'appelle le change qui
17:42
est plutôt intéressant et qui permet de détecter quand le champ a changé par contre son comportement peut être un
17:48
petit peu surprenant par rapport à ce que l'on entendrait donc imaginons je décide de prendre ce formulaire et de
17:54
rentrer des données on voit que challenge n'est pas appelé pour le moment par contre dès que je vais quitter le champ il est appelé si je
18:02
refocus le champ et que je le quitte ce n'est pas appelé et en fait dès que je change la valeur et que je quitte le
18:07
focus cette événement de chaîne je va être appelé si vous voulez détecter quand l'utilisateur tape dans le champ
18:14
je vais peut-être aller à la ligne pour un petit peu plus de clarté ici voilà vous pouvez utiliser la
18:20
l'événement input input va être appelé dès que il y a une input dans le champ si je tape ici une lettre on voit qu'on
18:28
a une put ce que l'on pourrait faire c'est faire un console point log de e point courante target point value le
18:35
point value va nous donner la valeur dans un champ donc typiquement dès que je tape quelque chose on voit que
18:41
j'obtiens ici les informations qui ont été tapées attention par contre sur les input vous n'avez pas la possibilité de
18:48
faire un Prévan defold si je le fais on voit que ça n'empêche absolument pas l'utilisateur de taper des choses on a
18:54
d'autres événements on a par exemple qui down qui va permettre de détecter quand une clé va être pressée donc ça ça peut
19:01
être utilisé pour un champ mais ça peut aussi être utilisé pour autre chose typiquement ici on peut faire un event
19:07
point prévente défolt et dans ce cas là lorsque l'utilisateur presse une touche on voit que kidown est appelé mais rien
19:13
n'est tapé dans le formulaire parce qu'on a empêché la soumission de cet événement vers le champ si je le retire
19:18
on a bien ça l'avantage de qui down si on fait un console point log de l'événement c'est qu'on peut recevoir
19:25
des informations sur la touche qui a été appuyée si ici j'appuie sur a dans notre
19:30
événement on recevra un keyboard event et on aura une propriété qui s'appellera qui qui nous donnera la clé sur laquelle
19:37
on a appuyé comme je vous le dis on peut faire ça sur un input mais on peut faire ça sur n'importe quoi on pourrait lui
19:43
dire j'aimerais bien écouter ça directement sur le document et donc lorsque l'utilitateur tape quelque chose
19:48
ben on détecte ce qui bord des vent par exemple c'est ce que j'utilise pour
19:53
graphicard lorsque vous essayez de faire une recherche vous avez un raccourci contrôle cas qui déclenche une recherche
19:59
c'est pareil si vous avez besoin de faire ça au niveau de votre page vous pouvez écouter sur tout le document
20:05
lorsque l'on presse une touche et regardez est-ce qu'on a fait la touche Contrôle plus k si je réactualise la
20:11
page je fais ici contrôle k mais on va voir que dans la partie qui bordent on a
20:16
la touche qui a été app donc on voit bien que c'est un cas et on peut regarder aussi si contrôle qui est
20:22
appuyé donc on pourrait mettre une condition en lui disant si eux point contrôle qui est égal à trous et que la
20:30
clé sur laquelle on appuyer c'est égal à K dans ce cas-là on fait un présente des folles et ensuite on peut faire un
20:36
console point de log pour dire qu'on a appuyé sur un raccourci donc si vous voulez créer des raccourcis sur votre
20:41
page qui dans ne peut être super intéressant si j'appuie sur contrôle cas on voit bien qu'on a le raccourci qui
20:47
est déclenché et on a le comportement par défaut qui serait de focaliser la barre d'adresse
20:53
ici qui est annulée grâce au prévode
21:56
un élément va avoir le focus si je clique ici dès que je focus mon champ de
22:02
cet événement qui est appelé et on voit que c'est un événement de type focus event Blur va être appelé lorsque un
22:08
élément a été focus et qu'on le quitte voilà ça nous renvoie le même type d'événement mais c'est appelé lorsque on
22:14
quitte le focus alors maintenant on va parler des autres types de chant dans les formulaires donc on va imaginer que on a un input de type
22:22
checkbox et on a bien détecté quand je clique ou quand je retire le clic au
22:27
niveau de cette checkbox donc dans le cadre des check box c'est l'événement que l'on va écouter c'est le change qui
22:32
permettra de détecter lorsque la valeur change l'événement qui est renvoyé par ce lisseur va être un simple event ce
22:38
sera pas un event d'un type particulier et si on veut savoir si la case est cochée il faudra utiliser le courant
22:43
target et on fera courante target ce qui nous donnera à input et on aura une propriété particulière qui sera checke
22:50
dessus si je clique on voit que il me dit bien que ça a été sélectionné et si je supprime le checkbox on a ici Falls
22:58
donc c'est comme ça en général que vous allez vérifier si une case est cochée ou non enfin on va parler des select donc les
23:06
select on va créer un select et on va mettre différentes options donc
23:12
on va l'appeler first name toujours on va pas lui mettre didy et on va avoir une option avec option 1 en valeur
23:20
et en label voilà et on va dupliquer ce truc au moins trois fois on aimerait
23:26
bien détecter quand est-ce qu'on a changé la valeur dans ce Select et quelle valeur a été sélectionnée donc au
23:31
niveau de mon app.js je vais sélectionner le Select et c'est le même type d'événements qui va être écouté
23:36
c'est le change si j'essaie maintenant de sélectionner une valeur dans mon select dès que je change la valeur je
23:42
reçois un événement classique si je veux connaître l'élément qui était sélectionné je peux faire un event pour
23:48
une courante target.value et dans ce cas là ça va me donner l'option qui a été sélectionné option 3 j'aurais peut-être
23:55
dû mettre des valeurs différentes pour pouvoir différencier la valeur du label
24:00
mais dans ce cas là ça me donne vraiment ce qui a été indiqué dans la value on a aussi la possibilité de savoir quel
24:06
élément est sélectionné grâce ici à une autre propriété qui est dans le courant
24:12
de Target qui est sélectide options voilà si je sélectionne le
24:18
l'option 2 on voit que ça me renvoie une HTML collection qui nous dit l'ensemble
24:23
des éléments qui ont été sélectionnés et là j'ai mon option donc après on pourrait récupérer les attributs dedans
24:29
ou ce que l'on veut si jamais on a un select qui est multiple et que j'aurai essayé de sélectionner
24:36
une valeur puis une autre on voit que dans le cadre de la value mais ça nous
24:42
renvoie toujours un malheureusement ça nous renvoie que la première valeur qui a été sélectionnée alors que la partie sélective option va plutôt nous donner
24:48
toutes les options sélectionnées donc si on voulait les valeurs mais il faudrait il faudrait par exemple faire un petit
24:54
map on pourrait faire un console point log on ferait un e point courant de Target
25:02
sans le transformerait sous forme de tableau voilà pour pouvoir avoir dessus la
25:08
méthode map on récupérerait chaque élément chaque option et on sera intéressé que par la valeur de l'option
25:14
et dans ce cas là lorsque je sélectionne plusieurs éléments on voit qu'on obtient les différentes valeurs des options
25:20
sélectionnées voilà le Select fonctionne de manière un petit peu particulière mon concrètement
25:25
il y a beaucoup beaucoup d'événements et je peux pas tous vous les lister ce serait extrêmement long extrêmement pénible mais il faut savoir que sur la
25:31
documentation vous avez une page que je vous mettrai en description qui contient la liste de tous les événements possibles et sur quoi ils vont être
25:38
appelés donc par exemple sur les formes et les menthes on va avoir ces différents événements sur les inputs on
25:43
va voir ces choses là en plus et vous avez ici sur tous les événements qui sont sur un HTML élément et vous pouvez
25:49
comme ça parcourir pour découvrir un petit peu certaines choses peut-être un dernier petit détail sur les pointeurs
25:55
comme pour la partie qui down qui presque qui up on a la même chose on a le pointer out qui permet de détecter
26:01
qu'un élément quitte le survol pointeur over quand l'événement quand le curseur passe sur l'élément pointer up quand on
26:08
lâche le clic de la souris et vous avez comme ça tout un tas d'événements on parlera de pointeurs aujourd'hui plutôt
26:13
que de clics parce que on a les mobiles qui rentrent en jeu donc l'événement clic même si on peut s'imaginer que ça
26:19
ne marche qu'avec les souris il marche lorsque clique avec un iPhone avec son doigt mais on a des événements pointer
26:26
qui permettent d'indiquer justement que c'est des événements qui vont fonctionner à la fois avec un pointeur de type souris mais aussi avec un
26:32
pointeur de type doigt donc par exemple si on a le pointer leave ça détecte quand le pointeur quitte le survole pour
26:37
le coup c'est quelque chose qui va plutôt fonctionné avec les les souris parce qu'on n'a pas vraiment de moyen de bouger avec un doigt et en dessous on a
26:44
la chaîne de prototype qui nous montre comment hérite cette cette événement là donc il
26:50
y a beaucoup beaucoup de choses à découvrir mais ça dépendra des cas que vous avez besoin d'avoir et vous allez découvrir les événements un petit peu au
26:55
fur et à mesure de votre exploration du langage donc ce que je vous propose maintenant c'est un petit exemple simple pour
27:03
essayer un cas concret d'utilisation des event listeners alors rassurez-vous ça va pas être quelque chose de très
27:08
compliqué on s'imagine que on a un gros paragraphe et à l'intérieur on est en train de spoiler une série donc on est
27:15
en train de révéler la fin d'une série importante donc ce que l'on va faire c'est que on va s'imaginer que le début
27:21
de cette phrase qui contient le nom du personnage qui est mort on va mettre une classe spoiler dessus
27:27
voilà et on va faire la même chose sur un autre élément un petit peu plus bas voilà ici jusqu'à voilà jusqu'à là voilà
27:36
donc au niveau de mon CSS je vais préciser que lorsque j'ai un spoiler je
27:42
veux que le background color soit noir voilà et je veux aussi que la couleur du
27:47
texte soit noir petit détail c'est que si l'utilisateur sélectionne le texte il va se faire spoiler quand même donc on
27:53
va lui préciser que sur les spoilers la sélection va avoir une couleur de texte
27:59
qui sera complètement transparente donc on va utiliser du noir avec l'opacités
28:04
de 0 pour être sûr que vraiment notre texte ne soit pas visible impeccable maintenant j'aimerais bien que les
28:10
utilisateurs qui ont déjà vu la série puis cliquez sur ces éléments là on va même mettre un curseur pointeur pour
28:15
révéler le spoiler donc je vous laisse essayer de le faire sans forcément vous donner des indications et on corrigant ensemble
28:22
juste après alors maintenant on va corriger ça ensemble donc l'idée c'est de détecter
28:27
quand on clique sur les spoilers et ensuite on fera un traitement donc là on dans cette phrase là on a déjà une
28:34
partie de l'algorithme qui se décide quand on clique sur tous les spoilers ça veut dire qu'il me faut d'abord tous les
28:39
spoilers donc je peux faire un quarry selector all et à les sélectionner tous les éléments qui ont la classe spoiler
28:45
maintenant qu'est-ce que je vais faire je veux écouter l'événement clic dessus donc on fera un fort reach parce que je
28:51
ne peux pas faire directement à des ventes sur une collection et on va récupérer chaque spoiler
28:57
individuellement pour chaque spoiler on va rajouter un lisseur et on va écouter le clic lorsque je clique je vais avoir
29:04
une fonction qui prend en paramètre l'événement qu'est-ce qu'on veut faire maintenant on veut révéler le texte on a deux
29:10
solutions soit on rajoute une classe supplémentaire qui ferait le révil soit tout simplement on peut se contenter de retirer la classe donc nous c'est cette
29:18
seconde option que l'on va prendre donc ici je voulais dire sur le spoiler c'est l'avantage d'être dans la boucle je peux
29:24
utiliser cette variable là mais je pourrais tout aussi bien utiliser un e point courant target ça aurait le même
29:29
effet et je vais lui dire de prendre la classe liste et de venir supprimer la classe spoiler
29:36
voilà si maintenant je clique sur un élément hop on voit que ça révèle le spoiler si on voulait un petit effet de
29:44
rival un peu sympa on pourrait lui préciser que tout l'Espagne ont une transition sur le background ou sur
29:50
toutes les propriétés de 300 millisecondes et dans ce cas là lorsque je clique voilà on a cet effet de rival
29:56
si on se dit que l'utilisateur lorsqu'il clique sur un spoiler on veut révéler tous les spoilers à la fois on peut
30:02
changer un petit peu notre code n'hésitez pas à essayer par vous-même et ensuite je vous donne la solution
30:08
donc la solution c'est de séparer un petit peu les choses donc d'abord il nous faudra la liste des éléments qui
30:13
ont la classe spoiler donc on va appeler ça spoiler ensuite on va se dire je me crée une
30:20
fonction qui va révéler les spoilers donc cette fonction va l'appeler revival spoiler et on va lui dire de faire un
30:28
parcours de tous les éléments ici donc on fera un spoiler point for reach ça
30:33
prendre un paramètre les spoilers et pour chaque spoiler je ferai un classe list et je ferai le code que j'avais
30:40
fait actuellement dans mon liceneur et on supprime la classe spoiler voilà donc
30:45
là j'ai ma fonction que je vais pouvoir utiliser maintenant je peux parcourir l'ensemble de mes éléments encore une
30:51
fois et lui dire lorsque je clique dessus je veux que tu utilises la méthode Revil spoiler donc à ce niveau
30:57
là je vais plutôt lui passer cette méthode là si je sauvegarde maintenant on voit que lorsque je clique tous les
31:03
spoilers sont révélés et voilà pour ce petit exemple là vous allez le voir finalement avec ces deux choses que l'on
31:09
a vu jusqu'à maintenant on va pouvoir faire une grande partie des opérations qui sont intéressantes sous javascript très souvent bah on va dire lorsque tu
31:16
cliques sur quelque chose mais on va déc prochain comportement et on va manipuler le dôme par exemple si on a un bouton
31:22
qui permet de charger plus d'articles mais qu'on clique sur ce bouton on va pouvoir rajouter un petit lodeur donc ça
31:28
c'est un manipulant d'hommes ensuite on va pouvoir faite et réinjecter les articles dans le DOM et donc finalement
31:34
ce n'est qu'une combinaison de des ventes
31:39
et du coup je vous donne rendez-vous dans les prochains chapitres
