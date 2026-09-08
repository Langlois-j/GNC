# Correction : Arrow Functions, Destructuring, Async/Await, Spread/Rest

## Exercice 1
```javascript
const double = x => x * 2;
```

## Exercice 2
```javascript
const config = { host: "localhost", port: 3000, debug: true };
const { host, port = 8080 } = config;
```

## Exercice 3
```javascript
async function recupererUtilisateurs() {
  try {
    const reponse = await fetch("/api/utilisateurs");
    const donnees = await reponse.json();
    return donnees;
  } catch (erreur) {
    console.error("Erreur lors de la récupération :", erreur);
  }
}
```

## Exercice 4
```javascript
const a = [1, 2, 3];
const b = [4, 5, 6];
const fusion = [...a, ...b];
// a et b restent inchangés
```

## Exercice 5
```javascript
function moyenne(...nombres) {
  if (nombres.length === 0) return 0;
  const somme = nombres.reduce((total, n) => total + n, 0);
  return somme / nombres.length;
}
moyenne(2, 4, 6); // 4
```
