# Correction 13 : Sucre syntaxique

## Exercice 1
```javascript
const produits = [
    { nom: "Clavier", prix: 45, stock: { quantite: 12 } },
    { nom: "Souris", prix: 20, stock: null },
    { nom: "Écran", prix: 150 },
];

for (const produit of produits) {
    const quantite = produit.stock?.quantite ?? "inconnu";
    console.log(`${produit.nom} - ${produit.prix}€ - Stock : ${quantite}`);
}
// Clavier - 45€ - Stock : 12
// Souris - 20€ - Stock : inconnu   (stock est null → ?. renvoie undefined → ?? remplace)
// Écran - 150€ - Stock : inconnu  (stock n'existe pas du tout → même résultat)
```
⚠️ Piège évité : si `stock.quantite` valait `0`, un `||` aurait affiché `"inconnu"` à tort (0 est *falsy*). `??` ne se déclenche que sur `null`/`undefined`, donc `0` reste `0`.

## Exercice 2
```javascript
const configRecue = { theme: "sombre", langue: "fr" };

function creerConfig(config) {
    const { theme, langue, notifications = true } = config;
    return { theme, langue, notifications };
}

const config = creerConfig(configRecue);
console.log(config);       // { theme: "sombre", langue: "fr", notifications: true }
console.log(configRecue);  // { theme: "sombre", langue: "fr" } — inchangé
```
📌 La valeur par défaut `notifications = true` ne s'applique que si la propriété est **absente** ou vaut `undefined` (pas si elle vaut `false`). Le nouvel objet renvoyé (créé par un objet littéral neuf) ne partage pas de référence avec `configRecue`.

## Exercice 3
```javascript
const scores = [15, 8, 22, 8, 3, 22, 15];

const [meilleurScore, ...autresScores] = [...scores].sort((a, b) => b - a);

console.log(`Meilleur score : ${meilleurScore}${meilleurScore >= 20 ? " (parfait !)" : ""}`);
// Meilleur score : 22 (parfait !)

const scoresAvecBonus = [...scores, 10];
console.log(scoresAvecBonus);   // [15, 8, 22, 8, 3, 22, 15, 10]
console.log(scores);            // [15, 8, 22, 8, 3, 22, 15] — inchangé
```
⚠️ Piège évité : `sort()` modifie le tableau **en place**. Trier directement `scores.sort(...)` aurait changé l'ordre de `scores` lui-même. En passant par `[...scores].sort(...)`, on trie une copie et l'original reste intact — le même réflexe que pour `reverse()`.
