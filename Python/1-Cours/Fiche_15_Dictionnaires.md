# Fiche 15 : Dictionnaires

## 📌 Définition
Un dictionnaire est un tableau associatif `clé: valeur`. Les clés sont **uniques**, sans ordre garanti.

## 🛠️ Création et accès
```python
dico = {}                                        # vide
dico = {"prenom": "Jeremie", "Age": "12"}
print(dico["prenom"])                             # accès par clé
```

## 🛠️ Ajout / modification / suppression
```python
dico["nouvelleClef"] = "Test"       # ajoute (ou modifie si la clé existe déjà)
valeur_supprimee = dico.pop("Age")  # supprime et renvoie la valeur
del dico["prenom"]                   # supprime sans récupérer la valeur
```

## 🛠️ Vérification d'existence
```python
if "prenom" in dico:
    print("La clef existe")
```

## 🛠️ Parcourir un dictionnaire
```python
for key in dico.keys():
    print("Clef:", key)

for val in dico.values():
    print("Valeur:", val)

for x, y in dico.items():   # x, y = tuple (clé, valeur)
    print("Clef {} : Valeur: {}".format(x, y))
```

## 🛠️ **kwargs — paramètres nommés en dictionnaire
```python
def ma_fonction(**param):
    print(param)

ma_fonction(var1="hello", var2="Salut")
# {'var1': 'hello', 'var2': 'Salut'}
```

## ⚠️ Piège : copie vs référence
```python
dico2 = dico1          # référence, pas une copie
dico2 = dico1.copy()   # vraie copie
```

## ✅ À retenir
Même piège que les listes : `dico2 = dico1` crée une référence, pas une copie. `**param` (comme `*args` pour les fonctions) capture un nombre variable d'arguments nommés sous forme de dictionnaire.
