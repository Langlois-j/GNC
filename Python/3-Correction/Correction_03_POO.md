# Correction 03 : POO

## Exercice 1
```python
class Livre:
    def __init__(self, titre, auteur, nb_pages):
        self.titre = titre
        self.auteur = auteur
        self.nb_pages = nb_pages

    def resume(self):
        print("{} par {} ({} pages)".format(self.titre, self.auteur, self.nb_pages))
```

## Exercice 2
```python
class Livre:
    nb_livres_crees = 0

    def __init__(self, titre, auteur, nb_pages):
        self.titre = titre
        self.auteur = auteur
        self.nb_pages = nb_pages
        Livre.nb_livres_crees += 1

    def regles_bibliotheque():
        print("Un livre emprunté doit être rendu sous 3 semaines.")
    regles_bibliotheque = staticmethod(regles_bibliotheque)
```

## Exercice 3
```python
class Livre:
    def __init__(self, titre, auteur, nb_pages):
        self.titre = titre
        self.auteur = auteur
        self._nb_pages = nb_pages

    def _get_nb_pages(self):
        return self._nb_pages

    def _set_nb_pages(self, valeur):
        self._nb_pages = 0 if valeur < 0 else valeur

    nb_pages = property(_get_nb_pages, _set_nb_pages)
```

## Exercice 4
```python
class LivreNumerique(Livre):
    def __init__(self, titre, auteur, nb_pages, taille_mo):
        super().__init__(titre, auteur, nb_pages)
        self.taille_mo = taille_mo
```

## Exercice 5
```python
mon_ebook = LivreNumerique("Python 101", "Jérémie", 250, 4.5)
print(isinstance(mon_ebook, Livre))        # True
print(issubclass(LivreNumerique, Livre))   # True
```
