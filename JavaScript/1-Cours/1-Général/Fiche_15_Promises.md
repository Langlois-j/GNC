# Fiche 15 : Les promesses

## 📌 Pourquoi les promesses ?
Elles résolvent le problème du **callback hell** rencontré en [[Fiche_14_Timers]] : au lieu d'imbriquer des callbacks les uns dans les autres, une `Promise` représente une valeur **pas encore disponible** (une opération asynchrone en cours) et permet d'enchaîner les étapes de façon linéaire plutôt qu'imbriquée.

## 🛠️ Créer une promesse
```javascript
const p = new Promise((resolve, reject) => {
    // resolve(valeur) : la promesse a été tenue
    // reject(valeur)  : la promesse a échoué
    resolve(4);
});
```
Le constructeur `Promise` attend une fonction (l'"executor") qui reçoit deux callbacks : `resolve` et `reject`. On appelle l'un ou l'autre selon que l'opération réussit ou échoue.

⚠️ **Piège important** : le code à l'intérieur de l'executor est exécuté **immédiatement**, dès la création de la promesse — pas au moment où on appelle `.then()`. Si ce code contient une boucle bloquante, elle bloquera le script tout de suite, même avant qu'on ait "consommé" la promesse.

## 🛠️ Consommer une promesse : `.then()` / `.catch()` / `.finally()`
```javascript
p.then((nombre) => {
    console.log("nombre :", nombre);   // appelé si la promesse est résolue
}).catch((erreur) => {
    console.log("échec :", erreur);    // appelé si la promesse est rejetée
}).finally(() => {
    console.log("terminé");            // appelé dans tous les cas
});
```
📌 `.then()` s'exécute quand la promesse est *fulfilled* (résolue), `.catch()` quand elle est *rejected* (échouée). `.finally()` s'exécute systématiquement, qu'il y ait eu succès ou échec.

## 🛠️ Chaînage — l'intérêt principal des promesses
`.then()` et `.catch()` renvoient eux-mêmes une **nouvelle promesse**, ce qui permet d'enchaîner les étapes :
```javascript
p.then((nombre) => {
    return nombre + 1;          // devient la valeur reçue par le .then() suivant
}).then((nombre2) => {
    console.log("nombre2 :", nombre2);
}).catch((erreur) => {
    console.log("erreur :", erreur);
});
```
📌 Si un `.then()` ne retourne rien, le `.then()` suivant reçoit `undefined`. Si un `.then()` lève une erreur ou retourne une promesse rejetée, c'est le `.catch()` suivant (pas le `.then()`) qui prendra le relais — exactement comme un `try`/`catch` classique. Un `.catch()` qui se termine normalement (sans relancer d'erreur) "répare" la chaîne : les `.then()` suivants seront de nouveau appelés normalement.

## 🛠️ Fabriquer une promesse à partir d'un timer
En reprenant `setTimeout` de [[Fiche_14_Timers]] :
```javascript
function wait(duree) {
    return new Promise((resolve) => {
        setTimeout(() => resolve(duree), duree);
    });
}

function waitAndFail(duree) {
    return new Promise((_, reject) => {
        setTimeout(() => reject(duree), duree);
    });
}

wait(2000)
    .then((duree) => console.log("attendu :", duree))   // affiché après 2s
    .catch((err) => console.log("erreur :", err));
```
💡 Retourner une nouvelle promesse depuis un `.then()` fait attendre la chaîne jusqu'à la résolution de **cette** promesse avant d'appeler le `.then()` suivant.

## ⚠️ Promesse rejetée sans `.catch()`
```javascript
waitAndFail(1000);   // ⚠️ "Uncaught (in promise)" — rejet non géré
```
Une promesse rejetée sans `.catch()` associé (directement ou plus loin dans la chaîne) déclenche une erreur non gérée signalée par l'environnement. Toujours prévoir un `.catch()`, même minimal.

## 🛠️ `async` / `await` — écrire de l'asynchrone comme du synchrone
```javascript
async function main() {
    console.log("hello");
    const duree = await wait(2000);   // met en pause CETTE fonction jusqu'à résolution
    console.log("durée :", duree);    // affiché après 2s, avec la valeur résolue
}
```
📌 `await` ne peut être utilisé qu'à l'intérieur d'une fonction `async` (ou en haut d'un module — hors sujet ici). Une fonction `async` **renvoie toujours une promesse**, même si on écrit un simple `return` :
```javascript
async function getValeur() {
    return 4;   // équivaut à : return Promise.resolve(4)
}
getValeur().then(v => console.log(v));   // 4
```

## 🛠️ Gérer les erreurs avec `try`/`catch`
```javascript
async function main() {
    try {
        await waitAndFail(1000);
        console.log("jamais atteint");
    } catch (erreur) {
        console.log("erreur :", erreur);
    }
}
```

## ⚠️ Piège : le fil principal reste synchrone
`await` met en pause **la fonction asynchrone**, pas tout le programme — mais du code bloquant classique (une boucle `while`) reste, lui, totalement bloquant. Un ordre d'exécution typique :
1. Tout le code synchrone du fichier s'exécute d'abord en entier (y compris une boucle bloquante si elle existe).
2. Les `.then()`/`await` en attente ne sont traités qu'une fois le fil principal libéré.

## ⚠️ Piège : `async` inutile
```javascript
// ❌ Inutile : crée une promesse supplémentaire pour rien
async function waitAndLog(duree, message) {
    await wait(duree);
    console.log(message);
}

// ✅ Équivalent, sans wrapper de promesse superflu
function waitAndLog(duree, message) {
    return wait(duree).then(() => console.log(message));
}
```
📌 N'utiliser `async` que si la fonction contient un `await`. Si on ne fait que retourner une promesse existante (éventuellement transformée via `.then()`), pas besoin d'`async` : ça évite de créer une couche de promesse inutile.

## 🛠️ Combiner plusieurs promesses
| Méthode | Comportement |
|---|---|
| `Promise.resolve(v)` / `Promise.reject(v)` | Crée directement une promesse déjà résolue/rejetée avec `v` |
| `Promise.all([...])` | Attend **toutes** les promesses ; échoue dès qu'**une seule** échoue (renvoie son erreur) |
| `Promise.allSettled([...])` | Attend toutes les promesses, ne rejette jamais ; renvoie un tableau d'objets `{status, value}` ou `{status, reason}` pour chacune |
| `Promise.any([...])` | Renvoie la **première réussie** ; échoue seulement si **toutes** échouent (`AggregateError`) |
| `Promise.race([...])` | Renvoie le résultat de la **première réglée** (résolue ou rejetée), peu importe laquelle |

```javascript
Promise.all([wait(1000), wait(2000)])
    .then((resultats) => console.log(resultats))   // [1000, 2000], après 2s
    .catch((erreur) => console.log("échec :", erreur));

Promise.allSettled([wait(1000), waitAndFail(2000)])
    .then((resultats) => console.log(resultats));
// [{status:"fulfilled", value:1000}, {status:"rejected", reason:2000}]

Promise.race([wait(1000), wait(2000)])
    .then((v) => console.log(v));   // 1000 — la première réglée l'emporte
```
💡 Ces méthodes de combinaison restent d'usage assez rare au quotidien, mais indispensables le jour où on doit lancer plusieurs opérations asynchrones en parallèle plutôt que les unes après les autres.

## ✅ À retenir
Une promesse a 3 états : *pending* (en cours), *fulfilled* (résolue), *rejected* (rejetée). `.then()`/`.catch()`/`.finally()` permettent d'enchaîner sans imbrication. `async`/`await` est un sucre syntaxique par-dessus les promesses (voir [[Fiche_13_Sucre_syntaxique]]) — plus lisible, mais uniquement dans une fonction `async`, avec un `try`/`catch` pour gérer les erreurs. Ne jamais laisser une promesse rejetée sans `.catch()`.
