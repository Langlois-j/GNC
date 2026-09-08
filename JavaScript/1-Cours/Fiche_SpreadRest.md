# Fiche : Spread & Rest

## 📌 Définition
Le même opérateur `...` avec deux usages opposés : "étaler" (spread) ou "regrouper" (rest).

## 🛠️ Spread — étaler des éléments
```javascript
// Copier un tableau
const original = [1, 2, 3];
const copie = [...original];

// Fusionner des tableaux
const fusion = [...tab1, ...tab2];

// Copier/fusionner des objets (immutabilité en React)
const utilisateur = { nom: "Julien", age: 30 };
const utilisateurMaj = { ...utilisateur, age: 31 };

// Passer des arguments à une fonction
Math.max(...[5, 2, 9]);
```

## 🛠️ Rest — regrouper des éléments
```javascript
function somme(...nombres) {
  return nombres.reduce((a, b) => a + b, 0);
}
somme(1, 2, 3, 4); // 10

const [premier, ...autres] = [1, 2, 3, 4];
```

## ✅ À retenir
Essentiel en React pour respecter l'immutabilité de l'état (`setState`, `useState`) sans muter directement objets/tableaux.
