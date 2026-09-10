# Fiche 13 : Listes

## 🛠️ Création
```python
inventaire = []                          # liste vide
inventaire = [1, "Voiture", "Maison"]    # liste hétérogène
inventaire = ["Voiture"] * 5              # 5 éléments identiques
inventaire = range(10)                    # séquence de 0 à 9
```

## 🛠️ Accès et slicing (indice de départ à 0)
```python
inventaire[1]        # élément d'indice 1
inventaire[:]         # tous les éléments (copie)
inventaire[:2]        # les 2 premiers (indices 0 et 1)
inventaire[-3]        # le 3e élément en partant de la fin
inventaire[1:4]       # indices 1 à 3 inclus (4 exclu)
```
💡 Mémo : `B - A` = nombre d'éléments affichés dans `inventaire[A:B]`.

## 🛠️ Modification
```python
inventaire[2] = "Lapin"          # remplacer un élément
inventaire[:2] = ["Clef"] * 2    # remplacer une tranche
```

## 🛠️ Méthodes courantes
```python
inventaire.append("Marteau")      # ajout en fin
inventaire.insert(1, "Enclume")   # ajout à une position précise
inventaire.remove("Enclume")      # retire la 1ère occurrence par valeur
del inventaire[1]                 # retire par indice
inventaire.index("Lapin")         # indice d'un élément
inventaire.sort()                 # trie la liste
inventaire.reverse()              # inverse l'ordre
inventaire.count("Chat")          # compte les occurrences
len(inventaire)                   # nombre d'éléments
" ".join(inventaire)              # fusionne en chaîne (éléments str uniquement)
```

## ⚠️ Piège : copie vs référence
```python
liste2 = liste1          # liste2 est une RÉFÉRENCE, pas une copie !
import copy
liste2 = copy.deepcopy(liste1)   # vraie copie indépendante
```

## ✅ À retenir
`liste2 = liste1` ne duplique pas la liste — modifier `liste2` modifie aussi `liste1`. Toujours utiliser `copy.deepcopy()` pour une copie indépendante.
