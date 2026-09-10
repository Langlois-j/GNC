# Fiche 05 : Boucles (while / for)

## 🛠️ while
```python
i = 1
while i <= 3:
    print(i)
    i += 1
print("Terminé")
```

## 🛠️ for
`for` parcourt une **séquence** (chaîne, liste, range...).
```python
ma_phrase = "Bonjour"
for lettre in ma_phrase:
    print(lettre)

for i in range(10):   # 0 à 9
    print(i)
```

## 📌 Mots-clés de contrôle
| Mot-clé | Effet |
|---|---|
| `break` | Sort immédiatement de la boucle |
| `continue` | Passe directement à l'itération suivante |

## 💡 Bonnes pratiques
Les compteurs sont généralement nommés avec des lettres courtes : `i`, `j`, `k`.

## ✅ À retenir
`while` = tant qu'une condition est vraie (nombre d'itérations parfois inconnu). `for` = pour chaque élément d'une séquence (nombre d'itérations connu/fini).
