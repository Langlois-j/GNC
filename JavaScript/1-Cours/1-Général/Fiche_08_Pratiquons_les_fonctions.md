# Fiche 08 : Pratiquons les fonctions — méthodes utiles découvertes

## 📌 Contexte
Cette fiche regroupe les méthodes natives JavaScript découvertes en pratiquant les fonctions sur des cas concrets (palindrome, moyennes d'élèves, fréquence de mots).

## 🛠️ Chaînes ↔ Tableaux
```javascript
"kayak".split("");            // ["k","a","y","a","k"] — découpe une chaîne en tableau
["k","a","y","a","k"].join(""); // "kayak" — recolle un tableau en chaîne
[1,2,3].reverse();             // [3,2,1] — inverse un tableau EN PLACE (modifie l'original)
```
💡 `reverse()` ne fonctionne que sur des tableaux, pas directement sur une chaîne — d'où le combo `split → reverse → join` pour inverser un mot.

## 🛠️ Trier un tableau avec `sort()`
```javascript
// Sans fonction : tri alphabétique par défaut
["banane", "pomme", "kiwi"].sort();

// Avec fonction de comparaison (ex : tri d'objets par une propriété)
function compareEtudiants(a, b) {
    return b.moyenne - a.moyenne;   // décroissant : le plus grand en premier
}
etudiants.sort(compareEtudiants);
```
📌 La fonction de comparaison doit renvoyer : négatif si `a` doit passer avant `b`, positif si `a` doit passer après `b`, `0` si égaux. `a.valeur - b.valeur` = croissant, `b.valeur - a.valeur` = décroissant.
⚠️ `sort()` modifie le tableau **en place**, comme `reverse()`.

## 🛠️ Nettoyer une chaîne
```javascript
"Bonjour,".replace(",", "");         // remplace UNE SEULE occurrence
"a,b,c,d".replaceAll(",", "");       // remplace TOUTES les occurrences
"BONJOUR".toLowerCase();             // "bonjour"
```
⚠️ Piège rencontré : `replace()` ne traite que la première occurrence — pour tout nettoyer, utiliser `replaceAll()`.

## 🛠️ Math.min / Math.max / Math.random
```javascript
Math.min(...notes);     // note la plus basse d'un tableau
Math.max(...notes);     // note la plus haute d'un tableau
Math.floor(Math.random() * max);   // entier aléatoire entre 0 et max-1
```
⚠️ `Math.min`/`Math.max` n'acceptent pas un tableau directement — il faut "étaler" ses valeurs avec `...` (spread), sinon utiliser l'ancienne méthode `Math.max.apply(null, tableau)`.

## 🛠️ Construire un objet de comptage (fréquence)
```javascript
const frequencies = {};
for (const mot of mots) {
    if (frequencies[mot]) {
        frequencies[mot]++;
    } else {
        frequencies[mot] = 1;
    }
}
```
💡 Pattern très courant : vérifier si une clé existe déjà dans un objet avant d'incrémenter ou de l'initialiser.

## 🛠️ Transformer un objet `{clé: valeur}` en tableau triable
```javascript
const tableau = [];
for (const cle in frequencies) {
    tableau.push({ mot: cle, count: frequencies[cle] });
}
tableau.sort((a, b) => b.count - a.count);
```
📌 `sort()` ne fonctionne que sur des tableaux — un objet doit d'abord être converti en tableau d'objets `{clé, valeur}` avant de pouvoir être trié.

## ✅ À retenir
1. **Early return** : sortir d'une fonction dès que possible avec `return` évite d'imbriquer trop de conditions (ex : `if (n < 2) return false;` avant de tester la primalité).
2. Un premier jet de code qui fonctionne mais n'est pas optimisé, c'est normal — l'optimisation vient après, une fois que la logique est correcte.
