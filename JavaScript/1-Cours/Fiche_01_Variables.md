# Fiche 01 : Les variables (types simples & complexes)

## 📌 Déclaration
```javascript
const majeur = 18;
// majeur = 21;  → ❌ Erreur : impossible de réaffecter une constante (TypeError)
```
`const` = valeur non réassignable. `let` = variable modifiable. `var` = ancienne syntaxe, à éviter (portée floue).

## 🛠️ Types simples
```javascript
const age    = 20;          // number (entier)
const taille = 1.83;        // number (décimal)
const nom    = "Térieur";   // string
const homme  = true;        // boolean
const couleur = null;        // null : absence de valeur volontaire
let poids;                    // undefined : déclarée mais non initialisée
```

## 💡 Concaténation vs template literals
```javascript
const nomComplet1 = prenom + " " + nom;      // concaténation classique
const nomComplet2 = `${prenom} ${nom}`;       // template literal (préféré, plus lisible)
```

## 🛠️ Types complexes — tableaux
```javascript
const notes = [12, 15, 18, 14, 16, 13, 17, "abs", 11, 10, 12, 14];

// Tableau de tableaux (ex: devoirs d'une classe)
const lesNotes = [
    ["Devoir 1", 10, "abs", 12, 14],
    ["Devoir 2", 15, 18, 14, 16],
    ["Devoir 3", 13, 17, "abs", 11],
];
```

## 🛠️ Types complexes — objets
```javascript
const unePersonne = {
    nom: "Térieur",
    prenom: "Alain",
    age: 20,
    taille: 1.83,
    poids: 75,
};
```

## ✅ À retenir
Une valeur "absente" (`abs`) mélangée à des nombres dans un tableau reste possible en JS (typage dynamique) — contrairement à un langage typé strict, mais attention aux calculs (moyenne, somme) qui devront filtrer ces valeurs non numériques.
