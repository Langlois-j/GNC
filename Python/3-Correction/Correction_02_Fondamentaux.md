# Correction 02 : Fondamentaux

## Exercice 1
```python
annee_naissance = input("Quelle est ton année de naissance ? ")
annee_naissance = int(annee_naissance)
age = 2026 - annee_naissance
print("Tu as environ", age, "ans")
```

## Exercice 2
```python
note = float(input("Quelle est ta note sur 20 ? "))
if note >= 16:
    print("Excellent")
elif note >= 12:
    print("Bien")
else:
    print("Insuffisant")
```

## Exercice 3
```python
for i in range(1, 11):
    print("7 x {} = {}".format(i, 7 * i))
```

## Exercice 4
```python
def est_pair(nombre):
    return nombre % 2 == 0

for i in range(1, 21):
    if est_pair(i):
        print(i)
```

## Exercice 5
```python
def stats(*nombres):
    minimum = min(nombres)
    maximum = max(nombres)
    moyenne = sum(nombres) / len(nombres)
    return (minimum, maximum, moyenne)

mini, maxi, moy = stats(4, 8, 15, 16, 23, 42)
print("Min: {}, Max: {}, Moyenne: {:.2f}".format(mini, maxi, moy))
```

## Exercice 6
```python
try:
    nb1 = int(input("Premier nombre : "))
    nb2 = int(input("Deuxième nombre : "))
    res = nb1 / nb2
except ZeroDivisionError:
    print("Division par 0 interdite")
except ValueError:
    print("Saisie non numérique")
else:
    print("{} / {} = {}".format(nb1, nb2, res))
finally:
    print("Fin du calcul")
```
