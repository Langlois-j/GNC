# Fiche 03 : Opérations arithmétiques

## 📌 Opérateurs de base
| Opérateur | Rôle |
|---|---|
| `+` | Addition |
| `-` | Soustraction |
| `*` | Multiplication |
| `/` | Division classique (résultat en float) |
| `%` | Modulo (reste de la division euclidienne) |

## 🛠️ Exemples
```python
op_a = int(input("Premier chiffre : "))
op_b = int(input("Deuxième chiffre : "))

res = op_a + op_b
res += 1   # incrémentation automatique

# Division euclidienne (quotient entier + reste)
quotient = int(op_a / op_b)
reste = op_a % op_b
print("{} / {} = {} reste {}".format(op_a, op_b, quotient, reste))

# Division classique
division = op_a / op_b
```

## ✅ À retenir
`/` renvoie toujours un `float` en Python 3, même si la division "tombe juste". Pour une division entière, utiliser `//` ou caster avec `int()`.
