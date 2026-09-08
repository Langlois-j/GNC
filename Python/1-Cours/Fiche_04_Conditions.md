# Fiche 04 : Conditions

## 📌 Opérateurs de comparaison
| Opérateur | Signification |
|---|---|
| `<` `>` | inférieur / supérieur à |
| `<=` `>=` | inférieur ou égal / supérieur ou égal |
| `==` | égal |
| `!=` | différent |

## 📌 Opérateurs logiques
`and` (ET), `or` (OU), `in` / `not in` (appartenance)

## 🛠️ if / elif / else
```python
var_a = 17

if var_a >= 18 and var_a <= 50:
    print("majeur")
elif var_a > 50:
    print("senior")
else:
    print("mineur")

# Compris entre deux valeurs (syntaxe raccourcie)
if 0 < var_a <= 18:
    ...

# Test d'appartenance
lettre = "aeiou"
if "m" in lettre:
    print("voyelle")
else:
    print("consonne")
```

## 🛠️ match / case (Python 3.10+)
```python
exemple = 3
match exemple:
    case 1:
        print("cas 1")
    case 2:
        print("cas 2")
    case 3:
        print("cas 3")
    case _:
        print("autre cas")   # cas par défaut
```

## ✅ À retenir
`match/case` remplace avantageusement de longues chaînes `if/elif` quand on compare une seule variable à plusieurs valeurs fixes. `case _` = cas par défaut (équivalent du `else`).
