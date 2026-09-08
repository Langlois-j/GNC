# Fiche 11 : Héritage

## 🛠️ Classe mère / classe fille
```python
class Animal:
    def __init__(self, nom_animal, age_animal):
        self.nom = nom_animal
        self.age = age_animal

    def nourrir(self):
        return "L'animal {} mange".format(self.nom)

class Chien(Animal):
    def __init__(self, nom_chien, age_chien, race_chien):
        Animal.__init__(self, nom_chien, age_chien)   # appel du constructeur parent
        self.race = race_chien

    def aboyer(self):
        return "Le chien {} de race {} aboie".format(self.nom, self.race)
```

## 💡 `super()` — raccourci pour appeler la classe parente
```python
class Oiseau(Animal):
    def __init__(self, nom_oiseau, age_oiseau, espece_oiseau):
        super().__init__(nom_oiseau, age_oiseau)   # équivalent à Animal.__init__(self, ...)
        self.espece = espece_oiseau
```

## 🛠️ Vérifications de type
```python
isinstance(objet, Classe)        # l'objet est-il une instance de Classe (ou d'une classe fille) ?
issubclass(ClasseFille, ClasseMere)   # ClasseFille hérite-t-elle de ClasseMere ?
```
```python
le_chien = Chien("Kiki", 5, "Caniche")
print(isinstance(le_chien, Animal))       # True
print(issubclass(Chien, Animal))          # True
```

## ✅ À retenir
La classe fille hérite des attributs et méthodes de la classe mère, et peut en ajouter de nouveaux (ex : `aboyer()` n'existe que sur `Chien`). `super()` est préférable à `NomClasseParente.__init__()` car il reste valide même si la hiérarchie de classes change.
