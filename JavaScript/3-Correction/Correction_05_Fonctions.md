# Correction 05 : Les fonctions

## Exercice 1
```javascript
function getRandomInt(max) {
    return Math.floor(Math.random() * (max + 1));
}

const solution = getRandomInt(10);

function isRight(n) {
    return solution === n;
}

function guess() {
    const number = Number(prompt("Entrez un chiffre :"));
    return isRight(number);
}

for (let i = 0; i < 3; i++) {
    if (guess()) {
        console.log("Bravo !");
        break;
    } else if (i === 2) {
        console.log("Vous avez perdu");
    }
}
```

## Exercice 2
```javascript
function isPremier(n) {
    if (n < 2) return false;
    for (let i = n - 1; i > 1; i--) {
        if (n % i === 0) return false;
    }
    return true;
}

console.log(isPremier(0));   // false
console.log(isPremier(1));   // false
console.log(isPremier(2));   // true
console.log(isPremier(3));   // true
console.log(isPremier(11));  // true
console.log(isPremier(12));  // false
```
💡 `return false` dès qu'un diviseur est trouvé évite d'avoir besoin d'un `break` : la fonction s'arrête immédiatement.
