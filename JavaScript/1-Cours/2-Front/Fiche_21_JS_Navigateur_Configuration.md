# Fiche 21 : JavaScript côté navigateur — mise en place

## 📌 Compatibilité entre navigateurs
Chrome, Firefox et Safari embarquent chacun leur propre moteur JavaScript — l'utilisateur n'a rien à installer, le code s'exécute directement. Problème : tous les moteurs ne supportent pas exactement les mêmes fonctionnalités, ni les mêmes versions de ces fonctionnalités.
- La documentation **MDN** affiche, en bas de chaque page de référence, un tableau de compatibilité par navigateur et par version.
- Le site **caniuse.com** offre une vue équivalente, plus visuelle, pour le JavaScript comme pour le CSS.

💡 Les navigateurs modernes se mettent à jour automatiquement — le risque de version obsolète est donc assez faible aujourd'hui, à l'exception de vieux appareils iOS bloqués sur une ancienne version de Safari. Internet Explorer, lui, n'est plus du tout supporté par Microsoft (même pour la sécurité) : sa colonne de compatibilité peut être ignorée sans regret. Des outils existent aussi pour convertir automatiquement du code moderne vers une syntaxe compatible avec d'anciens navigateurs.

## 🛠️ Charger du JavaScript dans une page
Plutôt que d'écrire le code directement dans une balise `<script>` inline, on sépare généralement le JavaScript dans un fichier dédié :
```html
<script src="app.js"></script>
```
Le chemin peut être relatif, absolu, ou une URL complète — comme pour une feuille de style CSS.

## ⚠️ Ordre de chargement et position du `<script>`
Par défaut, le navigateur **interrompt** l'analyse du HTML dès qu'il rencontre un `<script>`, charge et exécute le fichier, puis reprend. Si ce script tente de manipuler des éléments du DOM qui arrivent plus loin dans la page, il ne les trouvera pas encore. Ancienne solution : placer le `<script>` juste avant la fermeture de `</body>`, pour qu'il s'exécute une fois tout le HTML analysé.

## 🛠️ Attributs `defer` et `async`
```html
<script src="app.js" defer></script>
```
- **`defer`** : charge le script en parallèle du reste de la page, mais ne l'exécute qu'**une fois le HTML entièrement analysé** — permet de placer le `<script>` dans le `<head>` tout en garantissant que le DOM est prêt. C'est l'option à privilégier pour un script qui interagit avec la page.
- **`async`** : charge le script en parallèle, mais l'exécute **dès qu'il est prêt**, sans garantie sur le moment précis (peut interrompre l'analyse du HTML en cours de route). Utile pour un script indépendant du DOM (ex : outil de suivi statistique), rarement pour de l'interactif.

## 🛠️ Attribut `type="module"`
```html
<script src="app.js" type="module"></script>
```
Active le système `import`/`export` (voir [[Fiche_17_Modules]]). Sans cet attribut, `import`/`export` ne fonctionnent pas. Par défaut, un script `type="module"` se comporte déjà comme s'il avait `defer` (exécution après chargement complet du DOM) — on peut ajouter `defer` en plus sans que ça pose problème, mais ce n'est pas nécessaire.

## 🛠️ L'objet global `window`
Dans un navigateur, la variable `window` référence un objet global contenant toutes les informations sur la fenêtre/page courante, ainsi que toutes les fonctions et variables globales disponibles :
```javascript
window.location;        // informations sur l'URL actuelle
window.setTimeout(...);  // équivaut à setTimeout(...) — voir [[Fiche_14_Timers]]
window.alert("message"); // équivaut à alert("message")
```
💡 Convention courante : omettre `window.` pour les **fonctions** (`setTimeout(...)`, `alert(...)`) — ça allège l'écriture et reste compatible avec d'autres environnements (comme Node.js, où `window` n'existe pas). Le préfixe `window.` reste plus utile pour les **propriétés** (`window.location`), pour éviter toute ambiguïté avec une variable locale de même nom.

## 🛠️ Fonctions bloquantes : `alert` et `prompt`
```javascript
window.prompt("Quel est ton nom ?");   // demande une saisie, bloque le script jusqu'à validation
alert("Attention !");                  // affiche un message, bloque jusqu'au clic sur OK
```
Ces deux fonctions **bloquent l'exécution du script** tant que l'utilisateur n'a pas répondu — comportement à garder en tête si le reste du code dépend d'un timing précis (voir le piège du fil bloquant en [[Fiche_15_Promises]]).

## ⚠️ Variables globales : script classique vs module
Dans un `<script>` **classique** (sans `type="module"`), une variable déclarée au premier niveau devient accessible depuis `window`, et donc partagée avec **tous les autres scripts** chargés sur la même page :
```javascript
// app.js (script classique)
const a = 3;
```
```javascript
// autre fichier chargé après, même page
console.log(window.a);   // 3 — accessible malgré l'absence d'export
console.log(a);           // 3 aussi
```
Dans un `<script type="module">`, ce n'est **plus le cas** : chaque module a son propre espace, et seul ce qui est explicitement `export`é devient accessible ailleurs :
```javascript
// app.js (module)
const a = 3;
```
```javascript
console.log(window.a);   // undefined — comportement isolé et prévisible
```
📌 Ce comportement plus prévisible des modules est une bonne raison supplémentaire d'utiliser systématiquement `type="module"` pour son JavaScript, même sans avoir besoin d'`import`/`export` dans l'immédiat.

## 💡 Lire les icônes de la documentation MDN
- ⚠️ Icône d'avertissement : fonctionnalité non standard — à éviter.
- 🗑️ Icône "poubelle" : fonctionnalité **dépréciée** — encore supportée par certains navigateurs pour la rétrocompatibilité, mais vouée à disparaître. Utile seulement pour comprendre du vieux code, jamais pour en écrire de nouveau.
- 🧪 Icône "expérimental" (fiole) : fonctionnalité en test, généralement supportée par un ou deux navigateurs seulement, pas encore standardisée.

## ✅ À retenir
Charger le JavaScript dans un fichier séparé avec `<script src="..." defer type="module">` couvre la grande majorité des cas : chargement non bloquant, exécution après le DOM, variables isolées du reste de la page. Vérifier la compatibilité via MDN ou caniuse.com avant d'utiliser une fonctionnalité récente ; ignorer sans hésiter tout ce qui est marqué déprécié.
