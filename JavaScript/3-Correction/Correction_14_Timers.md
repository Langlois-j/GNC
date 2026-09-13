# Correction 14 : Timers et asynchrone

## Exercice 1
```javascript
function feuTricolore() {
    console.log("Rouge");
    setTimeout(() => {
        console.log("Orange");
        setTimeout(() => {
            console.log("Vert");
        }, 1000);
    }, 1000);
}

feuTricolore();
// Rouge (immédiat), Orange (+1s), Vert (+2s)
```
📌 Chaque étape est déclenchée par le `setTimeout` de l'étape précédente — c'est volontairement un mini "callback hell" pour illustrer pourquoi ça devient vite pénible avec plus d'étapes (voir [[Fiche_15_Promises]]).

## Exercice 2
```javascript
function compteARebours(depart, arretA = 0) {
    let n = depart;
    console.log(n);
    const intervalId = setInterval(() => {
        n--;
        console.log(n);
        if (n <= arretA) {
            clearInterval(intervalId);
        }
    }, 1000);
}

compteARebours(3);      // 3, 2, 1, 0
compteARebours(10, 5);  // 10, 9, 8, 7, 6, 5
```
⚠️ Piège évité : tester `n === 0` fonctionne pour l'exemple de base, mais bloque le bonus (un compte à rebours qui doit s'arrêter à 5 n'atteindra jamais 0). `n <= arretA` couvre les deux cas.

## Exercice 3
```javascript
let scoreA = 0;
let scoreB = 0;

const idA = setInterval(() => {
    scoreA++;
    console.log("A avance");
    if (scoreA >= 5) {
        console.log("A a gagné !");
        clearInterval(idA);
        clearInterval(idB);
    }
}, 500);

const idB = setInterval(() => {
    scoreB++;
    console.log("B avance");
    if (scoreB >= 5) {
        console.log("B a gagné !");
        clearInterval(idA);
        clearInterval(idB);
    }
}, 800);
```
📌 Les deux `setInterval` tournent en parallèle de manière totalement indépendante — c'est l'intérêt de l'asynchrone illustré dans la fiche (l'analogie du restaurant qui cuit deux poissons en même temps). Dès qu'un des deux camps déclare la victoire, on nettoie **les deux** intervalles (`idA` ET `idB`), pas seulement le sien, sinon le perdant continuerait à s'afficher.
⚠️ `idB` est utilisé à l'intérieur du callback de `idA` avant d'être déclaré plus bas dans le fichier — ça fonctionne ici car `const idB` est bien assignée avant que le premier intervalle de 500 ms ait le temps de se déclencher (le code synchrone s'exécute en entier avant le premier callback asynchrone).
