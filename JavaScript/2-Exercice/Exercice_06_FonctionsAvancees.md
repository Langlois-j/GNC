# Exercice 06 : Fonctions — mise en pratique avancée

## Exercice 1 — Palindrome
Créez une fonction `isPalindrome(str)` qui renvoie `true` si le mot se lit de la même façon dans les deux sens (ex : "kayak"), en ignorant la casse (majuscules/minuscules).

## Exercice 2 — Moyennes d'élèves
À partir de :
```javascript
const etudiants = [
    { nom: "John", notes: [12, 15, 16, 12, 15] },
    { nom: "Jane", notes: [18, 15, 17, 16, 17] },
    { nom: "Manon", notes: [19, 12, 18, 18, 17] },
];
```
1. Ajoutez une propriété `moyenne` à chaque étudiant.
2. Triez les étudiants du meilleur au moins bon.
3. Affichez un podium "Top 3" avec nom + moyenne de chacun.
4. Bonus : ajoutez aussi la meilleure (`best`) et la moins bonne (`worst`) note de chaque étudiant.

## Exercice 3 — Fréquence de mots
À partir d'une phrase (`const phrase = "..."`), construisez un objet indiquant le nombre d'occurrences de chaque mot (insensible à la casse, sans ponctuale). Affichez les 3 mots les plus fréquents.
