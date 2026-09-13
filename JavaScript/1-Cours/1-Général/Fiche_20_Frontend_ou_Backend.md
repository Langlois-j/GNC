# Fiche 20 : Frontend ou Backend ?

## 📌 Deux directions possibles avec JavaScript
Une fois les bases du langage acquises, deux grandes voies s'offrent pour la suite :
- **JavaScript côté navigateur (frontend)** : ajouter de l'interactivité à une page web (le navigateur exécute le code).
- **JavaScript côté serveur (backend)**, via des technologies comme **Node.js** : lire des fichiers, exécuter d'autres processus, répondre à des requêtes HTTP, etc. (le serveur exécute le code).

📌 Il n'y a pas d'ordre imposé entre les deux — on peut commencer par l'un, par l'autre, étudier les deux, ou se concentrer sur un seul selon ses objectifs.

## 🛠️ JavaScript côté navigateur (frontend)
Permet notamment de :
- détecter les interactions utilisateur (clics, défilement...) ;
- générer ou modifier des éléments HTML dynamiquement ;
- créer des composants interactifs : animations d'apparition au défilement, fenêtres modales (afficher/masquer une `div` au clic ou à la touche Échap), menus qui suivent la section affichée ("scroll spy")...

## 🛠️ JavaScript côté serveur (backend)
Avec Node.js notamment, permet de :
- lire/écrire des fichiers, appeler d'autres outils/processus (ex : convertir des vidéos) ;
- créer des bots pour des systèmes de messagerie (écouter les nouveaux messages, y répondre) ;
- créer un **serveur web** qui répond aux requêtes HTTP (voir [[Fiche_16_Appel_HTTP_fetch]]) — par exemple : recevoir une requête sur `/blog`, aller chercher les derniers articles en base de données, générer la page HTML et la renvoyer à l'utilisateur.

## 💡 Comment choisir
Pas de mauvais choix : regarder les premiers chapitres de chaque piste (frontend / backend) permet de se faire une idée concrète de ce qui plaît le plus avant de s'engager plus loin dans l'une ou l'autre.

## ✅ À retenir
Le langage JavaScript est le même des deux côtés — ce qui change, c'est l'environnement d'exécution (navigateur vs Node.js) et donc les possibilités disponibles : interactivité visuelle côté navigateur, accès système/fichiers/réseau côté serveur.
