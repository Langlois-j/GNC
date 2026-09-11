# Apprendre le JavaScript : L objet Date

Video : https://www.youtube.com/watch?v=O41U3fOOhvA

## Transcription

salut et bienvenue dans ce nouveau chapitre où je vous propose de parler un petit peu orientation et de vous guider vers ce que vous pouvez apprendre maintenant donc tout d'abord je tiens à
0:088 secondesvous féliciter d'être arrivé jusqu'au bout des bases du langage je n'étais pas forcément évident mais maintenant il est temps de découvrir comment vous allez pouvoir utiliser le javascript pour des
0:1515 secondescas concrets donc vous avez deux choix qui s'offrent à vous soit vous pouvez faire déjà un skate côté navigateur c'est ce qui va vous permettre de rajouter des interactions sur une page web c'est aussi ce que l'on appelle en
0:2323 secondesgénéral le fontaine soit vous pouvez faire du javascript côté serveur donc avec des technologies comme note JS ce qui va vous permettre soit de créer des
0:3131 secondesoutils par exemple en mode discord ou un bot pour un système de messagerie des outils qui vont permettre de traiter des fichiers ou carrément même un serveur
0:3939 secondesweb qui va permettre de répondre à des requêtes HTTP donc pour rappel on avait déjà parlé de ce que c'était le HTTP justement avec le JavaScript on va
0:4747 secondespouvoir interpréter la requête et générer la page qui correspond donc là il y a pas forcément d'ordre moi j'ai choisi de mettre ici le jasque côté navigateur en premier mais c'est parce
0:5555 secondesque forcément je devais faire un choix au niveau de l'affichage mais vous pouvez commencer par l'un ou par l'autre et ça n'a pas d'importance et vous pouvez aussi voir les deux si les deux
1:031 minute et 3 secondesvous intéressent ou n'en voir qu'un ça dépend de ce que vous voulez faire un petit peu plus pour être un petit peu plus en profondeur sur le jaski de côté navigateur ça va vous permettre de
1:121 minute et 12 secondesrajouter des interactions sur la page de détecter par exemple lorsque l'utilisateur va cliquer sur un élément de générer des éléments HTML si je vous donne quelques exemples ce sont des
1:201 minute et 20 secondesexemples de TP que l'on fera dans cette partie là par exemple sur cette page là j'ai un système d'apparition donc lorsque je défile dans ma page on voit que les éléments apparaissent avec un
1:281 minute et 28 secondespetit effet comme ça d'animation donc ça ça va pouvoir être piloté par le JavaScript on pourra aussi utiliser le Jask script pour créer des composants un petit peu plus avancés par exemple on a
1:371 minute et 37 secondesenvie de créer une boîte modale même si aujourd'hui on a un élément HTML pour faire ça et on va pouvoir créer un élément HTML qui sera une div et quand
1:451 minute et 45 secondesje vais cliquer sur un bouton pouf ça va s'afficher lorsque j'appuierai avec mon clavier sur échappe la modèle donc tout ça ça sera rendu possible par
1:531 minute et 53 secondesdu javascript un autre exemple c'est un système de scroll spy c'est à dire que lorsque l'on défile on va automatiquement détecter la section sur laquelle on est et souligner le bon
2:012 minutes et 1 secondeélément dans le menu et vous avez comme ça des tonnes et des tonnes d'exemples de choses que l'on pourra faire en Javascript et du coup ça c'est déjà
2:082 minutes et 8 secondesinscrit de côté navigateur c'est le navigateur qui va exécuter votre code donc ensuite on verra le Javascript côté
2:152 minutes et 15 secondesserveur donc nous vu qu'on s'intéresse au web c'est essentiellement pour créer un serveur web mais vous allez voir que avec le Javascript côté serveur vous
2:222 minutes et 22 secondesallez pouvoir par exemple lire des fichiers vous allez pouvoir aussi exécuter d'autres processus donc on pourrait tout à fait s'imaginer utiliser le javascript pour récupérer des vidéos
2:302 minutes et 30 secondesappeler un outil pour les convertir et les sortir dans un autre dossier on peut aussi s'imaginer créer des bottes pour différents systèmes de messagerie
2:382 minutes et 38 secondesécouter quand de nouveaux messages arrivent et pouvoir envoyer des informations pour pouvoir poster de nouveaux messages ou répondre à des questions utilisateurs et on pourra
2:462 minutes et 46 secondesaussi et c'est surtout ce qui va nous intéresser créer des serveurs Web pour répondre à ta requête HTTP par exemple quand je fais un appel à slashblog ben
2:532 minutes et 53 secondesje vais aller me connecter à une base de données récupérer les derniers articles générer la page html et renvoyer ça pour que l'utilisateur voit un blog qui fonctionne donc ça ça sera rendu
3:023 minutes et 2 secondespossible par le Javascript côté serveur si vous ne savez pas trop ce qui vous intéresse ce que vous pouvez faire c'est regarder les premiers chapitres de chacun de ces de ces actions là et voir
3:113 minutes et 11 secondesce qui vous intéresse et ensuite vous faire vous faites votre propre opinion et vous commencez donc je vous donne rendez-vous dans un une de ces sections