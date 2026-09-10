# Fiche : Décorateurs

## 📌 Définition
Fonction qui modifie/enrichit le comportement d'une autre fonction sans la modifier directement.

## 🛠️ Syntaxe
```python
def mon_decorateur(fonction):
    def wrapper(*args, **kwargs):
        print("Avant l'appel")
        resultat = fonction(*args, **kwargs)
        print("Après l'appel")
        return resultat
    return wrapper

@mon_decorateur
def dire_bonjour(nom):
    print(f"Bonjour {nom}")
```

## 💡 Cas d'usage fréquents
- Chronométrer une fonction (`@timer`)
- Logger des appels (`@log`)
- Vérifier des permissions (`@require_auth`)
- Cache de résultats (`@functools.lru_cache`)

## ✅ À retenir
Un décorateur = une fonction qui prend une fonction et retourne une fonction. `functools.wraps` permet de conserver le nom/docstring de la fonction d'origine.
