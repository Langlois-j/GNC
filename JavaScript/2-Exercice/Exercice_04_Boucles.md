# Exercice 04 : Les boucles

## Exercice 1 — Compte à rebours
Demandez à l'utilisateur un chiffre entre 0 et 10 (`prompt`). Si le chiffre n'est pas dans cet intervalle, affichez une erreur en console. Sinon, affichez tous les chiffres depuis ce nombre jusqu'à 0 (ex : saisie `9` → affiche `9 8 7 6 5 4 3 2 1 0`).

## Exercice 2 — Jeu du nombre mystère
Une variable `guess` contient un nombre fixé à l'avance (ex : `8`). Demandez à l'utilisateur de deviner ce nombre en boucle (`prompt`), jusqu'à ce qu'il trouve la bonne valeur. Affichez `"Bravo, vous avez deviné"` à la fin.

## Exercice 3 — Jeu avec indices
Améliorez l'exercice 2 : à chaque essai raté, indiquez si la proposition est **trop petite** ("+") ou **trop grande** ("-") par rapport au nombre à deviner.

## Exercice 4 — Parcours de tableau
Étant donné `const fruits = ["pomme", "banane", "kiwi", "mangue"];`, affichez chaque fruit précédé de son index, avec `for`, puis avec `for...of`, puis avec `for...in`. Comparez les 3 résultats.
