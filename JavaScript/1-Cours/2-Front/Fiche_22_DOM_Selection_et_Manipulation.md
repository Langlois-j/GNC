# Fiche 22 : Manipuler le DOM — les bases

## 📌 Le DOM et le point d'entrée `document`
Le DOM (*Document Object Model*) représente la structure HTML de la page sous forme d'un arbre de **nœuds**. Le point d'entrée pour y accéder est l'objet global `document` (disponible via `window.document`, mais on omet presque toujours `window.` devant `document`).

## 🛠️ Sélectionner un élément : `querySelector`
```javascript
const hello = document.querySelector("#hello");   // sélecteur CSS classique
```
`querySelector` prend une chaîne de sélecteur **CSS** (id, classe, balise, sélecteurs combinés...) et renvoie le **premier élément correspondant**, ou `null` si aucun ne correspond.

## 🛠️ Sélectionner plusieurs éléments : `querySelectorAll`
```javascript
const lis = document.querySelectorAll("li");   // une NodeList, pas un tableau
```
📌 Le retour est une **`NodeList`** : on peut itérer dessus avec `.forEach()` et accéder par index (`lis[0]`), mais **pas** avec `.filter()`, `.map()`, etc. — ce n'est pas un tableau.

## ⚠️ Convertir une `NodeList` en vrai tableau
```javascript
const tableauLis = Array.from(lis);
tableauLis.filter((li) => li.textContent.includes("bonjour"));   // fonctionne maintenant
```
`Array.from(...)` (voir [[Fiche_13_Sucre_syntaxique]] pour le spread, une alternative possible : `[...lis]`) permet d'accéder à toutes les méthodes de tableau quand `NodeList` ne suffit pas.

## 💡 Anciennes méthodes de sélection
`getElementById`, `getElementsByClassName`, `getElementsByTagName` existent toujours mais sont largement remplacées par `querySelector`/`querySelectorAll`, plus uniformes (syntaxe CSS pour tous les cas). `getElementById` reste parfois utilisée pour sa rapidité sur un cas très spécifique, mais rarement nécessaire.

## 🛠️ Sélecteurs CSS avancés et sélection imbriquée
```javascript
document.querySelector("ul > li");        // enfant direct
document.querySelector("li:first-child"); // premier enfant
document.querySelector("li:nth-child(2)");

const ul = document.querySelector("ul");
ul.querySelectorAll("li");   // ne cherche QUE dans ce ul, pas dans toute la page
```
📌 `querySelector`/`querySelectorAll` peuvent s'appeler sur n'importe quel élément, pas seulement sur `document` — utile pour restreindre la recherche à une sous-partie précise du DOM.

## 🛠️ Lire/modifier le contenu d'un élément
| Propriété | Contenu | Modifiable |
|---|---|---|
| `nodeName` | Nom du nœud (toujours en **majuscules**, ex : `"LI"`) | non |
| `innerHTML` | Structure HTML interne (balises comprises) | oui |
| `innerText` | Texte **visible** par l'utilisateur (ignore contenu caché, scripts...) | oui |
| `textContent` | Tout le texte brut, y compris caché et contenu de `<script>` | oui |

⚠️ `innerText` et `textContent` ne renvoient **pas** la même chose dès qu'il y a des éléments cachés (`hidden`) ou des balises `<script>` à l'intérieur — `innerText` respecte ce qui est réellement affiché, `textContent` prend tout sans distinction.

## 🛠️ Attributs HTML
```javascript
element.setAttribute("hidden", "hidden");   // ajoute/modifie un attribut
element.removeAttribute("hidden");          // le retire
element.getAttribute("class");              // lit sa valeur — null si l'attribut n'existe pas
```
⚠️ `getAttribute` sur un attribut absent renvoie `null`, pas `undefined`.

## 🛠️ Manipuler les classes CSS : `classList`
```javascript
element.classList.add("red");      // ajoute — ignore si déjà présente (pas de doublon)
element.classList.remove("red");   // retire — ne fait rien si absente
element.classList.toggle("red");   // ajoute si absente, retire si présente
```
💡 `classList.toggle(...)` combiné à `setInterval` (voir [[Fiche_14_Timers]]) permet par exemple de faire clignoter un élément facilement.

## 🛠️ Style en ligne vs style calculé
```javascript
element.style.color = "blue";        // modifie le style INLINE de l'élément
element.style.fontWeight = "bold";   // ⚠️ camelCase, pas "font-weight"
```
⚠️ `element.style` ne reflète que les styles écrits **en ligne** sur l'élément — si la couleur vient d'une classe CSS externe, `element.style.color` renverra une chaîne vide. Pour connaître le style réellement **appliqué** (cascade CSS comprise) :
```javascript
getComputedStyle(element).color;   // couleur réelle, interprétée par le navigateur (souvent en RGB)
```

## 🛠️ Créer un élément : `createElement`
```javascript
const newLi = document.createElement("li");   // créé en mémoire, pas encore dans la page
newLi.innerHTML = "bonjour les gens";
```

## 🛠️ Ajouter un élément au DOM
```javascript
ul.appendChild(newLi);   // attend un Node — historique
ul.append(newLi);        // attend un Element OU une chaîne, accepte plusieurs arguments — à privilégier
ul.prepend(newLi);       // ajoute au tout début plutôt qu'à la fin
```
📌 `append`/`prepend` sont plus pratiques qu'`appendChild` (accepte du texte brut directement, plusieurs éléments d'un coup) — à préférer aujourd'hui.

## ⚠️ Un élément ne peut être qu'à un seul endroit
```javascript
ul.append(premierLi);   // si premierLi est déjà dans le DOM ailleurs, il est déplacé, pas dupliqué
```
Un nœud ajouté à un nouvel endroit du DOM est **retiré** de sa position précédente — jamais copié automatiquement. Pour dupliquer, voir `cloneNode` plus bas.

## 🛠️ Insérer à une position précise : `insertAdjacentElement`
```javascript
element.insertAdjacentElement("beforebegin", nouvelElement);   // juste avant l'élément
element.insertAdjacentElement("afterbegin", nouvelElement);    // au tout début de l'élément (= prepend)
element.insertAdjacentElement("beforeend", nouvelElement);     // à la toute fin (= append)
element.insertAdjacentElement("afterend", nouvelElement);      // juste après l'élément
```
💡 Pour ajouter au début/à la fin d'un élément, préférer `append`/`prepend` (plus lisibles) ; `insertAdjacentElement` devient utile pour insérer **avant** ou **après** un élément, ce que `append`/`prepend` ne permettent pas.

## 🛠️ Parcourir les enfants
| Propriété | Retourne |
|---|---|
| `children` | `HTMLCollection` des enfants qui sont des **éléments** (pas le texte) |
| `childNodes` | `NodeList` de **tous** les nœuds enfants, y compris les nœuds de texte (espaces...) |
| `firstElementChild` / `lastElementChild` | Premier/dernier enfant **élément** |
| `firstChild` / `lastChild` | Premier/dernier **nœud** enfant (peut être du texte) |
| `childElementCount` | Nombre d'enfants éléments (équivaut à `children.length`) |

## ⚠️ Collections "live" (dynamiques) vs figées
```javascript
const enfants = ul.children;        // HTMLCollection LIVE : se met à jour si le DOM change
const lis = document.querySelectorAll("li");   // NodeList figée : ne change plus après coup
```
📌 `children` (et d'autres propriétés comme `childNodes`) sont des collections **dynamiques** : supprimer un élément du DOM les met à jour automatiquement. Le retour de `querySelectorAll`, lui, est une **photo figée** au moment de l'appel — un élément supprimé ensuite reste compté dedans.

## 🛠️ Se déplacer latéralement / vers le haut
```javascript
element.parentElement;          // élément parent
element.parentNode;             // nœud parent (quasi toujours identique à parentElement)
element.nextElementSibling;     // élément suivant au même niveau (null si aucun)
element.previousElementSibling; // élément précédent (null si aucun)
element.nextSibling / element.previousSibling;   // équivalents au niveau des nœuds (texte inclus)
```

## 🛠️ Supprimer un élément
```javascript
element.remove();   // retire réellement l'élément du DOM (pas juste le cacher)
```

## 🛠️ Dupliquer un élément : `cloneNode`
```javascript
element.cloneNode();       // clone superficiel : SANS les enfants
element.cloneNode(true);   // clone profond : avec tous les enfants
```

## 💡 Vérifier une relation d'inclusion : `contains`
```javascript
ul.contains(li);   // true si li est un descendant de ul, false sinon
```

## 🛠️ Exemple complet : charger et afficher une liste depuis une API
```javascript
/**
 * @typedef {object} Post
 * @property {string} title
 * @property {string} body
 */

/**
 * Crée un élément HTML avec un tag et un contenu textuel.
 * @param {string} tagName
 * @param {string} contenu
 * @returns {HTMLElement}
 */
function createElementWithText(tagName, contenu) {
    const element = document.createElement(tagName);
    element.innerText = contenu;
    return element;
}

/**
 * @param {Post} post
 * @returns {HTMLElement}
 */
function createArticle(post) {
    const article = document.createElement("article");
    article.append(createElementWithText("h2", post.title));
    article.append(createElementWithText("p", post.body));
    return article;
}

async function main() {
    const wrapper = document.querySelector("#last-posts");
    const loader = createElementWithText("p", "Chargement...");
    wrapper.append(loader);

    try {
        const r = await fetch("https://jsonplaceholder.typicode.com/posts?_limit=5", {
            headers: { Accept: "application/json" },
        });
        if (!r.ok) {
            throw new Error("Erreur serveur");
        }
        const posts = await r.json();

        loader.remove();
        for (const post of posts) {
            wrapper.append(createArticle(post));
        }
    } catch {
        loader.innerText = "Impossible de charger les articles";
        loader.style.color = "red";
    }
}

main();
```

## ⚠️ Sécurité : ne jamais injecter du HTML non fiable
```javascript
// ❌ DANGEREUX si post.title vient d'une source non fiable
article.innerHTML = `<h2>${post.title}</h2>`;
// un utilisateur malveillant pourrait mettre du <style> ou pire du <script> dans title
```
`innerHTML` **interprète** ce qu'on lui donne comme du HTML — l'utiliser avec des données provenant de l'extérieur (formulaire, API tierce...) ouvre la porte à des injections (CSS malveillant au minimum, JavaScript malveillant au pire — attaque XSS). Utiliser `innerText`/`textContent`, ou construire les éléments avec `createElement`, garantit que le contenu est traité comme du **texte brut**, jamais interprété.

## 💡 Ne pas hésiter à créer des fonctions utilitaires
La manipulation "manuelle" du DOM (créer un élément, définir son texte, l'ajouter) demande souvent plusieurs lignes pour une opération très simple. Se créer des petites fonctions comme `createElementWithText` (ci-dessus) évite de répéter ce schéma partout et rend le code final beaucoup plus lisible.

## ✅ À retenir
`querySelector`/`querySelectorAll` couvrent la quasi-totalité des besoins de sélection. `innerHTML` est pratique mais dangereux avec des données non fiables — préférer `innerText`/`textContent`/`createElement` dans ce cas. `append`/`prepend` pour ajouter un élément, `insertAdjacentElement` pour insérer avant/après un élément existant, `remove()` pour le supprimer. `cloneNode(true)` pour dupliquer un élément avec ses enfants.
