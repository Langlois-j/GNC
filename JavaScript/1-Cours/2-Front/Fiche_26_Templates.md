# JavaScript cote navigateur : Templates

Video : https://www.youtube.com/watch?v=7e4EMDOeiYE

## Transcription

alors bienvenue dans cette nouvelle
0:01
vidéo aujourd'hui je vous propose de
0:02
parler ensemble du système de template
0:04
donc c'est à la fois quelque chose qui
0:06
va nous servir dans l'HTML mais aussi
0:07
dans le Javascript un des problèmes que
0:09
l'on rencontre assez souvent en
0:10
Javascript c'est parfois on a besoin de
0:11
copier des gros morceaux de code on a vu
0:13
dans l'exemple que l'on a fait dans la
0:14
partie TP on était obligé de copier
0:17
toute cette structure HTML directement
0:18
sous forme d'une simple chaîne de
0:20
caractères ce qui n'est pas forcément
0:21
idéal et c'est là que les template vont
0:23
nous aider les template vont nous
0:25
permettre de d'insérer à une structure
0:26
HTML directement dans notre page donc
0:29
typiquement on utilisera un tag template
0:31
en lui donnera un ID pour pouvoir le
0:32
récupérer plus facilement ensuite dans
0:34
notre JavaScript et à l'intérieur on
0:35
mettra la structure HTML que l'on
0:37
souhaite pouvoir réutiliser attention il
0:39
y a quelques petites particularités
0:41
cette structure HTML est complètement
0:43
ignorée du dôme donc typiquement si je
0:44
me rends ici sur ma page et que on
0:47
s'imagine dans mon index.html je crée
0:49
une DIV ou je mets un hello world mais
0:52
par défaut ça te dit va se voir elle est
0:55
ici mais si on la met dans une balise
0:56
template
0:59
comme ceci mais dans ce cas là cet
1:01
élément là va être retiré du flux de la
1:03
même manière tout ce qui est à
1:05
l'intérieur ne sera pas interprété donc
1:06
elle le CSS ne sera pas appliqué et en
1:09
plus on n'aura pas de vérification ce
1:10
qui nous permet par exemple de créer un
1:12
TR en plein milieu d'une structure sans
1:14
forcément que l'HTML nous dise ouais
1:16
ouais mais attends il faudrait
1:17
normalement une table donc nous dans
1:19
notre cas ça pourrait être très utile
1:20
pour toute la partie typiquement de
1:22
notre to do list qui contenait toute la
1:24
structure de base plutôt que de l'avoir
1:25
dans la dans la partie JavaScript on
1:27
peut créer un template donc nous ici on
1:29
créerait un template on lui donnerait un
1:32
ID particulier donc on l'appellerait
1:33
tout doux list tirer l'ayant donc soyez
1:36
assez créatif sur le nom de l'ID pour
1:38
pouvoir le retrouver plus facilement et
1:40
ensuite vous fermez cette partie
1:41
template
1:42
donc ce template là vous pouvez le
1:44
mettre où vous voulez dans votre code ça
1:46
n'a pas d'importance il est complètement
1:47
ignoré par les navigateurs donc je me
1:49
dis que d'ailleurs hop là histoire
1:51
d'être un petit peu plus clair et un
1:53
petit peu plus simple on va plutôt
1:55
mettre ça en dehors de la section moi
1:58
j'aime bien avoir les template au
1:59
premier niveau en général juste avant la
2:00
fin de la page et là c'est vraiment une
2:02
convention personnelle avant tout une
2:05
fois qu'on a ce template on va pouvoir
2:06
l'utiliser dans notre JavaScript alors
2:07
avant de l'utiliser dans notre code réel
2:09
je vous propose un exemple directement
2:10
depuis la console donc on va commencer
2:12
par récupérer le template en faisant un
2:15
document get élément de byedy où vous
2:17
pouvez faire un quadrice sélecteur ça
2:18
donne la même chose et on va
2:20
sélectionner l'élément qui a cette Idy
2:22
là
2:23
voilà donc on obtiendra alors l'élément
2:26
template si je regarde TPL ça me donne
2:28
bien ça
2:30
donc le template en lui-même de servira
2:32
pas à grand chose mais on a une
2:33
propriété intéressante dessus qui est
2:35
contente contente va nous donner le
2:37
contenu du template et ça sera un objet
2:39
qui est tout nouveau qui est un document
2:41
de fragments ce n'est pas réellement un
2:43
élément HTML mais si vous voulez c'est
2:45
un nœud qui représente une série
2:47
d'éléments enfants donc l'avantage c'est
2:50
que ça se comporte comme un classique et
2:52
on peut par exemple le cloner pour en
2:54
récupérer une copie vous pouvez utiliser
2:56
par exemple clone node avec la propriété
2:59
trou pour pouvoir cloner tous les
3:01
enfants et ça vous donnera un document
3:02
de fragmente qui est différent fragment
3:04
que vous pouvez ensuite rajouter
3:05
n'importe où sur votre page donc je peux
3:07
faire un document de point body point à
3:09
peine et lui demander de la rajouter ce
3:12
fragment là hop comme ceci si je fais ça
3:16
et que je descends un petit peu dans ma
3:18
page on va voir que notre structure est
3:20
bien là donc ça veut dire que ça a été
3:22
capable de rajouter cette structure HTML
3:24
au niveau de notre body si je regarde
3:26
dans la partie élément maintenant on
3:28
voit que à ce niveau là j'ai à la fois
3:30
le formulaire et le main
3:33
l'avantage des documents de fragments
3:34
c'est que contrairement aux éléments on
3:36
n'est pas obligé d'avoir qu'un seul
3:37
enfant on peut avoir un template qui
3:39
contiendrait un élément et un second
3:40
élément donc ça c'est pratique on n'est
3:42
pas obligé de toujours entourer d'une
3:44
DIV ou quelque chose comme ça pour
3:45
pouvoir réutiliser les choses
3:48
en fin dernier petit détail un fragment
3:50
n'existe pas en soi c'est à dire que
3:52
dans la structure HTML finale le
3:54
fragment n'a pas réellement d'importance
3:55
du coup vous ne pouvez pas brancher des
3:58
event lisseur sur un fragment si je
4:00
voulais écouter le clic à la fois sur le
4:02
format et le main je devrais
4:03
sélectionner les chats et les mains et
4:05
venir mettre le comportement sur les
4:06
vrais éléments les documents de
4:08
fragments ne sont pas des éléments HTML
4:10
classiques et c'est tout ce qui à savoir
4:11
sur les template c'est pas plus
4:12
compliqué que ça maintenant imaginons
4:14
qu'on essaie d'utiliser ça dans notre
4:16
système de to-do list parce que là on
4:18
peut faire c'est créer aussi un second
4:19
template qui concernerait chaque élément
4:22
dans notre liste donc on va aller créer
4:23
un template
4:25
on va lui donner l'ID ici to do list
4:28
tiret item et on va mettre notre item
4:31
c'est simplement notre li à ce niveau là
4:33
donc là on va mettre le label ensuite on
4:36
va rajouter le bouton et on va essayer
4:39
de formater sa bière si vous êtes sur
4:41
vscode vous pouvez faire un contrôle
4:42
shiftp et vous tapez format et vous
4:46
cherchez mettre le document en forme ça
4:47
peut vous permettre de réorganiser les
4:48
choses correctement bien que là il fasse
4:51
pas un travail phénoménal voilà donc là
4:54
on amène dans nos deux template donc
4:56
dans notre to do list.js déjà dans notre
4:59
à peine de tout on s'embêtait à mettre
5:01
toute cette structure HTML mais plutôt
5:02
que de faire ça on peut lui dire au
5:04
niveau de l'élément j'aimerais bien
5:06
mettre un clone de notre template donc à
5:09
ce niveau là on ferait un lmment
5:11
à peine on récupérerait un document
5:14
point queris élector ou un get élément
5:18
de by Heidi je préfère gatter les
5:19
membaidi parce que c'est plus précis je
5:21
vais lui dire je récupère ici ce to do
5:24
list
5:26
et ensuite je vais lui dire récupère le
5:28
contenu et clone le nœud et clone le ne
5:32
de manière profonde
5:34
ça me permet ensuite d'enlever cette
5:36
partie iner-html à ce niveau là
5:39
j'aurais actualise la page et on voit
5:40
que ça ne change absolument rien au
5:42
niveau de la structure et mon code
5:43
continue de fonctionner ce que vous
5:45
pouvez faire c'est vous créez une
5:46
fonction pour aller un petit peu plus
5:48
vite par exemple ici je peux faire une
5:50
fonction que je peux appeler clone
5:53
template je lui passerai un paramètre
5:55
l'ID du template et ça ferait cette
5:58
partie là hop comme ceci
6:02
et je vais retourner cette partie là
6:05
voilà l'avantage c'est que dans cette
6:07
partie clone template vous pourriez lui
6:09
dire ben vous faites si l'ID je ne la
6:10
trouve pas dans la page ça provoquerait
6:12
une erreur et à ce niveau là maintenant
6:14
au niveau de mon to-do liste plutôt que
6:16
de faire une ligne qui est aussi longue
6:17
que ça je peux utiliser mon clone
6:19
template
6:21
et je lui passerai simplement l'idy de
6:23
mon template ce qui est un petit peu
6:24
plus court
6:26
de la même façon si je descends dans
6:27
notre to do list item on s'était un
6:29
petit peu embêté à générer les
6:31
différents éléments on est plus obligé
6:33
de faire ça je vais pouvoir lui dire
6:34
j'aimerais bien que tu clones le temps
6:36
plate donc on va créer une variable que
6:39
l'on va appeler fragment et on va lui
6:41
demander de cloner le template et c'est
6:43
le template qui avait comme ID to do
6:46
list item mais dans mais dans ce cas là
6:48
je suis intéressé pour ne récupérer que
6:50
le l.i donc sur les documents de
6:52
fragments si je reviens dans la
6:54
documentation si vous cherchez document
6:56
fragment vous avez quelques méthodes qui
6:58
peuvent être intéressantes dessus vous
7:00
avez des méthodes qui ont entrées aux
7:01
enfants donc là c'est des choses qu'on a
7:03
déjà vu et vous avez le First element
7:05
child donc là on pourrait lui dire bah
7:07
en fait dans ce cas là je ne suis
7:09
intéressé que par le l.i donc ça serait
7:11
le First element child et donc plutôt
7:13
que de récupérer le fragment je
7:15
récupérerai le lie
7:17
pour avoir une meilleure auto-complétion
7:19
n'hésitez pas ici à préciser la valeur
7:20
de retour et dire à ce niveau là ça
7:24
atteint un paramètre qui sera une chaîne
7:25
de caractère qui sera l'ID du template
7:27
et ça nous retournera un document
7:29
fragment voilà donc je reviens dans mon
7:32
tout do list et la particularité c'est
7:34
que du coup tous les éléments qui
7:36
étaient créés manuellement avant je vais
7:38
plutôt avoir besoin de les récupérer
7:39
donc la checkbox ça sera finalement
7:43
1li sur lequel je vais récupérer l'input
7:47
par contre attention il va falloir
7:50
changer les propriétés Heidi et check
7:52
donc là je pourrais dire au niveau de la
7:54
checkbox je veux que tu fasses un set
7:55
attribute tu vas changer l'ID et je veux
7:58
que tu mettes cette Idy là tu vas aussi
8:00
en profiter pour au niveau de check ici
8:03
vérifier si tout doux est complété donc
8:06
si tout doux est compliqué
8:08
je veux que tu rajoutes un cet attribute
8:12
de check et que tu mettes une chaîne de
8:13
caractère vide pour cocher la case donc
8:16
là on a fait la checkbox pour le label
8:19
ça va être la même chose on va récupérer
8:21
grâce au courrier selector le label que
8:23
l'on sauvegardera dans la même variable
8:24
label et on en profitera pour modifier
8:27
la tribu fort en faisant un label point
8:29
7 attribute et en modifiera la tribu
8:32
fort pour mettre l'ID
9:22
[Musique]
9:28
moi je trouve que le principal avantage
9:30
de ça c'est que derrière vous pouvez
9:31
changer la structure HTML de vos
9:33
éléments facilement sans avoir besoin de
9:35
retravailler le Javascript c'est votre
9:37
HTML qui reste maître de piloter la
9:39
structure de vos éléments il faudra par
9:41
contre faire très attention à mettre les
9:43
bonnes classes CSS donc là par exemple
9:45
je vais retirer le X compliquitide
9:48
ne sert à rien parce qu'il sera injecté
9:50
en html pareil la tribu fort ici ne sert
9:53
à rien
9:53
le contenu textuel ben ne sert à rien
9:56
non plus voilà donc faudra vraiment
9:58
penser que cette structure là elle sert
10:00
de base et c'est tout ce qu'elle fait si
10:02
jamais vous décidez par exemple de créer
10:03
deux boutons il faut se dire attention
10:05
ça va rentrer en collision avec la
10:07
todolist qui atteint un bouton à ce
10:08
niveau là donc on utilisera plutôt des
10:10
classes à l'intérieur des templates pour
10:12
pouvoir mieux cibler les éléments au
10:13
niveau de notre JavaScript voilà mais en
10:15
dehors de ça c'est tout ce qui à
10:16
connaître sur cette partie template
