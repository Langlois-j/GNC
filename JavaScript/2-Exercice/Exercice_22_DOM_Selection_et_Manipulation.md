# Exercice 22 : Manipuler le DOM — les bases

On suppose la structure HTML suivante disponible dans la page pour tous les exercices :
```html
<ul id="fruits">
    <li class="stock">Pomme</li>
    <li>Banane</li>
    <li class="stock">Cerise</li>
</ul>
```

## Exercice 1 — Sélection et lecture
1. Sélectionnez la liste `#fruits` et affichez son `innerHTML`.
2. Sélectionnez tous les `li` ayant la classe `stock` (en un seul sélecteur CSS) et affichez leur nombre.
3. Convertissez le résultat de `querySelectorAll("li")` en vrai tableau et utilisez `.map()` pour obtenir un tableau des textes (`["Pomme", "Banane", "Cerise"]`).

## Exercice 2 — Modifier le DOM
1. Ajoutez un nouveau `<li>Kiwi</li>` à la fin de la liste, sans utiliser `innerHTML`.
2. Ajoutez la classe `stock` au `<li>` contenant "Banane" (sélectionné dynamiquement, pas en dur).
3. Supprimez de la liste l'élément contenant "Cerise".

## Exercice 3 — Créer une liste dynamiquement
Écrivez une fonction `creerListe(items)` qui, à partir d'un tableau de chaînes de caractères, crée et renvoie un élément `<ul>` contenant un `<li>` par élément du tableau — sans jamais utiliser `innerHTML` (pour éviter tout risque d'injection si `items` provient d'une source externe).

## Exercice 4 — Piège des collections live
Sans exécuter le code, indiquez ce qu'affichera chaque `console.log` :
```javascript
const ul = document.querySelector("#fruits");
const enfantsLive = ul.children;
const enfantsFiges = ul.querySelectorAll("li");

ul.lastElementChild.remove();

console.log(enfantsLive.length);
console.log(enfantsFiges.length);
```
Expliquez la différence de comportement en une phrase.
