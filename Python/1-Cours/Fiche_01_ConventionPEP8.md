# Fiche 01 : Convention PEP8

## 📌 Définition
PEP8 est le guide de style officiel Python : règles de nommage et de mise en forme pour un code lisible et cohérent.

## 🛠️ Règles clés (issues du projet)
```python
# Classes en CamelCase
class MaClasse:
    """Docstring : description de la classe"""
    pass

# Variables et fonctions en snake_case
ma_variable = 1
def ma_fonction():
    pass

# Alignement des paramètres sur plusieurs lignes
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print("la variable =", var_one)

# Un espace après chaque virgule (listes, paramètres)
ma_liste = [0, 1, 2]

# Tuple à un seul élément : virgule sans espace avant
mon_tuple = (1,)

# Espace autour des opérateurs
res = 1 + 2

# Pas d'espace dans un calcul entre parenthèses
resultat = (2 * 3) + 8

# Un import par ligne
import os
import sys

# Pas d'espace avant , ; :
if x == 4:
    print(x, y)
```

## ✅ À retenir
Deux conventions de nommage existent (camelCase / snake_case) — Python privilégie **snake_case** pour les variables/fonctions et **CamelCase** pour les classes.
