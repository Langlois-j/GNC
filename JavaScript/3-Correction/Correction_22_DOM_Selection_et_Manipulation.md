# Correction 22 : Manipuler le DOM — les bases

## Exercice 1
```javascript
const fruits = document.querySelector("#fruits");
console.log(fruits.innerHTML);

const enStock = document.querySelectorAll("#fruits li.stock");
console.log(enStock.length);   // 2

const textes = Array.from(document.querySelectorAll("#fruits li")).map((li) => li.textContent);
console.log(textes);   // ["Pomme", "Banane", "Cerise"]
```
📌 `li.stock` (sans espace) sélectionne les `li` qui ont la classe `stock` — combinaison de sélecteurs CSS classique, rien de spécifique au JavaScript.

## Exercice 2
```javascript
const fruits = document.querySelector("#fruits");

const kiwi = document.createElement("li");
kiwi.textContent = "Kiwi";
fruits.append(kiwi);

const banane = Array.from(fruits.querySelectorAll("li")).find((li) => li.textContent === "Banane");
banane.classList.add("stock");

const cerise = Array.from(fruits.querySelectorAll("li")).find((li) => li.textContent === "Cerise");
cerise.remove();
```
⚠️ Piège évité : sélectionner "Banane" en dur avec `querySelector("li:nth-child(2)")` casserait dès que l'ordre des éléments change. Chercher par contenu textuel (`find`) est plus robuste ici, même si ça demande de repasser par un tableau.

## Exercice 3
```javascript
/**
 * @param {string[]} items
 * @returns {HTMLUListElement}
 */
function creerListe(items) {
    const ul = document.createElement("ul");
    for (const item of items) {
        const li = document.createElement("li");
        li.textContent = item;   // jamais innerHTML : item pourrait contenir du HTML malveillant
        ul.append(li);
    }
    return ul;
}

document.body.append(creerListe(["Pomme", "Banane", "Cerise"]));
```

## Exercice 4
```javascript
console.log(enfantsLive.length);    // 2 — collection dynamique, mise à jour après le remove()
console.log(enfantsFiges.length);   // 3 — NodeList figée au moment de l'appel, avant la suppression
```
📌 `ul.children` est une `HTMLCollection` **live** : elle reflète l'état actuel du DOM à chaque lecture. `querySelectorAll(...)` renvoie, lui, une **photo figée** de la liste au moment de l'appel — elle ne se met pas à jour même si le DOM change ensuite.
