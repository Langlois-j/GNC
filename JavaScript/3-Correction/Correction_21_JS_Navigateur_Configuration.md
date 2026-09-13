# Correction 21 : JavaScript côté navigateur — mise en place

## Exercice 1
1. **`defer`** — le script a besoin que le DOM soit chargé avant d'agir dessus ; `defer` garantit une exécution après l'analyse complète du HTML, sans bloquer le chargement de la page.
2. **`async`** — indépendant du DOM, on veut qu'il se charge et s'exécute le plus vite possible, sans attendre la fin du chargement de la page.
3. **Aucun attribut** — placé juste avant `</body>`, tout le HTML précédent a déjà été analysé au moment où le script s'exécute ; l'ancien pattern se passe donc de `defer`/`async` (mais reste moins pratique qu'utiliser `defer` dans le `<head>`).

## Exercice 2
```javascript
console.log(message);          // "bonjour"
console.log(window.message);   // "bonjour"
```
📌 En script classique, une variable de premier niveau devient une propriété de `window`, partagée par tous les scripts chargés sur la page — `second.js` peut donc y accéder directement, sans import.

Avec `type="module"` sur les deux balises :
```javascript
console.log(message);          // ❌ ReferenceError : message n'est pas défini dans second.js
console.log(window.message);   // undefined
```
Chaque module a son propre espace : `message` resterait local à `premier.js` et invisible ailleurs, sauf à l'exporter explicitement puis l'importer dans `second.js` (voir [[Fiche_17_Modules]]).

## Exercice 3
```html
<script src="config.js"></script>
<script src="app.js"></script>
```
```javascript
// config.js (script classique)
window.apiUrl = "https://jsonplaceholder.typicode.com";
```
```javascript
// app.js
console.log(window.apiUrl);   // "https://jsonplaceholder.typicode.com"
console.log(apiUrl);           // fonctionne aussi, sans préfixe
```
📌 Assigner explicitement `window.apiUrl` rend l'intention plus claire qu'une simple déclaration `const apiUrl` — même si les deux fonctionnent en script classique, écrire `window.xxx` signale volontairement "ceci est une variable globale partagée".
