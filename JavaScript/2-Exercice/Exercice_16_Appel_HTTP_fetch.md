# Exercice 16 : Appels HTTP avec `fetch`

On utilisera l'API de test `https://jsonplaceholder.typicode.com` pour tous les exercices.

## Exercice 1 — Récupérer et vérifier
Écrivez une fonction `getPost(id)` qui :
1. Appelle `https://jsonplaceholder.typicode.com/posts/{id}`.
2. Vérifie `r.ok` avant de continuer.
3. Renvoie le post au format JSON si tout s'est bien passé.
4. Lève une erreur explicite (`throw new Error(...)`) si `r.ok` est `false`.

Testez avec un id valide (`1`) puis un id invalide (`99999`) pour vérifier les deux chemins.

## Exercice 2 — Créer une ressource
Écrivez une fonction `creerPost(titre, contenu)` qui envoie une requête `POST` vers `https://jsonplaceholder.typicode.com/posts` avec un body JSON `{ title, body }`, les bons en-têtes, et renvoie la réponse du serveur (qui inclut un nouvel `id`).

## Exercice 3 — Le premier arrivé
En utilisant `Promise.race`, contactez en parallèle :
- `https://jsonplaceholder.typicode.com/users?_limit=3`
- `https://jsonplaceholder.typicode.com/comments?_limit=3&_delay=1500`
et affichez uniquement le résultat de la requête la plus rapide.

## Exercice 4 — Annulation
Reprenez l'exercice 3 en ajoutant un `AbortController` : dès que le premier résultat arrive, annulez explicitement l'autre requête encore en cours. Vérifiez (via l'onglet réseau du navigateur, si vous testez dans un navigateur) que la requête perdante est bien interrompue plutôt que de continuer en arrière-plan.
