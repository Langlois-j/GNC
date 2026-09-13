# Fiche 14 : Les timers et l'asynchrone

## 📌 Synchrone vs asynchrone
Un code **synchrone** exécute les instructions les unes après les autres, en **bloquant** tant qu'une opération n'est pas terminée. Un code **asynchrone** peut lancer une opération longue puis continuer à exécuter la suite du script pendant qu'elle se déroule en arrière-plan — le JavaScript n'a qu'un seul fil d'exécution, mais il sait "mettre de côté" une tâche en attente pour ne pas rester bloqué dessus.

## ⚠️ Piège classique : attendre en bloquant (à ne jamais faire)
```javascript
function wait(duree) {
    const start = Date.now();          // Date.now() : nombre de ms écoulées depuis le 01/01/1970
    while (Date.now() - start < duree) {
        // ne fait rien : boucle vide qui monopolise le thread
    }
}

console.log("bonjour");
wait(1000);
console.log("les gens");   // s'affiche 1 seconde plus tard, mais TOUT est bloqué entre-temps
```
⚠️ Ce code "fonctionne" mais bloque complètement le script pendant la durée d'attente — rien d'autre ne peut s'exécuter. Ce n'est jamais la bonne façon de temporiser en JavaScript.

## 🛠️ `setTimeout` — exécuter une fois après un délai
```javascript
setTimeout(() => {
    console.log("les gens");
}, 1000);   // délai en MILLISECONDES

console.log("bonjour");
// Résultat : "bonjour" s'affiche immédiatement, "les gens" s'affiche 1 seconde plus tard
```
📌 `setTimeout` ne bloque rien : le script continue son exécution immédiatement, et la fonction passée en premier paramètre sera exécutée plus tard, quand le délai sera écoulé.

## 🛠️ `setInterval` — répéter à intervalle régulier
```javascript
const intervalId = setInterval(() => {
    console.log("bonjour");
}, 1000);   // exécute la fonction toutes les secondes, indéfiniment
```
📌 `setTimeout` et `setInterval` renvoient tous les deux un **identifiant** (un entier) qui permet de retrouver ce timer précis, notamment pour l'arrêter.

## 🛠️ Arrêter un timer : `clearInterval` / `clearTimeout`
```javascript
let i = 0;
const intervalId = setInterval(() => {
    console.log("bonjour");
    i++;
    if (i >= 5) {
        clearInterval(intervalId);   // arrête l'intervalle en lui donnant son identifiant
    }
}, 1000);
// Affiche "bonjour" exactement 5 fois, puis s'arrête
```
`clearTimeout(id)` fonctionne de la même manière pour annuler un `setTimeout` qui n'a pas encore eu le temps de se déclencher.

## ⚠️ Pas de garantie de timing exact
Le délai passé à `setTimeout`/`setInterval` est un **minimum**, pas une garantie absolue. Si le thread principal est occupé par une autre opération bloquante (ex : une boucle `wait()` ou un `prompt()` en attente de saisie utilisateur), le callback du timer devra patienter que la main soit rendue avant de pouvoir s'exécuter — même si le délai est techniquement écoulé.

## 🛠️ Exemple pratique : un décompte
Deux façons d'écrire la même chose (afficher `3, 2, 1, 0` avec 1 seconde entre chaque valeur) :

**Avec `setInterval`** (nécessite de penser à nettoyer l'intervalle) :
```javascript
function decompte(n) {
    console.log(n);
    const intervalId = setInterval(() => {
        n--;
        console.log(n);
        if (n === 0) {
            clearInterval(intervalId);
        }
    }, 1000);
}
decompte(3);   // 3, 2, 1, 0
```

**Avec `setTimeout` récursif** (la fonction se rappelle elle-même) :
```javascript
function decompte(n) {
    console.log(n);
    if (n === 0) return;                       // condition d'arrêt : pas besoin de clearTimeout
    setTimeout(() => decompte(n - 1), 1000);
}
decompte(3);   // 3, 2, 1, 0
```
💡 La version récursive évite d'avoir à gérer manuellement un identifiant et un `clear...` — l'arrêt se fait naturellement via le `return`. C'est aussi asynchrone : rien n'empêche de lancer plusieurs décomptes en parallèle, ils s'exécuteront indépendamment.

## 🛠️ Le problème des callbacks imbriqués ("callback hell")
Dès que l'on enchaîne plusieurs opérations asynchrones dépendantes les unes des autres, on est obligé d'imbriquer les callbacks les uns dans les autres :
```javascript
setTimeout(() => {
    console.log("étape 1");
    setTimeout(() => {
        console.log("étape 2");
        setTimeout(() => {
            console.log("étape 3");
        }, 1000);
    }, 1000);
}, 1000);
```
⚠️ Plus il y a d'étapes asynchrones successives, plus le code s'imbrique et devient difficile à lire — c'est ce qu'on appelle le **callback hell**. [[Fiche_15_Promises]] présente une syntaxe bien plus lisible pour ce genre d'enchaînement.

## ✅ À retenir
Ne jamais bloquer le thread avec une boucle d'attente manuelle. `setTimeout` = une seule exécution différée ; `setInterval` = exécution répétée ; les deux renvoient un identifiant à conserver pour pouvoir les arrêter avec `clearTimeout`/`clearInterval`. Le délai donné est indicatif, pas garanti si le thread est occupé ailleurs.
