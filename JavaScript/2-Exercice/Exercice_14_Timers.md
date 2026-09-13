# Exercice 14 : Timers et asynchrone

## Exercice 1 — Feu tricolore
Écrivez une fonction `feuTricolore()` qui affiche successivement, avec **1 seconde** entre chaque affichage :
```
Rouge
Orange
Vert
```
puis s'arrête (n'affiche rien d'autre après). Utilisez `setTimeout` (une seule chaîne d'appels, pas de boucle).

## Exercice 2 — Compte à rebours avec arrêt anticipé
Écrivez une fonction `compteARebours(depart)` qui affiche les nombres de `depart` jusqu'à `0`, un par seconde, à l'aide de `setInterval`.
1. N'oubliez pas de nettoyer l'intervalle une fois arrivé à `0`.
2. Bonus : ajoutez un second paramètre `arretA` (par défaut `0`) permettant d'arrêter le compte à rebours à une autre valeur que `0` (ex : `compteARebours(10, 5)` affiche `10, 9, 8, 7, 6, 5` puis s'arrête).

## Exercice 3 — Course entre deux timers
Lancez en même temps deux "coureurs" asynchrones :
- Le coureur A affiche `"A avance"` toutes les 500 ms.
- Le coureur B affiche `"B avance"` toutes les 800 ms.

Le premier qui atteint 5 affichages doit afficher `"X a gagné !"` (en remplaçant X par A ou B) et **arrêter les deux timers** (le perdant ne doit plus rien afficher après).
