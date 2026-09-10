# Fiche 09 : Classes et attributs

## 🛠️ Structure de base
```python
class Humain:
    """Cette classe crée un humain"""

    # Attribut de classe (partagé par toutes les instances)
    humain_cree = 0

    def __init__(self, param1, param2):
        # Attributs d'instance (self = l'objet lui-même)
        self.nom = param1
        self.age = param2
        Humain.humain_cree += 1

    def parler(self, msg):
        print(self.nom, "dit:", msg)
```

## 🛠️ Méthode de classe (`@classmethod`)
Opère sur la **classe** elle-même, pas sur une instance précise (`cls` au lieu de `self`).
```python
def changer_nombre(cls, nouveau_nombre):
    Humain.humain_cree += nouveau_nombre
changer_nombre = classmethod(changer_nombre)
```

## 🛠️ Méthode statique (`@staticmethod`)
Peut être appelée **sans instance**, n'a accès ni à `self` ni à `cls`.
```python
def definition():
    print("Un humain doit vivre sur une planète avec de l'oxygène !")
definition = staticmethod(definition)

Humain.definition()   # appel direct sur la classe
```

## 🛠️ Utilisation
```python
h1 = Humain("Albert", 12)
h2 = Humain("Ginette", 20)
h1.parler("Bonjour, je suis un objet")
print("humains créés :", Humain.humain_cree)
```

## ✅ À retenir
`self` = l'instance courante (méthode standard). `cls` = la classe elle-même (méthode de classe). En Python, les attributs sont accessibles directement (pas de vrais "private" natifs, voir fiche Propriétés).
