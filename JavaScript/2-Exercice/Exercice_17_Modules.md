# Exercice 17 : Les modules

## Exercice 1 — Module de chaînes de caractères
Créez un fichier `chaines.js` qui exporte (en export nommé) deux fonctions :
- `capitaliser(texte)` : met la première lettre en majuscule.
- `inverser(texte)` : renvoie le texte à l'envers.

Depuis un fichier `index.js`, importez les deux fonctions et testez-les.

## Exercice 2 — Export par défaut + export nommé
Créez un fichier `logger.js` qui :
- exporte **par défaut** une fonction `log(message)` qui affiche `[LOG] message`.
- exporte, en export **nommé**, une fonction `logErreur(message)` qui affiche `[ERREUR] message`.

Importez les deux dans `index.js` en une seule ligne d'`import`.

## Exercice 3 — Fichier "carrefour"
En réutilisant `chaines.js` et `logger.js` des exercices précédents, créez un fichier `utils.js` qui réexporte tout ce dont on pourrait avoir besoin (`capitaliser`, `inverser`, l'export par défaut de `logger.js` sous le nom `log`), afin que `index.js` n'ait plus qu'à faire `import { capitaliser, inverser, log } from "./utils.js"`.

## Exercice 4 — Chargement à la demande
Imaginez un fichier `rapport.js` qui exporte par défaut une fonction `genererRapport()` un peu coûteuse à charger. Écrivez, dans `index.js`, le code qui n'importe ce module **que si** une variable `utilisateurConnecte` vaut `true`, en utilisant l'import dynamique `import()`.
