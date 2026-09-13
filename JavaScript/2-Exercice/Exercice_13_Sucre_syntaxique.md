# Exercice 13 : Sucre syntaxique

## Exercice 1 — Fiche produit sécurisée
À partir de :
```javascript
const produits = [
    { nom: "Clavier", prix: 45, stock: { quantite: 12 } },
    { nom: "Souris", prix: 20, stock: null },
    { nom: "Écran", prix: 150 },
];
```
Pour chaque produit, affichez une ligne du type `Clavier - 45€ - Stock : 12` (ou `Stock : inconnu` si l'information n'est pas disponible), sans jamais provoquer d'erreur.
1. Utilisez l'**optional chaining** pour lire `stock.quantite` en toute sécurité.
2. Utilisez le **nullish coalescing** (`??`) pour afficher `"inconnu"` par défaut — attention, une quantité de `0` doit bien s'afficher `0`, pas `"inconnu"`.

## Exercice 2 — Configuration utilisateur
```javascript
const configRecue = { theme: "sombre", langue: "fr" };
```
Écrivez une fonction `creerConfig(config)` qui :
1. Utilise la **destructuration** avec valeurs par défaut pour extraire `theme`, `langue` et `notifications` (par défaut `true` si absent).
2. Renvoie un **nouvel objet** (sans modifier `configRecue`) contenant ces trois propriétés, obtenu grâce au **spread**.

Vérifiez que `configRecue` n'a pas été modifié après l'appel.

## Exercice 3 — Classement et podium
```javascript
const scores = [15, 8, 22, 8, 3, 22, 15];
```
1. Par **destructuration** avec rest, récupérez le meilleur score connu comme premier élément d'un tableau trié, et le reste des scores dans une autre variable (indice : triez le tableau avant de déstructurer).
2. Affichez `"Meilleur score : X"` en utilisant un **opérateur ternaire** pour ajouter la mention `" (parfait !)"` si `X` est supérieur ou égal à 20, sinon rien.
3. Bonus : à l'aide du **spread**, créez un nouveau tableau `scoresAvecBonus` qui contient tous les scores originaux plus un score bonus de `10`, sans modifier `scores`.
