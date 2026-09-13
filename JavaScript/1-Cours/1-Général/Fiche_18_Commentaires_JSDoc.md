# Fiche 18 : Commentaires et JSDoc

## 📌 Le rôle des commentaires
Un mauvais réflexe consiste à commenter **ce que fait** chaque ligne — le code lui-même, via des noms de variables/fonctions bien choisis, documente déjà ça. Un commentaire doit surtout expliquer le **pourquoi** : le contexte, une contrainte externe (texte de loi, décision métier...) qui n'est pas visible en lisant simplement le code.
```javascript
// ❌ Réexplique ce que fait déjà le code
// on vérifie si l'âge est supérieur à 16
if (age > 16) { ... }

// ✅ Apporte un contexte qui n'est pas dans le code
// La loi aux États-Unis autorise la conduite dès 16 ans (voir texte de loi : ...)
if (age > 16) { ... }
```

## 📌 Pourquoi la JSDoc
Sans indication de type, l'éditeur ne peut pas toujours deviner le type des paramètres ou du retour d'une fonction (il affiche `any`). La **JSDoc** est un format de commentaire structuré, sans outil à installer, qui permet de documenter les types attendus — l'éditeur en profite alors pour une meilleure auto-complétion et une détection d'erreurs.

## 🛠️ Syntaxe de base
```javascript
/**
 * Permet de savoir si l'utilisateur peut conduire.
 * En concordance avec les textes de droit en vigueur.
 * @param {number} age
 * @param {string} pays Code pays sur deux lettres
 * @returns {boolean}
 */
function canDrive(age, pays) {
    // ...
}
```
Un commentaire JSDoc commence par `/**` (deux astérisques) et se place juste au-dessus de l'élément documenté. `@param {type} nom description` documente un paramètre ; `@returns {type}` (ou son alias `@return`) documente la valeur renvoyée.

## 🛠️ Types de base
| Type JSDoc | Correspond à |
|---|---|
| `number` | Nombre |
| `string` | Chaîne de caractères |
| `boolean` | Booléen |
| `object` | Objet générique |

## 🛠️ Typer la forme d'un objet
```javascript
/**
 * @returns {{id: number, title: string, body: string}}
 */
function fetchPost() { ... }
```
L'éditeur comprend alors qu'un appel à `fetchPost()` renvoie un objet avec ces trois propriétés précises, et propose l'auto-complétion dessus (`a.title`, `a.id`...).

## 🛠️ Typer un tableau
Deux notations équivalentes :
```javascript
/** @returns {Array<string>} */
/** @returns {string[]} */
```
Pour un tableau d'objets :
```javascript
/**
 * @returns {Array<{id: number, title: string, body: string}>}
 */
function fetchPosts() { ... }
```

## 🛠️ Typer une promesse
Même principe que pour les tableaux, avec `Promise<Type>` (voir [[Fiche_15_Promises]]) :
```javascript
/**
 * @returns {Promise<Array<{id: number, title: string, body: string}>>}
 */
async function fetchPosts() { ... }
```

## 🛠️ Réutiliser un type : `@typedef` et `@property`
Répéter la même forme d'objet dans plusieurs fonctions devient vite pénible — on peut définir un type nommé une fois pour toutes :
```javascript
/**
 * @typedef {object} Post
 * @property {number} id
 * @property {string} title Titre de l'article
 * @property {string} body
 */

/**
 * @returns {Promise<Post[]>}
 */
async function fetchPosts() { ... }
```
📌 Une fois `Post` défini, on peut le réutiliser comme n'importe quel autre type (`Post`, `Post[]`, `Promise<Post>`...) dans toute la suite du fichier.

## 🛠️ Typer une fonction
```javascript
/**
 * @returns {(str: string, age: number) => Post}
 */
function fetchPostFactory() { ... }
```
Le type d'une fonction s'écrit `(param: Type, ...) => TypeDeRetour`, comme une signature de fonction fléchée.

## 🛠️ Typer une propriété de classe
Deux approches, selon la préférence et le support de l'éditeur :
```javascript
class Personne {
    /**
     * @param {string[]} firstName
     */
    constructor(firstName) {
        this.firstName = firstName;
    }
}
```
Ou, en documentant directement une variable :
```javascript
/**
 * Prénom de l'utilisateur
 * @type {string[]}
 */
let b = [];
```
⚠️ Le support de la JSDoc sur les propriétés de classe varie selon l'éditeur — certains proposent bien l'auto-complétion à partir de ces annotations, d'autres se contentent d'inférer le type à partir de ce qui est assigné dans le constructeur.

## 💡 Autres mots-clés utiles
| Tag | Rôle |
|---|---|
| `@throws {Type}` | Indique qu'une fonction peut lever une erreur |
| `@private` | Signale qu'un élément n'est pas censé être utilisé en dehors de son contexte (masqué de l'auto-complétion externe) |

📌 La liste complète des tags disponibles est référencée dans la documentation JSDoc officielle — tous les éditeurs ne les interprètent pas de la même façon.

## ✅ À retenir
Un commentaire doit expliquer le **pourquoi**, pas reformuler ce que le code dit déjà. La JSDoc (`/** ... */` avec `@param`, `@returns`, `@typedef`/`@property`) sert à préciser les types quand l'éditeur ne peut pas les déduire seul — utile même pour des cas "évidents", car ça sécurise l'utilisation future de la fonction par quelqu'un d'autre (ou par vous-même, plus tard).
