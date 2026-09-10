# Fiche 03 : Portée des variables (scope)

## 📌 Principe
Une variable déclarée avec `let` ou `const` n'est accessible **que dans le bloc où elle est créée** (entre `{ }`) et dans ses blocs enfants — jamais dans les blocs parents.

## 🛠️ Exemple
```javascript
const age = 18;

if (age >= 18) {
    const suffixe = "eur";
    console.log(suffixe);   // ✅ fonctionne : on est dans le bloc où elle est déclarée
}

console.log(suffixe);   // ❌ ReferenceError: suffixe is not defined
```
Une variable déclarée **avant** un bloc reste accessible **à l'intérieur** de ce bloc :
```javascript
let age = 18;

if (age >= 18) {
    age = age * 2;   // ✅ OK, age est visible ici (déclarée dans le bloc parent)
}
```

## ⚠️ Piège : réutiliser un nom de variable dans un bloc enfant
```javascript
let suffixe = 18;

if (true) {
    let suffixe = 4;         // nouvelle variable, propre à ce bloc
    console.log(suffixe);    // 4
}

console.log(suffixe);        // 18 (la variable extérieure n'a pas changé)
```
💡 Deux variables de même nom ne sont autorisées que si elles sont dans des **blocs différents**. Redéclarer deux fois la même variable **dans le même bloc** provoque une erreur.

## 🛠️ `var` — à connaître mais à ne jamais utiliser
```javascript
var suffixe = 4;
```
`var` a une portée bien plus large que le bloc (portée de fonction, voire globale) → source classique de bugs (variables "qui remontent" et s'écrasent entre elles). Utiliser **exclusivement `let` et `const`**.

## ✅ À retenir
`let`/`const` = portée de bloc (prévisible). `var` = portée de fonction/globale (à proscrire). Ne jamais utiliser une variable sans la déclarer explicitement (elle serait alors créée implicitement avec un comportement proche de `var`).
