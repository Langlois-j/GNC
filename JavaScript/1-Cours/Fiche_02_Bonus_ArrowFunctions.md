# Fiche : Arrow Functions

## 📌 Définition
Syntaxe courte pour écrire des fonctions en JavaScript (ES6+), avec un comportement particulier pour `this`.

## 🛠️ Syntaxe
```javascript
// Fonction classique
function addition(a, b) {
  return a + b;
}

// Arrow function
const addition = (a, b) => a + b;

// Un seul paramètre : parenthèses optionnelles
const carre = x => x * x;

// Corps multi-lignes : accolades + return explicite
const calcul = (a, b) => {
  const somme = a + b;
  return somme * 2;
};
```

## ⚠️ Piège majeur : le `this`
Une arrow function ne crée pas son propre contexte `this` — elle hérite de celui du parent. Ne pas les utiliser comme méthodes d'objet si on a besoin de `this`.

## ✅ À retenir
Idéal pour les callbacks courts (`.map()`, `.filter()`), à éviter pour les méthodes d'objets/classes.
