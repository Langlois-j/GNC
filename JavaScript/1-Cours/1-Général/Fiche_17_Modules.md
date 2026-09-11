# Apprendre le JavaScript : Appel HTTP avec fetch()

Video : https://www.youtube.com/watch?v=DJewHNOFqD0

## Transcription

bienvenue dans ce nouveau chapitre nous
0:01
allons parler du système de module donc
0:03
lorsque l'on va écrire pas mal de
0:04
JavaScript ça va être intéressant de
0:06
pouvoir séparer notre code dans
0:08
différents fichiers pour pouvoir nous
0:09
organiser et éviter d'avoir des lignes
0:11
et des lignes des lignes à lire plus
0:12
tard donc c'est là que le système de
0:14
module intervient donc dans notre cas on
0:16
aimerait bien par exemple créer une
0:18
fonction somme qui permet de faire la
0:19
somme sur les tableaux et de manière
0:21
générale sauvegarder quelque part toutes
0:22
les fonctions utiles sur les tableaux
0:24
donc on va devoir créer des fichiers
0:26
javascript séparés ou plutôt que de
0:28
l'écrire directement dans notre HTML on
0:30
va l'écrire un nouveau fichier et on va
0:32
l'appeler eurer.js pourquoi eurer parce
0:36
que dedans on va mettre toutes les
0:37
fonctions qui concernent les tableaux à
0:39
l'intérieur je vais créer une constante
0:41
somme et je vais lui dire que ça sera
0:43
une fonction qui prendra un paramètre
0:44
des éléments et qui utilisera la méthode
0:47
rieuse donc on fera un item.redius et je
0:51
lui demanderai de prendre un premier
0:52
paramètre l'accumulateur chaque
0:54
item et de retourner l'accumulateur
0:57
auquel on rajoute l'item et je donne la
0:59
valeur 0
1:00
donc je passe un petit peu vite dessus
1:01
parce que ça on l'a déjà vu dans le
1:03
chapitre précédent
1:05
maintenant je me dis j'aimerais bien
1:06
utiliser cette méthode somme dans mon
1:08
JavaScript alors au niveau de mon
1:10
index.tml je vais modifier cette partie
1:12
script et rajouter une attribut type et
1:16
lui dire que ces deux types modules
1:17
c'est important vous ne pouvez pas
1:19
utiliser les modules en dehors
1:20
d'inscrire de type module si vous êtes
1:22
sur d'autres environnements on verra les
1:25
spécificités de chaque environnement
1:26
mais en tout cas côté navigateur il faut
1:27
faire ça de cette manière là
1:30
ensuite dans mon ep.js il va falloir
1:32
spécifier ce que je souhaite exporter
1:34
qu'est-ce que je souhaite rendre
1:35
disponible à l'extérieur pour cela on va
1:38
utiliser le mot clé exporte juste avant
1:40
la définition de la constante donc là on
1:43
est en train de dire dans ce fichier
1:44
JavaScript j'exporte une constante qui
1:46
s'appelle somme ce qu'il y a après un
1:49
porte peu maintenant dans mon index.html
1:52
je peux utiliser une porte je vais
1:54
ensuite utiliser des accolades et
1:57
récupérer seulement les variables qui
1:58
m'intéressent qui ont été exportés au
2:00
préalable donc moi dans mon cas je vais
2:02
lui dire je veux importer somme
2:05
ensuite on va mettre from et on va
2:07
mettre un chemin qui sera le chemin vers
2:09
le fichier JavaScript relatif à notre
2:12
fichier courant donc moi ça sera dans le
2:14
même dossier et on mettra heure et point
2:16
JS le chemin devra commencer par un
2:19
point si c'est un chemin relatif ou
2:22
commencez par un slash si c'est un
2:24
chemin absolu et ça pourra aussi être
2:25
une URL si jamais on souhaite exporter
2:27
quelque chose depuis un tout autre nom
2:30
de domaine pour l'instant nous on va
2:32
dire simplement je veux charger le
2:33
fichier
2:34
ep.js et extraire la variable exportée
2:38
somme maintenant je peux faire un
2:40
console.log
2:42
et récupérer somme et je lui demande de
2:45
faire la somme d'un tableau qui
2:46
contiendrait 12 et 23 et 19 si je fais
2:51
ça je vois bien que ça me donne 54 si
2:54
dans mon ep.js je me décide de créer une
2:56
nouvelle constante par exemple on va
2:58
l'appeler Elo et cette constante elle
3:01
fait un console.log de vélo
3:03
mais si j'essaie de l'importer dans mon
3:06
index pour HTML
3:08
ça ne va pas fonctionner normalement mon
3:10
éditeur devrait le souligner on voit que
3:12
là il ne le fait pas mais on nous dit
3:13
bien il y a un problème le module ep.js
3:17
ne fournit pas d'export pour hello parce
3:20
que on n'a pas de export si on veut que
3:22
ça fonctionne il faudrait écrire exporte
3:24
à ce niveau-là donc on peut exporter
3:27
n'importe quoi on peut exporter des
3:29
fonctions
3:32
on peut exporter des classes et
3:35
finalement tout ce que l'on peut mettre
3:36
dans une variable on peut l'exporter le
3:39
nom de l'export sera automatiquement le
3:41
nom de la variable
3:42
ensuite quand on l'importe on peut
3:44
choisir de le renommer un des problèmes
3:46
que l'on peut avoir c'est que par
3:47
exemple SEM serait défini aussi dans un
3:49
autre fichier si vous voulez changer son
3:51
nom vous pouvez écrire un espace AZ et
3:54
donner un nouveau nom somme par exemple
3:56
maintenant dans ce fichier courant on
3:59
pourra utiliser cette méthode là de
4:01
cette manière là
4:03
donc ça ça peut être utile pour éviter
4:04
les conflits entre les noms de variables
4:06
si on a plusieurs fichiers javascript
4:08
qui exportent la même chose un autre
4:11
détail on peut choisir de toute exporter
4:13
dans une seule grosse variable pour cela
4:15
on va écrire étoile ASE et on va par
4:19
exemple l'appeler a dans ce cas-là ça va
4:22
nous créer un gros objet qui va
4:24
s'appeler a qui va contenir tous les
4:25
exports de notre fichier eurez pointjs
4:27
si je veux faire la somme mais je peux
4:30
refaire a point seul et lui dire je veux
4:33
faire la somme en mettant de valeur et
4:36
dans ce cas là ça me permettra
4:38
d'utiliser les choses si je veux dire
4:40
bonjour ben je peux faire un hello et
4:42
dans ce cas là ça me permet de dire
4:43
bonjour
4:45
de manière générale je ne vous conseille
4:46
pas forcément trop d'utiliser ça moi je
4:49
vous conseille de n’importer que ce dont
4:51
vous avez besoin c'est plus logique d'un
4:53
point de vue code et ça permet d'avoir
4:55
une meilleure structure mais c'est
4:56
toujours intéressant de savoir que ça
4:58
existe
4:59
vous avez aussi la possibilité dans un
5:01
fichier de faire un export par défaut
5:03
alors on va créer un nouveau fichier que
5:06
l'on va appeler et le point JS
5:08
à l'intérieur de ce fichier vous pouvez
5:10
faire un export et mettre ensuite le mot
5:12
clé des fautes et ensuite vous mettez
5:15
votre fonction ou votre valeur nous on
5:18
va mettre une fonction qui fait console
5:19
point log de hello je sais j'insiste
5:23
mais il faut vraiment dire bonjour
5:24
maintenant dans votre index.html lorsque
5:28
vous importez ce module là vous allez
5:30
l'importer un petit peu différemment
5:31
vous allez faire un innport vous n'allez
5:34
pas avoir besoin de mettre des accolades
5:36
vous allez directement mettre le nom que
5:37
vous voulez nous on va l'appeler hello
5:39
et après vous mettez le chemin vers le
5:42
fichier et le point JS si vous faites
5:45
maintenant appel à cette méthode là ça
5:48
affichera bonjour vous n'êtes pas du
5:50
tout contraint au niveau de cette
5:52
import-là vous pouvez mettre le nom que
5:53
vous voulez au niveau de
5:55
au niveau de cette import si j'ai envie
5:58
de l'appeler au revoir je peux l'appeler
6:00
au revoir
6:02
et ça donnera le même résultat
6:04
enfin vous pouvez avoir dans un même
6:07
fichier un des exports qui sont nommés
6:09
et des exports par défaut donc par
6:12
exemple ici
6:13
je peux avoir un export de la Somme et
6:16
le dire en fait le la fonction qui fait
6:19
et l'eau ça sera un export par défaut
6:21
alors on pourrait être embêté on
6:23
pourrait se dire mais là comment quand
6:25
je vais faire pour faire les deux je
6:26
pourrais lui dire mais j'ai envie hop
6:28
d'avoir l'export somme et l'export aussi
6:32
du hello et de le faire en deux fois
6:37
donc dans ce cas là ça fonctionnerait et
6:39
vous auriez bien le résultat ce que vous
6:41
pouvez aussi écrire c'est lui dire ici
6:43
je veux récupérer le défolt et lui
6:45
donner un nom ça va marcher comme ça
6:48
aussi ça donnera le même résultat ça
6:50
vous évite d'écrire de lignes c'est un
6:52
petit peu un petit peu plus rapide donc
6:54
si vous avez à la fois des exports
6:55
nommés et des exports et un export par
6:57
défaut vous pouvez l'utiliser de cette
6:59
manière là
7:00
alors je ne l'ai pas forcément précisé
7:02
mais il est tout à fait possible d'avoir
7:04
un import dans un autre module par
7:06
exemple on peut s'imaginer que à ce
7:08
niveau là dans le module de tableau
7:10
j'importe
7:12
Hello
7:14
from donc mon fichier
7:17
et ensuite je peux choisir d'exporter
7:19
cette constante là je fais un export
7:21
constant et l'eau et je vais être embêté
7:25
parce que du coup je l'ai déjà appelé
7:27
l'eau donc ça on va l'appeler hello 2 et
7:29
voilà donc là en fait j'utilise un
7:32
import et je le réexporte derrière si
7:36
maintenant je reviens dans mon index.tml
7:38
mais je peux à la fois importer somme et
7:40
donc on peut avoir plein plein de
7:42
modules pour séparer les choses et faire
7:44
des traitements donc si dans heure et on
7:46
a besoin d'une méthode pour une autre
7:47
méthode on peut le faire il y a
7:49
d'ailleurs une syntaxe un petit peu plus
7:50
rapide si vous voulez réexporter quelque
7:53
chose vous pouvez écrire ici export et
7:56
vous lui dites je veux exporter le
7:57
défolt as et l'eau comme ça vous
8:00
réexporter quelque chose depuis un autre
8:01
fichier ça ça peut parfois être
8:03
intéressant quand vous avez un fichier
8:05
Carrefour c'est à dire que vous allez
8:06
créer des fichiers qui vont correspondre
8:08
différentes méthodes et avoir un fichier
8:10
que vous allez appeler function et qui
8:13
va réexporter les différentes méthodes
8:14
de différents fichiers c'est après c'est
8:16
une question mais voilà c'est
8:18
intéressant de savoir que vous pouvez
8:19
réexporter quelque chose si vous le
8:21
souhaitez
8:23
ensuite il est possible d'importer des
8:25
modules de manière synchrone donc on va
8:27
retirer ça et ici on va lui dire
8:29
j'aimerais bien faire un inporte et
8:32
plutôt que de mettre un espace et de
8:34
mettre le reste on va mettre entre
8:35
parenthèses le chemin vers le fichier
8:37
donc nous ça serait ici ré.js
8:42
si je sauvegarde ça on reconnaît quand
8:44
on a ici notre petit ami les promesses
8:46
cette promesse a été complétée donc on
8:49
va regarder ce qu'elle nous donne donc
8:50
on va faire un veine et on va lui donner
8:53
demander une fonction et à l'intérieur
8:55
de cette fonction je vais lui demander
8:57
de m'afficher les arguments donc pour
8:59
cela on va lui dire
9:01
extrêmement les différents arguments et
9:03
voilà donc si je regarde d'abord on a
9:06
notre promesse qui est exécutée et ça
9:08
nous renvoie un tableau avec un module
9:11
si je regarde cette valeur 0 je retrouve
9:14
ici mon hello et mon seum donc on peut
9:16
utiliser la déstructuration à ce niveau
9:18
là mais je vais lui dire moi ce qui
9:20
m'intéresse c'est simplement de
9:22
récupérer hello et ensuite je vais lui
9:24
demander de faire un 1 et l'eau
9:28
voilà et dans ce cas là ça me permet
9:31
d'accéder à ça l'intérêt c'est qu'on ne
9:33
charge ce JavaScript que quand on en a
9:35
besoin il est aussi possible évidemment
9:37
d'utiliser la syntaxe avec le wait donc
9:39
l'avantage c'est que côté navigateur
9:41
quand on est dans un script qui est de
9:42
type module on a la possibilité de faire
9:44
des tops level wait c'est à dire qu'on
9:46
peut lui dire ici j'ai envie de faire un
9:47
const et l'eau et je peux directement
9:50
utiliser un awate de l'inport de ré.js
9:55
et ensuite je peux lui demander de faire
9:58
la méthode hello et ça ça va fonctionner
10:00
nativement
10:03
si jamais vous n'avez pas le support des
10:05
tops levels think vous pouvez utiliser
10:07
ce qu'on appelle des IFE ce sont des
10:09
fonctions qui s'auto exécutent donc pour
10:11
cela vous pouvez mettre en parenthèse
10:13
créer une fonction voilà et l'auto
10:16
appeler et ensuite dire que cette
10:18
fonction est à synchrone
10:20
et comme ça hop vous pouvez ensuite à
10:23
l'intérieur mettre votre wait sans avoir
10:24
de souci c'est une autre technique si
10:26
jamais vous n'avez pas accès au top
10:27
level wait et là on voit que ça nous
10:30
donne aussi et l'eau en console donc
10:32
cette seconde de syntaxe au niveau de
10:34
l'import elle va plutôt être utile côté
10:36
navigateur parce que ces côtés
10:38
navigateurs on veut pas trop charger de
10:39
ressources côté serveur on va être moins
10:42
gêné dans le sens où lorsque le serveur
10:43
est lancé on va pouvoir charger toutes
10:45
les librairies dont on a besoin donc
10:47
c'est vrai que ce wait de inport vous
10:49
allez moins se le rencontrer côté
10:51
serveur on va être plus sur une syntaxe
10:53
un petit peu plus classique où on aura
10:55
directement les imports de cette manière
10:57
là si vous avez besoin de plus
10:59
d'informations sur la syntaxe des
11:01
modules je vous renvoie sur la
11:03
documentation de MDN sur import il y a
11:06
beaucoup beaucoup d'autres petits
11:07
détails ça peut être intéressant de les
11:09
regarder mais là je vous ai vraiment
11:10
donné la basse retenez bien que côté
11:12
navigateur en tout cas vous devez mettre
11:14
un petit peu module on verra que côté
11:16
note JS et dans les autres
11:17
environnements c'est un petit peu
11:18
différent mais côté navigateur vous ne
11:20
pouvez pas utiliser les modules si vous
11:21
avez pas un script de type module donc
11:24
si vous essayez et que vous avez des
11:25
erreurs pensez à vérifier ça donc
11:27
j'espère que ce chapitre vous a plu et
11:29
je vous donne rendez-vous dans le
11:30
chapitre suivant