# Exercice 07 : Les classes — formes géométriques

## Exercice 1 — Rectangle
Créez une classe `Rectangle` construite avec une largeur (`width`) et une hauteur (`height`). Ajoutez :
- un getter `perimeter` (2×largeur + 2×hauteur)
- un getter `isValid` qui renvoie `false` si une dimension est ≤ 0

## Exercice 2 — Square (héritage)
Créez une classe `Square` qui hérite de `Rectangle` (`extends`), construite avec une seule dimension (largeur = hauteur).

## Exercice 3 — Comparaison
Ajoutez une méthode `isBiggerThan(shape)` (sur `Rectangle`, donc héritée par `Square`) qui compare les périmètres de deux formes.

## Exercice 4 — Bibliothèque
Créez une classe `Book` (titre, nombre de pages, page courante = 1 au départ) avec :
- une méthode `nextPage()` (n'avance pas au-delà de la dernière page)
- une méthode `close()` (revient à la page 1)

Créez une classe `Library` avec :
- `addBook(book)` — ajoute un livre
- `addBooks(books)` — ajoute plusieurs livres d'un coup
- `findBooksByLetter(letter)` — renvoie les livres dont le titre commence par cette lettre (insensible à la casse)
