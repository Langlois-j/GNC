# Fiche 08 : Gestion des erreurs

## 📌 Structure try / except / else / finally
| Bloc | Rôle |
|---|---|
| `try` | Code à tester |
| `except <Erreur>` | Exécuté si cette erreur précise est levée |
| `except` (sans type) | Attrape toute erreur non prévue |
| `else` | Exécuté si **aucune** erreur ne s'est produite |
| `finally` | Exécuté **dans tous les cas** |

## 🛠️ Exemple simple
```python
age_user = input("Quel âge as-tu ?")
try:
    age_user = int(age_user)
except:
    print("L'âge est incorrect !")
else:
    print("Tu as", age_user, "ans.")
finally:
    print("Merci pour votre réponse")
```

## 🛠️ Erreurs typées
```python
try:
    nb1 = int(input("Premier nombre : "))
    nb2 = int(input("Deuxième nombre : "))
    res = nb1 / nb2
except ZeroDivisionError:
    print("Division par 0 interdite")
except ValueError:
    print("Nombre invalide")
except:
    print("Saisie incorrecte")
else:
    print(nb1, "/", nb2, "=", res)
finally:
    print("Fin du calcul")
```

## 🛠️ raise et assert
```python
# Lever une erreur soi-même
if age < 0:
    raise ValueError("Âge invalide")

# assert : lève une AssertionError si la condition est fausse
age_test = int(input("Quel âge as-tu ?"))
try:
    assert age_test > 18
except AssertionError:
    print("Erreur d'âge : personne mineure")
```

## ✅ À retenir
Toujours attraper les erreurs spécifiques (`ZeroDivisionError`, `ValueError`...) **avant** un `except` générique, sinon ce dernier masquera les cas précis.
