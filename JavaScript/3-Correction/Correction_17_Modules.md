# Correction 17 : Les modules

## Exercice 1
```javascript
// chaines.js
export function capitaliser(texte) {
    return texte.charAt(0).toUpperCase() + texte.slice(1);
}

export function inverser(texte) {
    return texte.split("").reverse().join("");
}
```
```javascript
// index.js
import { capitaliser, inverser } from "./chaines.js";

console.log(capitaliser("bonjour"));   // "Bonjour"
console.log(inverser("bonjour"));      // "ruojnob"
```

## Exercice 2
```javascript
// logger.js
export default function log(message) {
    console.log(`[LOG] ${message}`);
}

export function logErreur(message) {
    console.log(`[ERREUR] ${message}`);
}
```
```javascript
// index.js
import log, { logErreur } from "./logger.js";

log("Tout va bien");         // [LOG] Tout va bien
logErreur("Il y a un souci"); // [ERREUR] Il y a un souci
```
⚠️ Piège évité : l'export par défaut s'importe **sans accolades**, l'export nommé **avec** — mélanger les deux dans la même instruction `import` est possible, mais l'ordre compte : le défaut d'abord, les nommés ensuite entre accolades.

## Exercice 3
```javascript
// utils.js
export { capitaliser, inverser } from "./chaines.js";
export { default as log } from "./logger.js";
```
```javascript
// index.js
import { capitaliser, inverser, log } from "./utils.js";

log(capitaliser("bonjour"));   // [LOG] Bonjour
console.log(inverser("bonjour"));
```
📌 `utils.js` ne fait que réexporter : il ne redéfinit ni n'importe ces fonctions pour son propre usage, il sert uniquement de point d'entrée unique pour le reste du code.

## Exercice 4
```javascript
// index.js
const utilisateurConnecte = true;

if (utilisateurConnecte) {
    const { default: genererRapport } = await import("./rapport.js");
    genererRapport();
}
```
📌 Grâce au top-level `await` (disponible dans un script `type="module"`), on peut attendre la résolution de l'import dynamique directement, sans passer par `.then()`. Le fichier `rapport.js` n'est chargé par le navigateur **que** si la condition est vraie — utile pour éviter de charger du code inutilisé.

⚠️ Si l'environnement ne supporte pas le top-level `await`, on encapsule dans une IIFE asynchrone :
```javascript
(async () => {
    if (utilisateurConnecte) {
        const { default: genererRapport } = await import("./rapport.js");
        genererRapport();
    }
})();
```
