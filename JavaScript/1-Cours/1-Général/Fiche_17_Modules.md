# Fiche 17 : Les modules

## 📌 Pourquoi les modules ?
Dès qu'un projet grossit, on veut séparer le code dans plusieurs fichiers plutôt que tout écrire dans un seul script. Le système de **modules** permet d'exporter des éléments (fonctions, classes, valeurs) depuis un fichier et de les importer dans un autre.

## ⚠️ Prérequis côté navigateur
```html
<script type="module" src="index.js"></script>
```
Le système de modules ne fonctionne, côté navigateur, que dans un `<script>` marqué `type="module"`. Sans ça, `import`/`export` provoquent une erreur.

## 🛠️ Export nommé
```javascript
// tableau.js
export const somme = (elements) =>
    elements.reduce((accumulateur, item) => accumulateur + item, 0);
```
`export` devant une déclaration la rend disponible depuis l'extérieur. Le nom de l'export est celui de la variable.

## 🛠️ Import nommé
```javascript
// index.js
import { somme } from "./tableau.js";

console.log(somme([12, 23, 19]));   // 54
```
📌 Le chemin doit commencer par `.` (chemin relatif) ou `/` (chemin absolu) — ou être une URL complète pour importer depuis un autre domaine. Seuls les éléments **explicitement exportés** peuvent être importés ; tenter d'importer un nom non exporté provoque une erreur.

## 🛠️ Renommer un import
Utile pour éviter un conflit de nom entre plusieurs fichiers :
```javascript
import { somme as sommeTableau } from "./tableau.js";
sommeTableau([1, 2, 3]);
```

## 🛠️ Tout importer d'un coup : `import * as`
```javascript
import * as tableau from "./tableau.js";
tableau.somme([1, 2, 3]);
```
⚠️ Pratique à connaître mais généralement déconseillée au quotidien : n'importer que ce dont on a réellement besoin donne un code plus lisible et une meilleure structure.

## 🛠️ Export par défaut
Chaque fichier peut avoir **un seul** export par défaut (en plus, éventuellement, d'exports nommés) :
```javascript
// salutation.js
export default function () {
    console.log("Bonjour");
}
```
```javascript
// index.js — pas d'accolades, et le nom choisi à l'import est totalement libre
import hello from "./salutation.js";
hello();   // "Bonjour"

import auRevoir from "./salutation.js";   // même fonction, nom d'import différent
auRevoir();   // "Bonjour" aussi
```

## 🛠️ Combiner export nommé et export par défaut
```javascript
// tableau.js
export const somme = (elements) => elements.reduce((a, i) => a + i, 0);
export default function hello() {
    console.log("Bonjour");
}
```
Deux façons d'importer les deux à la fois :
```javascript
import hello, { somme } from "./tableau.js";
// ou, en donnant explicitement un nom au défaut :
import { default as hello, somme } from "./tableau.js";
```

## 🛠️ Réexporter depuis un autre module
On peut importer un élément dans un module puis le réexporter, pour centraliser plusieurs sources dans un seul fichier "carrefour" :
```javascript
// tableau.js
import hello from "./salutation.js";
export const hello2 = hello;
```
Syntaxe raccourcie équivalente pour réexporter un export par défaut sans avoir à le nommer localement :
```javascript
export { default as hello } from "./salutation.js";
```
💡 Utile pour créer un fichier "index" qui regroupe et réexporte les fonctions de plusieurs fichiers, afin que le reste du code n'ait qu'un seul chemin à importer.

## 🛠️ Import dynamique (asynchrone)
`import()` utilisé comme une fonction charge un module **à la demande**, et renvoie une `Promise` (voir [[Fiche_15_Promises]]) :
```javascript
import("./tableau.js").then((module) => {
    console.log(module);          // { somme: [Function], default: [Function] }
});

import("./tableau.js").then(({ somme, default: hello }) => {
    // destructuration : "default" doit être renommé, ce n'est pas un identifiant valide
    console.log(somme([1, 2, 3]));
    hello();
});
```
📌 L'intérêt principal : ne charger le fichier JavaScript que lorsqu'on en a réellement besoin, plutôt qu'au chargement initial de la page.

## 🛠️ Import dynamique avec `await`
Dans un script `type="module"`, le **top-level await** est autorisé (contrairement à un script classique — voir [[Fiche_15_Promises]]) :
```javascript
const { default: hello } = await import("./salutation.js");
hello();
```
Si l'environnement ne supporte pas le top-level await, on peut s'appuyer sur une **IIFE** asynchrone (fonction qui s'auto-exécute) :
```javascript
(async () => {
    const { default: hello } = await import("./salutation.js");
    hello();
})();
```

## ✅ À retenir
Côté navigateur : `<script type="module">` est obligatoire pour utiliser `import`/`export`. `export` nomme un élément ; `export default` en désigne un par fichier, importable sous n'importe quel nom sans accolades. `import()` (fonction) charge un module à la demande et renvoie une promesse — pratique pour ne charger du code que lorsque c'est nécessaire.
