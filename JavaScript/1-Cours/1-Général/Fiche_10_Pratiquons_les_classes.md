# Fiche 10 : Pratiquons les classes — points de vigilance

## 📌 Contexte
Points pratiques découverts en construisant des classes (formes géométriques, bibliothèque de livres).

## 🛠️ `filter()` — créer un tableau filtré
```javascript
const livresEnS = livres.filter(livre => livre.title[0].toLowerCase() === "s");
```
`filter()` renvoie une **copie** du tableau ne contenant que les éléments pour lesquels la fonction passée renvoie `true`. Alternative plus courte à une boucle `for` + `if` + `push`.

## 🛠️ `forEach()` — exécuter une fonction sur chaque élément
```javascript
books.forEach(book => this.addBook(book));
```

## ⚠️ Piège majeur : `this` dans `forEach` / callbacks
```javascript
// ❌ Dangereux avec une fonction classique passée directement :
books.forEach(this.addBook);   // this, à l'intérieur d'addBook, devient undefined !

// ✅ Sûr avec une fonction fléchée qui "capture" le this englobant :
books.forEach(book => this.addBook(book));
```
📌 Quand une méthode est passée en référence (sans être appelée directement sur l'objet), elle **perd** son `this` d'origine. Les fonctions fléchées n'ont pas ce problème car elles n'ont pas leur propre `this`.

## 🛠️ Lire la stack trace en cas d'erreur
Une erreur affiche la chaîne d'appels ayant mené au problème (fonction A appelée par B, appelée par C...). Remonter cette pile aide à trouver la **ligne d'origine** du bug, pas seulement celle où l'erreur explose.

## 🛠️ Organiser des données : tableau vs objet
Pour une collection qu'on doit filtrer/trier de plusieurs façons différentes (par lettre, par date, etc.), un **tableau simple** + une fonction de recherche est souvent plus flexible qu'un objet pré-organisé par clé — on garde la donnée brute et on adapte la requête a posteriori.

## ✅ À retenir
La difficulté avec les classes n'est presque jamais la syntaxe, mais (1) bien découper son problème en classes cohérentes et (2) rester vigilant sur le comportement de `this` dès qu'une méthode est passée "par référence" à une autre fonction.
