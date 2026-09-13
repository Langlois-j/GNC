# Correction 15 : Les promesses

## Exercice 1
```javascript
function delai(ms, valeur) {
    return new Promise((resolve) => {
        setTimeout(() => resolve(valeur), ms);
    });
}

delai(1000, "1 seconde plus tard").then((message) => console.log(message));
```

## Exercice 2
```javascript
delai(1000, "Étape 1")
    .then((message) => {
        console.log(message);
        return delai(1000, "Étape 2");
    })
    .then((message) => {
        console.log(message);
        return delai(1000, "Étape 3");
    })
    .then((message) => {
        console.log(message);
    })
    .catch(() => {
        console.log("Une erreur est survenue");
    });
```
Version avec rejet volontaire à l'étape 2 :
```javascript
delai(1000, "Étape 1")
    .then((message) => {
        console.log(message);
        return Promise.reject("boom");   // court-circuite la suite
    })
    .then((message) => {
        console.log(message);            // ❌ jamais exécuté
        return delai(1000, "Étape 3");
    })
    .then((message) => {
        console.log(message);            // ❌ jamais exécuté non plus
    })
    .catch(() => {
        console.log("Une erreur est survenue");   // ✅ exécuté
    });
```
📌 Dès qu'un maillon de la chaîne rejette, tous les `.then()` suivants sont **sautés** jusqu'au premier `.catch()` rencontré — comme un `throw` qui remonte jusqu'au `catch` le plus proche.

## Exercice 3
```javascript
async function main() {
    try {
        const msg1 = await delai(1000, "Étape 1");
        console.log(msg1);

        const msg2 = await delai(1000, "Étape 2");
        console.log(msg2);

        const msg3 = await delai(1000, "Étape 3");
        console.log(msg3);
    } catch {
        console.log("Une erreur est survenue");
    }
}

main();
```
💡 Même comportement que la version `.then()`, mais qui se lit de haut en bas comme du code synchrone — c'est tout l'intérêt d'`async`/`await` sur une suite d'étapes séquentielles.

## Exercice 4
```javascript
function delaiEchec(ms, valeur) {
    return new Promise((_, reject) => {
        setTimeout(() => reject(valeur), ms);
    });
}

const promesseA = delai(300, "A");
const promesseB = delai(700, "B");
const promesseC = delai(500, "C");

Promise.race([promesseA, promesseB, promesseC])
    .then((gagnant) => console.log("Première arrivée :", gagnant));   // "A" (300 ms)

Promise.all([promesseA, promesseB, promesseC])
    .then((resultats) => console.log(resultats));   // ["A", "B", "C"] — ordre du tableau, pas ordre d'arrivée
```
Bonus, avec un échec parmi les trois :
```javascript
const promesseBEchec = delaiEchec(700, "B a échoué");

Promise.all([promesseA, promesseBEchec, promesseC])
    .then((resultats) => console.log(resultats))
    .catch((erreur) => console.log("Promise.all a échoué :", erreur));
// "Promise.all a échoué : B a échoué" — un seul échec fait échouer tout le groupe

Promise.allSettled([promesseA, promesseBEchec, promesseC])
    .then((resultats) => console.log(resultats));
// [
//   { status: "fulfilled", value: "A" },
//   { status: "rejected", reason: "B a échoué" },
//   { status: "fulfilled", value: "C" }
// ]
```
📌 `Promise.all` est "tout ou rien" : un seul échec fait échouer le groupe entier. `Promise.allSettled` garantit un résultat pour chaque promesse, qu'elle ait réussi ou échoué — utile quand on veut connaître l'état de chaque opération sans que les échecs des unes bloquent l'analyse des autres.
