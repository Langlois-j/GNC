# Exercice 03 : POO (classes, propriétés, héritage)

## Exercice 1 — Classe de base
Crée une classe `Livre` avec un constructeur (`titre`, `auteur`, `nb_pages`) et une méthode `resume()` qui affiche `"Titre par Auteur (X pages)"`.

## Exercice 2 — Attribut de classe
Ajoute un attribut de classe `nb_livres_crees` qui s'incrémente à chaque instanciation, et une méthode statique `regles_bibliotheque()` qui affiche une règle fixe.

## Exercice 3 — Propriété
Modifie la classe `Livre` pour que `nb_pages` soit géré via une `property` : le setter doit refuser une valeur négative (mettre 0 dans ce cas).

## Exercice 4 — Héritage
Crée une classe `LivreNumerique` héritant de `Livre`, avec un attribut supplémentaire `taille_mo`. Utilise `super()` dans le constructeur.

## Exercice 5 — Vérifications
Instancie un `LivreNumerique` et vérifie avec `isinstance()` et `issubclass()` qu'il est bien lié à `Livre`.
