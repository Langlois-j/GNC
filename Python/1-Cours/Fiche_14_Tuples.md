# Fiche 14 : Tuples

## 📌 Définition
Un tuple est une séquence **immuable** (non modifiable après création).

## 🛠️ Création
```python
mon_tuple = ()          # tuple vide
mon_tuple = 25,          # 1 seule valeur : virgule obligatoire !
mon_tuple = (25, 60, 80) # plusieurs valeurs
```

## 🛠️ Accès
```python
mon_tuple[0]   # accès par indice, comme une liste

try:
    print(mon_tuple[2])
except IndexError:
    print("Hors range")
```

## 💡 Pourquoi utiliser un tuple plutôt qu'une liste ?
1. **Affectations multiples** : `val1, val2 = mon_tuple`
2. **Retours multiples** de fonction (voir fiche Fonctions) : `return (ret1, ret2)`

## ✅ À retenir
Contrairement à une liste, un tuple ne peut pas être modifié après sa création (pas d'`append`, `remove`, etc.) — utile pour des données qui ne doivent jamais changer.
