# Fiche 16 : Appels HTTP avec `fetch`

## 📌 Rôle de `fetch`
`fetch` permet de faire des appels HTTP (contacter un serveur) directement en JavaScript. Côté navigateur, c'est le navigateur qui exécute la requête ; le principe est le même dans d'autres environnements (Node.js, etc.). `fetch` renvoie nativement une **`Promise`** (voir [[Fiche_15_Promises]]).

## 🛠️ Requête simple : `fetch(url)`
```javascript
const r = fetch("https://jsonplaceholder.typicode.com/users");
console.log(r);   // Promise <pending>, puis <fulfilled>
```
`fetch` prend en premier paramètre l'URL à appeler, et un second paramètre **optionnel** contenant les options de la requête (méthode, en-têtes, corps...).

## 🛠️ L'objet `Response`
Une fois la promesse résolue, on obtient un objet `Response` :
```javascript
fetch("https://jsonplaceholder.typicode.com/users")
    .then((r) => console.log(r));
```
Quelques propriétés utiles de cet objet :
| Propriété | Rôle |
|---|---|
| `ok` | `true` si le statut de réponse est dans la plage **200–299** (succès) |
| `status` | Code HTTP numérique de la réponse (`200`, `404`, ...) |
| `redirected` | `true` si la requête a suivi une redirection |
| `headers` | En-têtes de la réponse |
| `body` | Flux brut du contenu de la réponse |

## 🛠️ Récupérer le contenu : `.text()` et `.json()`
Le corps de la réponse n'est pas lu directement — il faut appeler une méthode dédiée, qui renvoie **elle aussi une promesse** :
```javascript
fetch("https://jsonplaceholder.typicode.com/users")
    .then((r) => r.text())          // renvoie une promesse du texte brut
    .then((body) => console.log(body));

fetch("https://jsonplaceholder.typicode.com/users")
    .then((r) => r.json())          // renvoie une promesse de l'objet JSON parsé
    .then((body) => console.log(body));
```
📌 `.json()` est à privilégier quand le serveur répond en JSON : on obtient directement un objet/tableau JavaScript exploitable, sans avoir à parser soi-même.

## ⚠️ Toujours vérifier `r.ok`
Un serveur peut répondre en JSON même en cas d'erreur (ex : `404`) — `fetch` ne rejette **pas** automatiquement la promesse pour un statut d'erreur HTTP. Il faut vérifier `r.ok` explicitement avant de traiter la réponse :
```javascript
async function fetchUsers() {
    const r = await fetch("https://jsonplaceholder.typicode.com/users");
    if (r.ok) {
        const donnees = await r.json();
        return donnees;
    }
    throw new Error("Impossible de contacter le serveur");
}

fetchUsers()
    .then((utilisateurs) => console.log(utilisateurs))
    .catch((erreur) => console.log(erreur));
```
📌 Ici, `fetchUsers` étant `async`, elle renvoie une promesse ; on peut donc directement la consommer avec `.then()`/`.catch()` (ou `await` dans une autre fonction `async`).

## 🛠️ Envoyer des données : méthode `POST`
Par défaut, `fetch` utilise la méthode `GET`. Pour envoyer des données (créer une ressource, remplir un formulaire...), on passe un second paramètre :
```javascript
fetch("https://jsonplaceholder.typicode.com/posts", {
    method: "POST",
    headers: {
        "Accept": "application/json",         // ce qu'on accepte en retour
        "Content-Type": "application/json",   // le format de ce qu'on envoie
    },
    body: JSON.stringify({ title: "Mon premier article" }),
})
    .then((r) => r.json())
    .then((body) => console.log(body));   // le serveur renvoie l'objet créé (avec un id)
```
💡 `JSON.stringify(objet)` transforme un objet JavaScript en chaîne JSON ; `JSON.parse(texte)` fait l'inverse. Ce sont les deux seules méthodes de l'objet global `JSON`.

## 🛠️ Lire un en-tête de réponse
`r.headers` n'est pas un simple objet JavaScript, mais un objet spécial doté d'une méthode `.get()` :
```javascript
fetch("https://jsonplaceholder.typicode.com/users")
    .then((r) => console.log(r.headers.get("content-type")));
// null si l'en-tête demandé n'existe pas
```

## 🛠️ Combiner plusieurs `fetch` : `Promise.race`
```javascript
const p1 = fetch("https://jsonplaceholder.typicode.com/posts?_limit=5");
const p2 = fetch("https://jsonplaceholder.typicode.com/users?_limit=5&_delay=2000");

Promise.race([p1, p2])
    .then((r) => r.json())
    .then((resultat) => console.log(resultat));   // le premier arrivé (ici les posts)
```
⚠️ `Promise.race` ne fait qu'ignorer les promesses non gagnantes : les requêtes perdantes **continuent de s'exécuter** en arrière-plan (visible dans l'onglet réseau du navigateur) même si leur résultat n'est plus utilisé — ce n'est pas une annulation, juste un résultat ignoré.

## 🛠️ Annuler une requête : `AbortController`
```javascript
const a = new AbortController();

const p1 = fetch(url1, { signal: a.signal });
const p2 = fetch(url2, { signal: a.signal });

Promise.race([p1, p2])
    .then((r) => r.json())
    .then((body) => {
        console.log(body);
        a.abort();   // annule toutes les requêtes connectées à ce signal, encore en cours
    });
```
📌 On crée un `AbortController`, on relie sa propriété `signal` à l'option `signal` de chaque `fetch` que l'on souhaite pouvoir annuler, puis on appelle `.abort()` quand on veut y mettre fin. La requête annulée n'obtient alors aucun statut de réponse (coupée côté navigateur).

## ✅ À retenir
`fetch(url, options)` renvoie une promesse d'un objet `Response`. Toujours vérifier `r.ok` avant d'utiliser `.json()`/`.text()` (eux-mêmes asynchrones). Pour `POST`, préciser `method`, les en-têtes `Content-Type`/`Accept`, et sérialiser le `body` avec `JSON.stringify`. `Promise.race` ne coupe pas les requêtes perdantes ; utiliser un `AbortController` si on veut réellement les annuler.
