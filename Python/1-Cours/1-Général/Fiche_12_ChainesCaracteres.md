# Fiche 12 : Chaînes de caractères

## ⚠️ Point clé
Toute méthode de chaîne travaille sur une **copie** — la chaîne d'origine n'est jamais modifiée, il faut réaffecter le résultat.

## 🛠️ Transformation de casse
```python
ma_chaine = "JE suis une chaine DE caractère"
ma_chaine.lower()        # tout en minuscule
ma_chaine.upper()        # TOUT EN MAJUSCULE
ma_chaine.capitalize()   # Première lettre en majuscule
ma_chaine.title()        # Premiere Lettre De Tous Les Mots
```

## 🛠️ Recherche / remplacement
```python
ma_chaine.center(100, "_")       # centre la chaîne sur 100 caractères
ma_chaine.find("suis")           # renvoie l'indice, ou -1 si non trouvé
ma_chaine.index("bonjour")       # lève ValueError si non trouvé
ma_chaine.strip()                # retire les espaces au début/fin
ma_chaine.replace("a", "x", 2)   # remplace les 2 premières occurrences
ma_chaine.split("/")             # découpe en liste selon un séparateur
```

## 🛠️ Vérifications (renvoient un booléen)
```python
ma_chaine.isalpha()       # que des lettres ?
ma_chaine.isnumeric()     # que des chiffres ?
ma_chaine.islower()       # tout en minuscule ?
ma_chaine.isupper()       # tout en majuscule ?
ma_chaine.isidentifier()  # nom de variable valide ?
```

## 🛠️ Longueur et appartenance
```python
len("Bonjour")                 # 7
"Voiture" in "Voiture/Ballon"  # True
```

## ✅ À retenir
`find()` renvoie -1 si non trouvé (pas d'erreur) → à utiliser avec une condition. `index()` lève une exception `ValueError` → à utiliser avec un `try/except` si l'existence n'est pas garantie.
