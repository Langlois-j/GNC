# Fiche 13 : Le sucre syntaxique

## 📌 Définition
Le **sucre syntaxique** désigne des raccourcis d'écriture qui n'apportent **aucune nouvelle fonctionnalité** au langage — ils permettent juste d'écrire la même chose plus rapidement et plus simplement (ex : `i++` au lieu de `i = i + 1`).

## 🛠️ Incrémentation / décrémentation
```javascript
let i = 0;

i++;   // post-incrémentation : renvoie la valeur AVANT incrémentation (0), puis incrémente
++i;   // pré-incrémentation : incrémente, puis renvoie la valeur APRÈS incrémentation
i--;   // équivalent pour décrémenter
```
💡 La différence ne compte que si on **utilise la valeur de retour** (`const x = i++`). En dehors de ce cas rare, `i++` et `++i` ont le même effet.

## 🛠️ Affectations composées
```javascript
let i = 3;
i += 3;   // i = i + 3 → 6
i *= 3;   // i = i * 3
i /= 3;   // i = i / 3
```

## 🛠️ Fonctions fléchées : parenthèses optionnelles
Vu en [[Fiche_05_Les_fonctions]] : une fonction fléchée à instruction unique fait un retour implicite. Particularité supplémentaire : si elle n'a **qu'un seul paramètre**, les parenthèses autour de celui-ci deviennent optionnelles.
```javascript
const double = x => x * 2;   // équivalent à (x) => x * 2
double(5);   // 10
```
⚠️ Cette omission de parenthèses ne fonctionne **que** pour les fonctions fléchées à un seul paramètre — impossible avec `function`.

## 🛠️ Valeur par défaut avec `||` (opérateurs logiques)
Rappel [[Fiche_02_Conditions]] sur les valeurs *truthy*/*falsy* : `a || b` renvoie `a` si `a` est *truthy*, sinon `b`.
```javascript
const a = 3;
const b = a || 5;   // b = 3 (a est truthy)

const a2 = 0;
const b2 = a2 || 5; // b2 = 5 (0 est falsy !)
```
⚠️ Piège : `||` traite `0`, `""` et autres valeurs *falsy* comme "absentes", même si elles sont volontaires.

## 🛠️ Nullish coalescing (`??`)
Même idée que `||`, mais ne se déclenche que si la valeur de gauche est **`null` ou `undefined`** (pas sur les autres valeurs falsy).
```javascript
const a = 0;
const b = a ?? 5;   // b = 0 → 0 n'est ni null ni undefined, donc conservé

let a2 = null;
const b2 = a2 ?? 5; // b2 = 5
```
✅ `??` est presque toujours préférable à `||` pour une valeur par défaut, sauf si `0`/`""` doivent explicitement être remplacés.

Version raccourcie lors d'une affectation :
```javascript
a ??= 3;   // équivalent à : a = a ?? 3
```

## 🛠️ Optional chaining (`?.`)
Accède à une propriété **seulement si** ce qui précède est défini ; sinon renvoie `undefined` sans lever d'erreur.
```javascript
const personne = { job: null };

personne.job.name;    // ❌ erreur : impossible de lire "name" de null
personne.job?.name;   // ✅ undefined, pas d'erreur
```
💡 Les `?.` peuvent s'enchaîner sur plusieurs niveaux, y compris avant un appel de méthode :
```javascript
personne?.age?.toString();   // n'appelle toString() que si age est défini
```

## 🛠️ Destructuration de tableaux
```javascript
const notes = [12, 17, 18];

const [premiereNote, secondeNote] = notes;
// premiereNote = 12, secondeNote = 17 (le 3e élément est ignoré)

const [note1, ...autresNotes] = notes;
// note1 = 12, autresNotes = [17, 18]  (rest : récupère tout le reste dans un tableau)
```

## 🛠️ Destructuration d'objets
```javascript
const personne = { firstName: "John", lastName: "Do", age: 18 };

const { firstName: prenom } = personne;   // renomme la variable extraite → prenom = "John"
const { firstName, lastName } = personne; // sans renommage : garde le nom de la propriété
const { firstName: f2, ...reste } = personne;
// f2 = "John", reste = { lastName: "Do", age: 18 }
```
📌 Très utile pour les paramètres de fonction : accepter un seul objet plutôt que plusieurs paramètres positionnels rend le code plus facile à faire évoluer (ajout/retrait de champs sans casser les appels existants). Reprend l'exemple `canDrive` de [[Fiche_05_Les_fonctions]] :
```javascript
function canDrive({ age, pays, region = "Paris" }) {
    // region vaut "Paris" si l'appelant ne la fournit pas
    // ...
}

canDrive({ age: 18, pays: "France" });   // region = "Paris" par défaut
```
💡 Une valeur par défaut peut aussi se mettre directement sur un paramètre "classique" (hors destructuration) :
```javascript
function power(nombre, exposant = 2) {
    return nombre ** exposant;
}
power(3);      // 9  (exposant par défaut = 2)
power(3, 3);   // 27
```

## 🛠️ Spread (`...`) — tableaux et objets
Aperçu déjà croisé en [[Fiche_08_Pratiquons_les_fonctions]] avec `Math.max(...notes)`. Le spread sert aussi à créer une **copie** d'un tableau/objet sans modifier l'original.
```javascript
const notes = [1, 2];
const notesEtendues = [...notes, 3, 4];   // [1, 2, 3, 4] — notes original non modifié
const notesInversees = [...notes].reverse();   // copie avant d'inverser
```
```javascript
const personne = { firstName: "John", lastName: "Do" };
const personneAvecAge = { ...personne, age: 18 };
// { firstName: "John", lastName: "Do", age: 18 } — personne original non modifié
```
⚠️ En cas de propriété en double, **la dernière déclarée l'emporte** :
```javascript
{ ...personne, firstName: "Jane" };   // firstName écrasé → "Jane"
{ firstName: "Jane", ...personne };   // personne écrase après → firstName reste "John"
```

## 🛠️ Opérateur ternaire
Raccourci pour un `if`/`else` qui ne fait qu'assigner une valeur (voir la structure complète en [[Fiche_02_Conditions]]).
```javascript
const age = 18;
const message = age >= 18 ? "majeur" : "mineur";
```
⚠️ **Ne jamais imbriquer des ternaires entre eux** (`a ? b : c ? d : e`) : la lisibilité s'effondre immédiatement. Au-delà d'une condition simple, revenir à un `if`/`else`.

## ✅ À retenir
| Sucre syntaxique | Usage typique |
|---|---|
| `i++` / `+=` | Raccourcis numériques |
| `x => x * 2` | Retour implicite, parenthèses optionnelles à 1 paramètre |
| `??` | Valeur par défaut, uniquement si `null`/`undefined` (préférer à `||`) |
| `?.` | Accès sécurisé à une propriété/méthode potentiellement absente |
| `[a, b] = tab` / `{a, b} = obj` | Extraire des valeurs, avec renommage/rest/défaut |
| `[...tab]` / `{...obj}` | Copier/fusionner sans modifier l'original |
| `cond ? a : b` | `if`/`else` court — jamais imbriqué |
