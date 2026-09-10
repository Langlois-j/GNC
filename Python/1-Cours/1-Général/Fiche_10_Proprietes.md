# Fiche 10 : Propriétés (property)

## 📌 Principe
Une propriété encapsule un attribut derrière un getter/setter/deleter, tout en gardant une syntaxe d'accès simple (`objet.attribut`).

## 🛠️ Convention de nommage
Un `_` devant un attribut/méthode signale qu'il ne doit pas être manipulé directement de l'extérieur.

## 🛠️ Exemple complet
```python
class Humain:
    def __init__(self, nom, age):
        self.nom = nom
        self._age = age

    def _get_age(self):
        try:
            return self._age
        except AttributeError:
            print("L'âge n'existe plus !")

    def _set_age(self, nouvel_age):
        self._age = 0 if nouvel_age <= 0 else nouvel_age

    def _del_age(self):
        del self._age

    # property(getter, setter, deleter, docstring)
    age = property(_get_age, _set_age, _del_age, "Je gère l'âge d'un humain")
```

## 🛠️ Utilisation — on passe toujours par la propriété
```python
h1 = Humain("Jeremie", 20)
print(h1.age)     # appelle le getter
h1.age = 15       # appelle le setter (validation possible)
del h1.age        # appelle le deleter
```

## 💡 Propriété en lecture seule (pas de getter)
```python
age2 = property(None, _set_age, None, "ceci est un essai")
```

## ✅ À retenir
Si une méthode getter ne fait que `return`, il est parfois inutile de la créer explicitement — mais l'utiliser via `property()` permet d'ajouter une validation invisible pour l'utilisateur de la classe (ex : empêcher un âge négatif).
