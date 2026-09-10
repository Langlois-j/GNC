# Fiche 02 : Variables & types

## 📌 Les 4 types de base
| Type | Mot-clé | Exemple |
|---|---|---|
| Entier | `int` | `10` |
| Réel | `float` | `10.6` |
| Chaîne | `str` | `"Bonjour"` |
| Booléen | `bool` | `True` (=1) / `False` (=0) |

## 🛠️ Déclaration et affichage
```python
le_nombre_entier = 10
print("Le type est :", type(le_nombre_entier))   # <class 'int'>

la_chaine = "Bonjour"
le_booleen = True
```

## 💡 Saisie utilisateur et cast
`input()` renvoie **toujours** une chaîne de caractères → il faut la "caster" (convertir) vers le bon type.
```python
age_utilisateur = input("Indiquez l'âge : ")
age_utilisateur = int(age_utilisateur)   # cast en entier

le_tarif = input("Indiquez le tarif : ")
le_tarif_ht = int(le_tarif) / 1.2
```

## 💡 Formatage de chaîne
```python
print("Le tarif HT de {} est de {}".format(le_tarif, le_tarif_ht))
```

## ✅ À retenir
`print()` = afficher, `input()` = saisir (renvoie une chaîne), `type()` = connaître le type d'une variable.
