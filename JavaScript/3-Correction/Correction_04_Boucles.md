# Correction 04 : Les boucles

## Exercice 1
```javascript
const chiffre = Number(prompt("Entrez un chiffre entre 0 et 10 :"));

if (chiffre > 10 || chiffre < 0) {
    console.log("Le nombre n'est pas entre 0 et 10");
} else {
    for (let i = chiffre; i >= 0; i--) {
        console.log(i);
    }
}
```

## Exercice 2
```javascript
const guess = 8;
let chiffre;

while (chiffre !== guess) {
    chiffre = Number(prompt("Votre chiffre :"));
    if (chiffre !== guess) {
        console.log("Dommage");
    }
}
console.log("Bravo, vous avez deviné");
```

## Exercice 3
```javascript
const guess = 8;
let chiffre;

while (chiffre !== guess) {
    chiffre = Number(prompt("Votre chiffre :"));
    if (chiffre < guess) {
        console.log("+");
    } else if (chiffre > guess) {
        console.log("-");
    }
}
console.log("Bravo, vous avez deviné");
```

## Exercice 4
```javascript
const fruits = ["pomme", "banane", "kiwi", "mangue"];

// for classique
for (let i = 0; i < fruits.length; i++) {
    console.log(i, fruits[i]);
}

// for...of (valeurs) — nécessite un compteur manuel pour l'index
let index = 0;
for (const fruit of fruits) {
    console.log(index, fruit);
    index++;
}

// for...in (index/clés directement)
for (const i in fruits) {
    console.log(i, fruits[i]);
}
```
💡 `for...in` donne directement l'index sans compteur manuel, mais `for...of` reste préférable si on n'a besoin que des valeurs (plus lisible, pas de risque de confondre index et valeur).
