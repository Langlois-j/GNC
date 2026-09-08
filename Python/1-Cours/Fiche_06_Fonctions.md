# Fiche 06 : Fonctions

## 📌 Règles de base
- Une fonction fait **une seule chose** à la fois
- Elle peut recevoir des paramètres (obligatoires ou non)
- Elle peut renvoyer une ou plusieurs valeurs

## 🛠️ Paramètres obligatoires / avec valeur par défaut
```python
def calcul_addition_obligatoire(nb1, nb2):
    return nb1 + nb2

def calcul_addition(nb1=0, nb2=0):
    return nb1 + nb2

calcul_addition(2)                # nb2 prend la valeur par défaut 0
calcul_addition(nb1=2, nb2=3)     # arguments nommés, ordre libre
calcul_addition(nb2=3, nb1=2)     # fonctionne aussi dans le désordre
```

## 🛠️ Nombre de paramètres indéfini (*args)
```python
def liste_elements(*items):
    for elt in items:
        print(elt)

liste_elements("Voiture", "Maison", "Animal")
```

## 🛠️ Retour de plusieurs valeurs
```python
def renvoi_multiple():
    return (101, 102)

val1, val2 = renvoi_multiple()
```

## 🛠️ Fonction lambda
Une fonction anonyme, sur une seule ligne, qui ne fait qu'une chose et renvoie une seule instruction.
```python
calcul_plus = lambda a, b: a + b
print(calcul_plus(2, 3))   # 5

calculer_tva = lambda montant_ht: montant_ht * 1.2
```

## ✅ À retenir
`*args` capture un nombre variable d'arguments positionnels sous forme de tuple. Les fonctions déjà connues : `print()`, `input()`, `type()`, `int()/float()/bool()`, `format()`.
