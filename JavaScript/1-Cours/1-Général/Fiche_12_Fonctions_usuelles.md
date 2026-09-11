# Fiche 12 : Fonctions usuelles (tableaux, objets, fonctions)

## 📌 Objectif
Tour d'horizon des méthodes natives les plus utiles. Inutile de toutes les retenir par cœur — l'important est de savoir **qu'elles existent** pour les retrouver le moment venu.

## 🛠️ Tableaux — les 3 méthodes vitales

### `map()` — transformer chaque élément (même taille en sortie)
```javascript
const noms = personnes.map(p => `${p.firstName} ${p.lastName}`);
const doubles = [1, 2, 3].map(x => x * 2);   // [2, 4, 6]
```

### `filter()` — garder certains éléments (taille ≤ original)
```javascript
const bonnesNotes = notes.filter(note => note >= 10);
```

### `reduce()` — réduire un tableau à une seule valeur
```javascript
const somme = notes.reduce((acc, note) => acc + note, 0);
// acc = accumulateur (valeur de départ = 2e argument), note = élément courant
```
📌 `map` = transformer, `filter` = sélectionner, `reduce` = agréger en une seule valeur. À eux trois, ils couvrent la majorité des besoins de manipulation de tableaux.

## 🛠️ Tableaux — recherche
| Méthode | Rôle |
|---|---|
| `at(-1)` | Accède à un élément, accepte les **index négatifs** (`-1` = dernier élément) |
| `find(fn)` | Renvoie le **premier élément** validant la condition |
| `findIndex(fn)` | Comme `find`, mais renvoie l'**index** |
| `findLast(fn)` / `findLastIndex(fn)` | Comme `find`/`findIndex`, en partant de la fin |
| `includes(valeur)` | `true`/`false` si la valeur est présente — remplace avantageusement `indexOf(v) !== -1` |
| `indexOf(valeur)` | Index de la 1ère occurrence, `-1` si absent |
| `lastIndexOf(valeur)` | Comme `indexOf`, en partant de la fin |

```javascript
const animaux = ["chat", "chien", "chauve-souris"];
animaux.includes("chat");   // true — bien plus lisible qu'une chaîne de ||
```

## 🛠️ Tableaux — modification **en place** (⚠️ modifient l'original)
| Méthode | Effet |
|---|---|
| `push(v)` | Ajoute à la fin |
| `pop()` | Retire et renvoie le dernier élément |
| `unshift(v)` | Ajoute au début |
| `shift()` | Retire et renvoie le premier élément |
| `reverse()` | Inverse l'ordre |
| `sort(fn)` | Trie |
| `splice(...)` | Insère/supprime à un index précis (peu utilisé, rarement nécessaire) |
| `fill(v)` | Remplit le tableau avec une valeur |

## 🛠️ Tableaux — sans modifier l'original
```javascript
const notesInversees = notes.slice().reverse();   // slice() sans argument = copie complète
const partie = animaux.slice(2);        // du index 2 jusqu'à la fin
const partie2 = animaux.slice(2, 4);    // de l'index 2 à 4 (4 exclu)
const partie3 = animaux.slice(-2);      // les 2 derniers éléments
```
💡 `slice()` crée un **nouveau tableau** — la technique classique pour éviter de modifier l'original avant d'appliquer `reverse()`/`sort()`.

```javascript
[1, 2].concat([3, 4]);   // [1, 2, 3, 4] — fusionne des tableaux sans les modifier
```

## 🛠️ Tableaux — autres
```javascript
Array.from("abc");          // ["a", "b", "c"] — convertit un itérable en tableau
notes.forEach((note, index) => console.log(note, index));   // parcours, sans retour
notes.join(", ");            // fusionne en chaîne
```

## 🛠️ Objets
```javascript
Object.assign({}, obj1, obj2);   // fusionne des objets (syntaxe ancienne, remplacée par le spread {...obj})
Object.keys(personne);            // ["firstName", "lastName"]
Object.values(personne);          // ["John", "Do"]
Object.entries(personne);         // [["firstName","John"], ["lastName","Do"]]
```
📌 À retenir en priorité : **`Object.keys`**, **`Object.values`**, **`Object.entries`** (ce dernier permet de faire un `for...of` sur un objet). Les autres (`Object.create`, `Object.defineProperty`, `Object.freeze`, `Object.is`) sont très spécifiques et rarement utiles en pratique courante.

## 🛠️ Fonctions — contrôler `this`
```javascript
function hello() { console.log(this); }

hello.call(3);              // appelle immédiatement, this = 3
hello.apply(3, [arg1]);     // comme call, mais les arguments sont dans un tableau
const helloBind = hello.bind(3);   // crée une NOUVELLE fonction, this figé à 3 pour toujours
helloBind();                 // this = 3, même si on essaie de le changer ensuite
```
📌 `bind()` fige définitivement la valeur de `this` (utile pour éviter les pièges vus avec `forEach(this.methode)`).

## ✅ À retenir
Priorités absolues à maîtriser : **`map`, `filter`, `reduce`** (tableaux) et **`Object.keys/values/entries`** (objets). Le reste se retrouve facilement dans la documentation (MDN) le jour où le besoin se présente.
