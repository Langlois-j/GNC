# Correction : List Comprehensions & Décorateurs

## Exercice 1
```python
resultat = [n for n in range(1, 51) if n % 3 == 0 or n % 5 == 0]
```

## Exercice 2
```python
mots = ["python", "git", "ia", "sql"]
longueurs = {mot: len(mot) for mot in mots}
# {'python': 6, 'git': 3, 'ia': 2, 'sql': 3}
```

## Exercice 3
```python
import time
from functools import wraps

def chrono(fonction):
    @wraps(fonction)
    def wrapper(*args, **kwargs):
        debut = time.perf_counter()
        resultat = fonction(*args, **kwargs)
        duree = time.perf_counter() - debut
        print(f"{fonction.__name__} exécutée en {duree:.4f}s")
        return resultat
    return wrapper
```

## Exercice 4
```python
prix = 42.5
quantite = 3
total = prix * quantite
print(f"Total : {total:.2f} € ({quantite} x {prix:.2f} €)")
```

## Exercice 5
```python
from contextlib import contextmanager

@contextmanager
def connexion():
    print("Connexion ouverte")
    try:
        yield
    finally:
        print("Connexion fermée")
```
