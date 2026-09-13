# Exercice 21 : JavaScript côté navigateur — mise en place

## Exercice 1 — Bon attribut de `<script>`
Pour chacune des situations suivantes, indiquez quel attribut (`defer`, `async`, aucun, ou une combinaison) utiliser sur la balise `<script>`, et justifiez en une phrase :
1. Un script qui sélectionne des éléments HTML et attache des interactions dessus.
2. Un script de suivi statistique indépendant du contenu de la page, à charger le plus tôt possible.
3. Un script placé juste avant `</body>`, à l'ancienne, sans aucun attribut.

## Exercice 2 — Portée des variables globales
Sans exécuter le code, indiquez ce qu'affichera chaque `console.log`, en supposant que `premier.js` est chargé avant `second.js` sur la même page :
```html
<script src="premier.js"></script>
<script src="second.js"></script>
```
```javascript
// premier.js (script classique, pas de type="module")
const message = "bonjour";
```
```javascript
// second.js
console.log(message);
console.log(window.message);
```
Que changerait le fait de mettre `type="module"` sur les deux balises `<script>` ?

## Exercice 3 — Utiliser `window` pour partager une donnée
Sans utiliser `import`/`export`, montrez comment un script `config.js` (chargé en premier, en script classique) peut rendre une valeur `apiUrl` disponible à un script `app.js` chargé ensuite sur la même page.
