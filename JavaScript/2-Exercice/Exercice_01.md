# Exercice : Arrow Functions, Destructuring, Async/Await, Spread/Rest

## Exercice 1 — Arrow function
Réécris cette fonction en arrow function :
```javascript
function double(x) {
  return x * 2;
}
```

## Exercice 2 — Destructuring
Étant donné `const config = { host: "localhost", port: 3000, debug: true };`, extrais `host` et `port` en une ligne, avec `port` par défaut à `8080` si absent.

## Exercice 3 — Async/Await
Écris une fonction `async` qui appelle `fetch("/api/utilisateurs")`, récupère le JSON, et gère les erreurs avec `try/catch`.

## Exercice 4 — Spread
Étant donné deux tableaux `a = [1, 2, 3]` et `b = [4, 5, 6]`, crée un nouveau tableau fusionné sans modifier `a` ni `b`.

## Exercice 5 — Rest
Écris une fonction `moyenne(...nombres)` qui calcule la moyenne d'un nombre variable d'arguments.
