# Correction 16 : Appels HTTP avec `fetch`

## Exercice 1
```javascript
async function getPost(id) {
    const r = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
    if (!r.ok) {
        throw new Error(`Post ${id} introuvable (statut ${r.status})`);
    }
    return await r.json();
}

getPost(1)
    .then((post) => console.log(post))
    .catch((erreur) => console.log(erreur.message));

getPost(99999)
    .then((post) => console.log(post))
    .catch((erreur) => console.log(erreur.message));
// "Post 99999 introuvable (statut 404)"
```
📌 `r.ok` étant `false` pour un `404`, `fetch` lui-même ne rejette jamais la promesse pour ce genre d'erreur HTTP — c'est à nous de le détecter et de transformer ça en erreur explicite avec `throw`.

## Exercice 2
```javascript
async function creerPost(titre, contenu) {
    const r = await fetch("https://jsonplaceholder.typicode.com/posts", {
        method: "POST",
        headers: {
            "Accept": "application/json",
            "Content-Type": "application/json",
        },
        body: JSON.stringify({ title: titre, body: contenu }),
    });
    return await r.json();
}

creerPost("Mon titre", "Mon contenu")
    .then((post) => console.log(post));
// { title: "Mon titre", body: "Mon contenu", id: 101 }
```
⚠️ Piège évité : `body` doit être une **chaîne de caractères** (`JSON.stringify(...)`), pas l'objet JavaScript brut — sinon le serveur ne saurait pas l'interpréter correctement malgré l'en-tête `Content-Type`.

## Exercice 3
```javascript
const pUsers = fetch("https://jsonplaceholder.typicode.com/users?_limit=3");
const pComments = fetch("https://jsonplaceholder.typicode.com/comments?_limit=3&_delay=1500");

Promise.race([pUsers, pComments])
    .then((r) => r.json())
    .then((resultat) => console.log(resultat));
// Les 3 users, car cette requête n'a pas de délai artificiel
```

## Exercice 4
```javascript
const a = new AbortController();

const pUsers = fetch("https://jsonplaceholder.typicode.com/users?_limit=3", { signal: a.signal });
const pComments = fetch("https://jsonplaceholder.typicode.com/comments?_limit=3&_delay=1500", { signal: a.signal });

Promise.race([pUsers, pComments])
    .then((r) => r.json())
    .then((resultat) => {
        console.log(resultat);
        a.abort();   // coupe la requête "comments" encore en attente
    });
```
📌 Les deux requêtes doivent être reliées **au même** `signal` dès leur création pour pouvoir être annulées ensemble via un seul `a.abort()`. Sans `AbortController`, la requête perdante finirait quand même par se terminer en arrière-plan, pour un résultat jamais utilisé — juste un gaspillage de ressources réseau.
