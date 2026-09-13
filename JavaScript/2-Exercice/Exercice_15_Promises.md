# Exercice 15 : Les promesses

## Exercice 1 — Promisifier un timer
Écrivez une fonction `delai(ms, valeur)` qui renvoie une **promesse** résolue après `ms` millisecondes avec `valeur`. Utilisez-la pour afficher `"1 seconde plus tard"` après 1 seconde, en chaînant avec `.then()` (pas de `async`/`await` pour cet exercice).

## Exercice 2 — Chaîne de promesses
En réutilisant `delai()` :
1. Écrivez une chaîne `.then()` qui : attend 1 seconde, affiche `"Étape 1"`, puis attend encore 1 seconde, affiche `"Étape 2"`, puis attend encore 1 seconde et affiche `"Étape 3"`.
2. Ajoutez un `.catch()` final qui affiche `"Une erreur est survenue"` si une étape échoue.
3. Modifiez temporairement l'étape 2 pour qu'elle rejette la promesse (avec `Promise.reject("boom")`) et vérifiez que l'étape 3 n'est jamais atteinte, mais que le `.catch()` s'exécute bien.

## Exercice 3 — Async/await et gestion d'erreur
Réécrivez l'exercice 2 (version qui réussit, sans le rejet volontaire) en utilisant une fonction `async` avec `await`, entourée d'un `try`/`catch`.

## Exercice 4 — Course de promesses
À l'aide de `delai()`, créez 3 promesses qui se résolvent respectivement après 300 ms, 700 ms et 500 ms, chacune avec un nom différent ("A", "B", "C").
1. Utilisez `Promise.race(...)` pour afficher quelle promesse a fini en premier.
2. Utilisez `Promise.all(...)` pour afficher les 3 résultats dans l'ordre où ils ont été passés (pas dans l'ordre de résolution).
3. Bonus : remplacez une des trois promesses par un rejet (`delai` qui échoue) et observez la différence de comportement entre `Promise.all` et `Promise.allSettled` sur ce nouveau jeu de promesses.
