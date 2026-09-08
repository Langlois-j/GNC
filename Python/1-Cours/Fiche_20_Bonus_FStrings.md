# Fiche : F-strings

## 📌 Définition
Façon moderne (Python 3.6+) de formater des chaînes en insérant des expressions directement dans le texte.

## 🛠️ Syntaxe
```python
nom = "Julien"
age = 30
print(f"{nom} a {age} ans")
```

## 💡 Fonctionnalités avancées
```python
# Formatage numérique
prix = 19.999
print(f"{prix:.2f} €")  # 20.00 €

# Alignement
print(f"{nom:>10}")  # aligné à droite sur 10 caractères

# Debug rapide (Python 3.8+)
print(f"{nom=}")  # affiche : nom='Julien'

# Expressions inline
print(f"{age * 2}")
```

## ✅ À retenir
Plus lisible et plus rapide que `.format()` ou `%`. À privilégier systématiquement pour le formatage de chaînes.
