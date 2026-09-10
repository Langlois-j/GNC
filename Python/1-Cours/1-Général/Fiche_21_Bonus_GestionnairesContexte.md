# Fiche : Gestionnaires de contexte (with)

## 📌 Définition
Le mot-clé `with` garantit qu'une ressource (fichier, connexion DB...) est correctement fermée/libérée, même en cas d'erreur.

## 🛠️ Syntaxe
```python
with open("fichier.txt", "r") as f:
    contenu = f.read()
# f est automatiquement fermé ici, même si une exception survient
```

## 💡 Créer son propre gestionnaire de contexte
```python
from contextlib import contextmanager

@contextmanager
def mon_contexte():
    print("Ouverture")
    yield
    print("Fermeture")

with mon_contexte():
    print("Travail en cours")
```

## 💡 Cas d'usage
- Fichiers (`open`)
- Connexions base de données (SQLAlchemy sessions)
- Verrous (`threading.Lock`)
- Mesure de temps d'exécution

## ✅ À retenir
Évite les fuites de ressources et les `try/finally` répétitifs. Pertinent pour `officerail_be` avec les sessions PostgreSQL.
