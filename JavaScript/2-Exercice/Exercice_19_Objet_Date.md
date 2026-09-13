# Exercice 19 : L'objet `Date`

## Exercice 1 — Fonction pure `addHours`
Écrivez une fonction pure `addHours(date, n)` (qui ne modifie pas la date reçue en paramètre) qui renvoie une nouvelle date décalée de `n` heures. Vérifiez que la date d'origine n'est pas modifiée après l'appel.

## Exercice 2 — Âge en années
Écrivez une fonction `calculerAge(dateNaissance)` qui renvoie l'âge en années révolues à partir d'une date de naissance (attention aux anniversaires pas encore passés cette année — quelqu'un né le 20 décembre n'a pas encore eu son anniversaire en septembre).

## Exercice 3 — Jour ouvré ou week-end ?
Écrivez une fonction `estWeekend(date)` qui renvoie `true` si la date tombe un samedi ou un dimanche.

## Exercice 4 — Compte à rebours lisible
Écrivez une fonction `tempsRestant(dateCible)` qui affiche une chaîne du type `"Dans 3 jours"`, `"Dans 5 heures"` ou `"Dans 2 minutes"` selon l'écart avec la date actuelle (choisissez la plus grande unité pertinente : si l'écart dépasse un jour, affichez des jours ; sinon des heures ; sinon des minutes).
