# Fiche : List Comprehensions

## 📌 Définition
Syntaxe concise pour créer une liste en une seule ligne, à partir d'une boucle + condition optionnelle.

## 🛠️ Syntaxe
```python
[expression for élément in itérable if condition]
```

## 💡 Exemples
```python
carres = [x**2 for x in range(10)]
pairs = [x for x in range(20) if x % 2 == 0]
# Version dict
carres_dict = {x: x**2 for x in range(5)}
```

## ⚠️ Piège courant
Ne pas imbriquer plus de 2 niveaux de list comprehension → devient illisible, préférer une boucle classique.

## ✅ À retenir
Plus rapide et plus pythonique qu'une boucle `for` + `append()`, mais à réserver aux cas simples.
